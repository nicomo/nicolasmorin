+++
title = "Machinebox"
date = 2018-01-31T13:48:42+01:00
description = "Playing around with Machinebox to automagically detect faces in photographs"
tags = [ "machinebox", "machine learning", "golang"  ]
type = "post"
feature_image = "/img/machinebox.png"
+++

Following an [experiment with the Google Cloud Speech API](/blog/speechapitests/), and another with the [Azure Vision API](/blog.azure-vision-api/), I continue my experiments in Machine Learning for archival materials with [Machine Box](https://machinebox.io/).

I read Machine Box founder's Mat Ryer's post about [How (he) built an image proxy server to anonymise images in twenty minutes](https://blog.machinebox.io/how-i-built-an-image-proxy-server-to-anonymise-images-in-twenty-minutes-e550466ea09e) and based my expriment on his.

He uses an image, detects a face in it, removes it and passes the modified image on. And reading the [machine box documentation](https://machinebox.io/docs), I saw it also had functionalities to train Machine Box to recognize a particular face, and then use it to find similar faces in other images.

Say I have thousands of pictures of meetings and demonstrations from March to June 1968, with thousands of people in them. We don't know these peope, but wouldn't it be cool to have Machine Box tell us that "Person #28" appears in photographs #123, #321, #832, #1022, #8844, etc?

Let's do that.

# Detecting faces

First, Machine Box is available as a Docker image. I hadn't used [docker](https://docs.docker.com/) before, and it's not the subject of this post, but damn, that's a cool tech. I'll certainly try to learn more about containers in the future.

Then Machine Box has a Go SDK, which I retrieved : ```go get github.com/machinebox/sdk-go```
 
Machine Box has separate docker images for its different services, and for my purpose I'll start the server for the Facebox service: 

```docker run -p 8080:8080 -e "MB_KEY=$MB_KEY" machinebox/facebox```

with MB_KEY being the key provided with the Machine Box account I created on the site.

I first need to create a facebox client pointing to the machine box running on my local machine: 

```fb := facebox.New("http://localhost:8080")```

My first image is going to be this one:

![May 1968 Groupe photo](/img/1968-sample-b.png "May 1968 Groupe photo")

Let's start processing it.

```
// read source image
reader, err := os.Open("/images/src00001.png")
if err != nil {
    log.Fatal(err)
}
defer reader.Close()

// put the image in a []bytes, which will be expected by the face api
b, err := ioutil.ReadAll(reader)

// detect faces in image using the Check API
faces, err := fb.Check(bytes.NewReader(b))
if err != nil {
    log.Fatal(err)
}
```

In our case, the result is a slice of 6 Faces, each with its coordinates in the source picture. I want to extract those faces, and save them each as a standalone image file. This [blog post about the Go image/draw package](https://blog.golang.org/go-imagedraw-package) is a good starting point and explains how to do the actual copy.

Ranging over each face, I can 

```
// create a destination image of the appropriate size
// i.e. of the size of the face I'm going to paste in
dstImg := image.NewRGBA(image.Rect(0, 0, f.Rect.Width, f.Rect.Height))

// copy face from src image to new img
srcPoint := image.Pt(f.Rect.Left, f.Rect.Top)
draw.Draw(dstImg, dstImg.Bounds(), srcImg, srcPoint, draw.Src)

// let's create a file to save the "avatar-like" image of the face
filename := "person" + strconv.Itoa(i) + ".png"
dstFile, err := os.Create(filename)
if err != nil {
    log.Fatal(err)
}
defer dstFile.Close()

// I don't think I can write an image.Image directly into a file, so
// create a buffer (io.Writer) and encode the destination image to the buffer
buf := bytes.NewBuffer(nil)
err = png.Encode(buf, dstImg)
if err != nil {
    log.Fatal(err)
}

// write buffer to file
_, err = io.Copy(dstFile, buf)
if err != nil {
    log.Fatal(err)
}
```

I end up with 6 new files

<div style="text-align:justify">

 <img style="display:inline-block" src="/img/1968-person-0.png" alt=""  /> 
 <img style="display:inline-block"src="/img/1968-person-1.png" alt=""  />
 <img style="display:inline-block"src="/img/1968-person-2.png" alt="" />
 <img style="display:inline-block" src="/img/1968-person-3.png" alt=""  /> 
 <img style="display:inline-block"src="/img/1968-person-4.png" alt=""  />
 <img style="display:inline-block"src="/img/1968-person-5.png" alt="" />

</div>

# Teach Facebox about the faces

Now I can train Facebox to recognize these faces. The SDK has a Teach method with the following signature: ```func (c *Client) Teach(image io.Reader, id, name string) error```

So it's a matter of reading back our face image into a reader:

```
// read source image
reader, err := os.Open("/images/person0.png")
if err != nil {
    log.Fatal(err)
}
defer reader.Close()
```

to then send it to teach, using the filename as both the unique ID and the name (since we don't know the name of the person, it's going to just be person-0)

```
// read back the face image
faceReader, err := os.Open("/path/to/my/face/file/0.png")
if err != nil {
    log.Fatal(err)
}
defer faceReader.Close()

// send image to Teach
err = fb.Teach(faceReader, "0.png", "person0")
if err != nil {
    log.Fatal(err)
}
```

# Are there similar faces in our batch?

The final API I'll use is ```Similar```, with this picture: the guy raising his arm on the left was also on our first picture.

![May 1968 Group 2 photo](/img/1968-sample.png "May 1968 Group 2 photo")

When I send my second image to the Similar API (process is really the same as Check, I won't repeat it here), I retrieve a slice with 1 result of type Similar, which is an ID (_in our case the file name of picture #1, where we first encountered guy with raised arm_) and a name (_person-0_).

# What next?

So it seems possible to have Machine Box kind of teach itself about the faces in your photographs. I could certainly imagine a workflow where you test, for any new image, if it has already known faces. If yes, tag the new pictures with those names, if not, save the new face as a new picture and teach Machine Box about it.

You could then, many many years after the _events_ of May 1968, scan the crowds and "track" the people who participated in demonstrations and meetings. Could be great for many historic collections, in fact. Imagine teaching Machine Box about the face of, say, Marcel Proust, and feed Face box with many historical pictures from the period. Who knows, it might spot Marcel in previously unknown photographs? That'd be cool.