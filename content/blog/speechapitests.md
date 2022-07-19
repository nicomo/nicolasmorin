+++
title= "Google Speech API"
date= 2018-01-10T10:00:03+01:00
description = "Playing around with the Google Speech API to automagically index sound files"
tags = [ "divers", "google", "speech recognition", "golang" ]
type = "post"
feature_image = "/img/google-speech-api.png"
+++

This past year, we've heard a lot about the progress of Machine Learning algorithms and that got me thinking. Libraries and archives have a lot of sound files around, which can't be easily used: for the most part, if you want to know what's in them you either have to listen to them, or hope that an archivist did and provided the necessary metadata, which is quite time consuming, and there's a lot of backlog around...

So my initial question was: could one use those Machine Learning APIs provided by Google, Microsoft, et al. to somewhat automate the process?

## Using the API

For this little experiment I used the [Google Speech API](https://cloud.google.com/speech/) and started by downloading the [Google Cloud SDK](https://cloud.google.com/sdk/).

You can directly stream sound files to the Speech API provided they're less than a minute long each. The use case for this _synchronous_ speech recognition is that you talk to your phone and get a text back.

For longer files, the proper way to do it is to upload it to Google Storage and use the _asynchronous_ API. I opened a project in the GCloud Console, created a bucket and uploaded a bunch of files to Google Cloud Storage through the browser. In an actual project, one would have the program itself create the bucket and upload files from a local directory using the [Storage APIs](https://cloud.google.com/storage/docs/json_api/v1/). Maybe have a pipeline where you regularly scan the directory and upload files as they're copied there.

The Speech API [doesn't accept any file format](https://cloud.google.com/speech/docs/encoding). Specifically it doesn't accept mp3 (I used flac). And the file has to be mono, not stereo. So before uploading the files you might have to convert them. And again, depending on the number of files, you might look for solutions to automate the process, maybe using the [go-audio package](https://github.com/go-audio/audio).

Anyway, I uploaded a bunch of mono flac files to my bucket: each of my files now has a URI in the form ```gs://name-of-bucket/name-of-file``` with ```gs://``` here standing for Google Storage.

The Speech API itself is [fairly well documented](https://cloud.google.com/speech/docs/basics) and you should start there.  

In Go you need to ```go get``` and then import two packages in your code:

- cloud.google.com/go/speech/apiv1
- google.golang.org/genproto/googleapis/cloud/speech/v1

Then in ```main()```you need to create a client for the API, using the context

```
	ctx := context.Background()
	client, err := speech.NewClient(ctx)
	if err != nil {
		log.Fatalf("Failed to create client: %v", err)
	}
```

We also need to prepare a request for a given file. Note that ```LongRunningRecognizeRequest``` ([documented here](https://cloud.google.com/speech/reference/rpc/google.cloud.speech.v1#google.cloud.speech.v1.LongRunningRecognizeRequest)) requires

- a configuration, containing the encoding of the file to process (here: FLAC), and the spoken language expected in the file (here: fr-FR, could be en-US, etc)
- and the file URI

```
	req := &speechpb.LongRunningRecognizeRequest{
		Config: &speechpb.RecognitionConfig{
			Encoding: speechpb.RecognitionConfig_FLAC,
			LanguageCode: "fr-FR",
		},
		Audio: &speechpb.RecognitionAudio{
			AudioSource: &speechpb.RecognitionAudio_Uri{Uri: "gs://name-of-bucket/name-of-file"},
		},
	}
```

We're now ready to send the request to the API, retrieve the response (after waiting until it completes), then print the results.

```
	// send request to API
	op, err := client.LongRunningRecognize(ctx, req)
	if err != nil {
		log.Fatalf("could not perform asynchronous speech recognition: %v", err)
	}

	// retrieve response
	resp, err := op.Wait(ctx)
	if err != nil {
		log.Fatalf("could not retrieve the results: %v", err)
	}

	// Print the results.
	for _, result := range resp.Results {
		for _, alt := range result.Alternatives {
			fmt.Printf("\"%v\" (confidence=%3f)\n", alt.Transcript, alt.Confidence)
		}
	}
}
```

It's a fairly straightforward REST API call, which could easily be scaled to loop over many files.

## Results

I started with a recording of a conversation, in French, between 2 people. The mic is placed closer to speaker #1, so you hear him better than speaker #2, who's a bit further away. And it's a conversation, so their voices sometimes overlap, sentences are not always complete, with lots of "hum", and "yeah", etc. 

The result was basically unusable. The Speech API didn't recognize much of the 2 minutes extract I sent, only returning 2 sentences, with mediocre confidence. (And yes, on a scale of 0.0 to 1.0, 0.87 is mediocre...)

>"mai 68 tu étais déjà au milieu de la rue avec un panneau c'est quoi" (confidence=0.909360)
>
>"les échantillons pour participer quoi qu'est-ce que tu as fait de beau" (confidence=0.872880)

I then used a file where I had recorded myself reading a book in French. Not great, but much better. Sample result:

>"pour certains les livres sont des objets les collectionne les entoure de soin jaloux il ne les prête jamais on va aller voir pour l'enquête il les expos chez eux et n'ayant plus d'espace dans les déjà nombreuse partie de la maison remplie de bibliothèque il les emplacement pile comme si c'était des archivistes en train de dépouiller un leg un critique littéraire important préparant sa chronique un chiffonnier occasionnel" (confidence=0.920042)

So a few things are clearly off: for instance, _il les emplacement pile_ should be _il les place en piles_. But this is a fairly literary text, and the general meaning of the paragraph is there.

Next up: a file where I read a few sentences in English. My english is slightly accented, so that could throw the Speech API off, but the confidence is basically the same as me reading in French.

> "traveling with band was a real contrast compared to just saying that concerts that shows where complete chaos but the best was actually mellow mostly we drink beer past joints and listen to dub reggae music but then the best would pull up the doors with SNAP open and I will be three television cameras pointing up from the bottom of the stairs" (confidence=0.918201)

Again, some mistakes: _just saying that_ was supposed to be _just seeing that_, _the best was actually_ should be _the rest was actually_, and _the best would pull up_ is _the bus would pull up_. So not perfect, but not too far off the mark either.

Next up, a news anchor from Martinique island TV (slight French caribbean accent) opening the evening news. The show's opening music is running in the background.

> "Bonjour à tous nous sommes le mardi 2 janvier au sommaire ce soir une altercation qui tourne mal hier après-midi à la Cité La Chapelle à Saint-Joseph deux personnes ont été blessé par balle et à l'arme blanche une enquête gendarmerie a été ouverte la mise en place de Martinique transport depuis le 1er janvier recrute des croisiéristes il était plus de 400000 à faire escale en Martinique en 2016 ils sont encore plus loin de chez nous nous verrons comment faire accueil" (confidence=0.925828)

The first few sentences are great and the end... is basically garbage because the Speech API missed a few sentences and bolted the rest of what it understood to the last bit it had.

Finally, another news report, this time in English, from NPR, with perfect enunciation.

> "husband are recently retired and they're looking to move from Iowa to state with a warmer climate she says the new tax law will limit how much they can deduct on the home babe I calling up local tax offices in different states to try to understand what the impact will be" (confidence=0.945443)

In the last 2 cases, the sound quality was maybe not so great, as I played the clip over the internet and just recorded my laptop's speakers. Again: not perfect, but certainly usable. Still, I never got to a confidence > 0.95.

## So...

At this stage, my take is that the Speech API certainly can't be used to generate transcripts, even of sound files where the conditions seem good : no multiple speakers, no background noises, no strongly accented speech.

However, if the conditions are good enough, one could probably use the text returned by the API to try and automatically generate keywords for those sound files. 

In the Martinique newscast above, one could presumably do some text analysis and extract 

- places (``` Saint-Joseph, Martinique```)
- dates (```mardi 2 janvier```)
- possibly some subjects: ```deux personnes ont été blessé par balle et à l'arme blanche une enquête gendarmerie a été ouverte ``` [shot ... knife ... inquiry] points to a crime, while words such as ```croisiéristes``` [Cruise passengers] and ``` escale ``` [port of call] point to the tourism industry.

I don't have plans to use any of this for a real life project right now, but if I had some archival materials that would be a good candidate, in terms of speech and quality, I would certainly take some time to investigate this further. I'm thinking for instance about things like the [BBC Caribbean Archive 1988-2011](http://uwispace.sta.uwi.edu/dspace/handle/2139/11134): it's been beautifully done by the good people at the University of the West Indies, but still, 23 years of daily newscast would be a great candidate for such experiments with the Speech API.

Also, I plan to revisit what the Speech API can do next year. I certainly expect it to get better over time.