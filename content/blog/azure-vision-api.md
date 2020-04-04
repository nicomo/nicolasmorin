+++
title= "Azure Vision Api"
date= 2018-01-17T12:09:18+01:00
description = "Playing around with the Azure Vision API to automagically index photographs"
tags = [ "microsoft", "machine learning", "vision", "golang" ]
type = "post"
feature_image = "/img/manioc-okoume.jpg"
+++

Following an [experiment with the Google Cloud Speech API](/blog/speechapitests/), where I tried to extract information from sound files - transcripts of speech, keywords, etc. - I thought I'd try another Machine Learning API, with the same overarching goal but a different project.

The overarching goal is still to use the Machine Learning APIs provided by such internet giants as Google or Microsoft and try to somewhat automate the treatment of archival and library material.

The project this time is to use Microsoft Azure to analyze images, and see what we can extract from them.

## Calling the api

There's no specific Golang documentation on the Azure Cognitive Sciences site yet, but there's [documentation](https://docs.microsoft.com/en-us/azure/cognitive-services/Computer-vision/) for several other languages, such as Python, and these are REST API calls, fairly straightforward to work with.

For each image, you should generate a request of the form 'https://[location].api.cognitive.microsoft.com/vision/v1.0/analyze[?visualFeatures][&details][&language]'

The first part is just the base URL for the service. You can point your program at, say, _westcentralus.api.cognitive.microsoft.com_

visualFeatures is a comma-separated list of keywords listing the services you want performed. From the documentation:

>Categories - categorizes image content according to a taxonomy defined in documentation.
>
> Tags - tags the image with a detailed list of words related to the image content.
>
> Description - describes the image content with a complete English sentence.
>
> Faces - detects if faces are present. If present, generate coordinates, gender and age.
>
> ImageType - detects if image is clipart or a line drawing.
>
> Color - determines the accent color, dominant color, and whether an image is black&white.
>
> Adult - detects if the image is pornographic in nature (depicts nudity or a sex act). Sexually suggestive content is also detected.

The same holds for the oddly-named _details_ parameter:

> Celebrities - identifies celebrities if detected in the image.
>
> Landmarks - identifies landmarks if detected in the image.

And finally the language parameter, which can be _en_ or _zh_ and defaults to _en_ if empty.

You also have to insert a minimum of information in the http header.

_Ocp-Apim-Subscription-Key_ is a string with your subscription key, which provides access to the API. It's obviously a required param.

The _Content-Type_ can be :

- either _application/json_ if, in the http body, you provide a url to the image to analyse, like so: {"url":"http://example.com/images/test.jpg"}
- or _application/octet-stream_ if, in the http body, you upload the image as a raw image binary

## Test with one image

### Analyze

The image we are using is not very good: a grainy scan of an old black and white picture in a book.

![Archival picture: cutting an Okoumé tree](/img/manioc-okoume.jpg "Archival picture: cutting an Okoumé tree")

This basic Go code just constructs an http request for a single image, but asking for multiple services gathered together in the [Analyse API](https://westus.dev.cognitive.microsoft.com/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e1fa).

```
var azureKey = "myKey"
var baseURI = "https://westeurope.api.cognitive.microsoft.com/vision/v1.0/"

func main(){
	client := &http.Client{}

	// our image #1
	imgURL := "{\"url\":\"http://www.manioc.org/gsdl/collect/images/index/assoc/GAD12017/0019i2.dir/GAD120170019i2.jpg\"}"

	// analyze service
	resp, err := analyzeImg(client, strings.NewReader(imgURL))
	if err != nil {
		log.Fatalf("uh oh, something went awry: %v", err)
	}
	defer resp.Body.Close()
	
	// parse the analyze response
	analyzeBody, err := ioutil.ReadAll(resp.Body)
	if err != nil {
		log.Fatalf("could not read the response body: %v", err)
	}
	fmt.Printf("RESPONSE:\nSTATUS: %v\nBODY: %v\n", resp.Status,string(analyzeBody))
}

// analyze API
func analyzeImg(c *http.Client, b *strings.Reader) (*http.Response, error) {

	analyzeURL := baseURI + "analyze?visualFeatures=Categories,Tags,Description,Faces,ImageType,Color&details=Landmarks"
	req, err := http.NewRequest("POST", analyzeURL, b)
	if err != nil {
		log.Fatalf("could not create http request: %v", err)
	}
	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("Ocp-Apim-Subscription-Key", azureKey)
	
	resp, err := c.Do(req)
	if err != nil {
		return nil, err
	}
	return resp, nil
}
	
```

The result we get is interesting.

We get a few "obvious" but useful informations such as the file format (```Jpeg```), the size of the source image (```1456 x 1085```) and the fact that it's B&W (```true``` that). 

The generated description is clearly wrong, but azure wasn't very confident about it anyway : <code>{ "text": "a black and white photo of a man", "confidence": 0.8989096 }</code>. Our program should probably discard descriptions below a certain threshold of confidence, say 0.93.

The tags, though, are interesting, esp. those with a confidence score > 0.9 : we retrieved _text_, _tree_, and _book_, which are all pertinent.

### OCR

The Analyze service also returned an indication that it spotted text on the image: ```"tags":[{"name":"text","confidence":0.99899858236312866}]```

In which case I might want to use the separate [OCR service](https://westus.dev.cognitive.microsoft.com/docs/services/56f91f2d778daf23d8ec6739/operations/56f91f2e778daf14a499e1fc) API. 

Its use is exactly the same as the analyze service above, so I won't repeat the code here.

In its response, Azure correctly asserts that the text is in French (<code>"language": "fr"</code>), and spots three chunks of text : 

<code>Cliché Agence générale des Colonies.</code>

<code>Photo VVin1ner</code>

<code>Abatage d'un Okoumé. (Gabon).</code>

You see that appart from the proper name _Wintner_, which became _VVin1ner_, the rest is spot on. Our program could weed out unlikely words like _VVin1ner_ and generate both a text caption and more keywords for the image. 

## Faces in 20 images 

Let's now use a bunch of images at once and see if we can get interesting aggregate information.

For instance, I have a bunch of pictures taken during the strikes and demonstrations in May 1968 in Paris. Sample image below.

![May 1968 image](/img/1968-sample.png "May 1968 image")

For each image, the Analyze service tells me if it found faces, and if it did, it tried to guess the age and gender of the person. The _json_ I get back looks like this.


```
"faces": [{
	"age": 37,
	"gender": "Male",
	"faceRectangle": {
		"left": 47,
		"top": 325,
		"width": 45,
		"height": 45
	}
}, {
	"age": 87,
	"gender": "Male",
	"faceRectangle": {
		"left": 499,
		"top": 354,
		"width": 45,
		"height": 45
	}
}]
```

I can loop over the images, loop over the faces it found, and store each face information as a new line in a .csv file, with the ages in the first column and the gender in the second column, discarding the box information. Let's do that.

Each photo is going to have 0 or more ```Face```and we'll need the structs for that:

```
type Face struct {
	Age    int
	Gender string
}

type Photo struct {
	RequestId string
	Faces     []Face
}
```

We can then unmarshal the json response into the struct, like so: 

```
var photos []Photo
err := json.Unmarshal(jsonBlob, &photos)
if err != nil {
	fmt.Println("error:", err)
}
```

We then have access to the data itself:

```
for _, v := range photos {
	for _, f := range v.Faces {
		fmt.Printf("%d;%s\n", f.Age, f.Gender)
	}
}
```

outputs the information we need, which we can store in a file: 

```
18;Male
41;Female
35;Male
29;Female
31;Male
```
Over a small batch of 20 pictures, I got 24 faces recognized. Far less than where actually in the pictures, but still a fairly decent number.

The gender split is 5 women for 19 men, which seems intuitively correct: '68 might have been about sexual revolution and the empowerment of women, but in Paris in 1968, from the pictures I had at least, men run the show. They're far more numerous in the pictures of meetings and demonstrations I saw. What's more, they are far more often speaking and generally at the center of the image, and thus more easily spotted by the algorithm.

The age is an interesting feature as well. May '68 was all about youth, but the average age of those 24 people in the pictures is 33.5 years old. Even though I suspect it's not really accurate.

All in all this would obviously need further investigations, esp. regarding reliability of the results, but it's encouraging: with very little effort you can certainly get useful information back from the Microsoft Cognitive Sciences APIs. A cool tool.