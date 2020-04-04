+++
title = "Gollico - ToC"
date = "2018-02-11T10:19:46+01:00"
description = "A Go Client for the Gallica APIs. #1. Table of Contents"
tags = [ "gallica", "golang", "gollico" ]
type = "post"
feature_image = "/img/gallica-toc.png"
+++

The _[Bibliothèque nationale de France](http://www.bnf.fr/)_ (BnF) has opened APIs for a number of services, including their [Gallica](http://gallica.bnf.fr/) digital library, which contains 4.3 millions of documents: digitized books, maps, photos, musical scores, etc. from the collections of the BnF and partner libraries.

I thought it'd be a nice little project to do a small set of client functions for those APIs: I'd practice Go, and familiarize myself with the APIs.

So I started doing that. First result is here:

- Code: https://github.com/nicomo/gollico
- Documentation: https://godoc.org/github.com/nicomo/gollico

It was good fun and I'll say at the outset that I think it's great the library is making efforts to provide APIs. But it's clearly early days yet.

Here's a list of the APIs provided for the Gallica digital library, which I have not implemented (yet): 

- Serials Holding: retrieves the years and issues for a periodical publication
- Metadata: retrieves the metadata / bibliographic data for a document
- Pages: retrieves the pages informations for a document, e.g. at which page is there a table of content in the document?
- Occurrence: retrieves the list of occurrences of a term in an indexed document
- Text: retrieves the OCRed text of a page / document
- Image: retrieves the image of a physical page of a document in various predefined formats (thmbnail, etc.)
- IIIF (International Image Interoperability Framework): standardized API to retrieve and manipulate images from the digital library
- and finally the Table of Contents API: given an identifier for a document in the digital library, it retrieves its Table of Content

### The ToC API

I chose to implement the **Table of Contents** API as a test. The principle is quite simple, it's a REST API, you give it the internal ID for a document, and your get back a table of content. I parse it and return it as json.

But. 

The result you get from the API can either be an HTML page, for documents processed by the BnF early in the Gallica project, or an XML TEI stream, for more recent documents. You can't know in advance. You have to test the result and parse accordingly.

For TEI, each entry is in a row:

```
<row>
    <cell>
        <seg n="int.000001">AVANT-PROPOS</seg>
    </cell>
    <cell>
        <xref n="lie.000001" type="image" from="FOREIGN(9754046/000011.jp2)">V</xref>
    </cell>
</row>
```

To generate the link to the page in the document, you have to regex the _from_ attribute to extract ```11``` from ```FOREIGN(9754046/000011.jp2)```.

As for the HTML response... it's a bit of a mess really. The meat of the information is in ```<div>``` and ```<a>``` tags. Like so:

```
<div class="Texte" style="font-size: 80%">
    RICHELIEU (cardinal de).Sa biblioth., 
    <a href="javascript:allerA('0083037', '36')">4</a>
    , <a href="javascript:allerA('0083037', '39')">7</a>
    , <a href="javascript:allerA('0083037', '40')">8</a>
    , <a href="javascript:allerA('0083037', '53')">21</a>
    . - Achète les manuscrits de Loménie, 
    <a href="javascript:allerA('0083037', '41')">9</a>
    . - Ses bibliothéc., 
    <a href="javascript:allerA('0083037', '39')">7</a>
    , 
    [elided for brevity]    
</div>
```

And as you can see in this very example, the ToC is sometimes... rather an index. _Id est_, you don't have a ToC like 

```
Title 1, p. 12 (url)
Title 2, p. 22 (url)
etc
```

but something like 

```
Title 1, p. 12 (url), p. 22 (url), some other text p. 32 (url)
Title 2 - p. 42 (url)
etc
```

The data is basically unstructured in my view. You can work with this, sure, but it's really a pain.

I bumped into further smaller obstacles, like encoding issues: the http Header for an HTML ToC says it's utf-8 but there are other encodings in there. Or the XML is explicitly in latin (but not always), while the Golang XML parser expects utf-8 by default. I thus had to detect the encoding in the incoming stream, and explictly set the encoding for the xml.Decoder, and generally switch it to permissive so as to be able to parse the responses without errors.

The data in there is really messy.

### License

The BnF tries to provide a fairly open license for much of its data, especially its metadata, as explained (in French) at http://api.bnf.fr/conditions-dutilisation. However, this doesn't seem to apply to the documents in the Gallica digital library, for which the site points to the [general conditions](http://gallica.bnf.fr/html/und/conditions-dutilisation-des-contenus-de-gallica). I can see several potential issues here:

- it is a bespoke license, which seems to have been created by the library itself. It is not something a developer might have encountered before, such as an MIT license, Creative Commons, or a traditional commercial license. This might create uncertainty for developers who might hesitate to invest work in using the APIs if they're unsure of what they are allowed to do with the data they retrieve.
- Commercial use of the API is restricted. You have to sign a separate license, and pay a fee. The price list doesn't seem to be specific to the API, but points to the same price list as if, for instance, you'd want to publish a print book containing a picture from the library. It's a whopping 60€ for a single image, and beyond 30 images, you're invited to negociate a bespoke deal with the library. Makes sense for a print book, not so much for an API. And generally I think this choice (but I guess the library didn't have much of a choice there? Third-party content?) limits the usefulness of the APIs.

Basically, you can do what you want with the _metadata_, but not with the documents themselves. Which, for a digital library, is quite a hurdle.

### Documentation

Not exhaustive but quite sufficient.

In French only though, as far as I could ascertain, which will limit the reach of the API.

### So?

I like APIs to be somewhat opinionated. By that I mean, if I may use a cooking metaphor: they don't just spit out the raw ingredients they have in the kitchen, they make choices, hide how the sausage is made and serve you a _dish_. So for the ToC API, for instance, it'd be great if the work I had to do on the client side, i.e. parsing TEI or HTML into a common, _ad hoc_ json format, dealing with the quirks of the underlying data, etc., was done on the server side.

I guess ease of use is a condition for any set of APIs to be widely adopted, and that certainly applies to the BnF if they want people outside of the library world to use theirs. It's not there yet.

All in all though, it looks like the BnF is trying to emulate https://labs.loc.gov/, and that's encouraging. A lot of legal and technical bumps on the road yet, sure, but I think it's great to see the national library at least taking these first steps. And the resources you can tap into here, those 4.5 million documents: that's huge.

As for me, I'll try to keep abreast of http://api.bnf.fr for the Gallica digital library, and I might try to enhance and maintain the Gollico package accordingly. Probably working on the IIIF API for images next? That looks to be the most interesting to me. Ping me if you have other ideas.

Also, I didn't bother to unit test the messy HTML case at this stage, as I just wanted to play around with the API, but it _should_ work. Please [open issues](https://github.com/nicomo/gollico/issues) if you see any.