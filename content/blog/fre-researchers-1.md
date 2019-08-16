+++
title = "A Database of French Researchers (1)"
date = 2019-08-15T07:57:36+02:00
draft = true
description = "First results of a project about French researchers and their publications"
tags = [ "data", "research" ]
type = "post"
image = "img/fre-researchers-1.jpg"

+++

During the spring and this summer, I worked on and off, in my free time, on a side project about French researchers and their publications. This is an ongoing work, but I think it's interesting to start documenting the first results I have.

Anyone with a passing knowledge of the French Higher Ed landscape will know this is a daunting task: polite decision makers talk of a _fragmented_ system; less polite people confess it's a terrible mess, a jumble of overlapping structures and competing loyalties, with Universities, University groups, _Ecoles_, the CNRS, and labs big and small with multiple parent organisations.

My primary objective is to do 3 things : get the names of as many researchers in the French higher education system; match them with research labs in the country; gather their publications, with a focus on monographs.

I used publicly available information, especially from Sudoc, the French union catalog of university libraries, OCLC and the [GRID project](https://grid.ac/). I was especially impressed with the work done by GRID to make sense of the institutes and structures in french HE.

The first result, for me, was that it seems it is indeed possible to build such a database, even though it is always going to be an approximation of the reality.

So, let's look at a first batch of numbers.

## Labs

I identified a little more than 500 research labs. Those are not all the labs in French universities, _écoles_, etc.: the set is skewed towards the bigger labs with an affiliation with the CNRS. Smaller, less recognized labs are harder to pinpoint.

I identified about 31 000 researchers and managed to match 21 000 of them with their respective lab and, sometimes, with their employer (university, _école_). I don't have data about other countries, but the size of the typical french research lab seems small to me, especially given my above remark about the data set being skewed towards bigger, more established labs. The range is from under 10 researchers to about 200 researchers, with an average of 39 researchers per lab and a median of 32, _id est_ about 250 labs have under 30 researchers working in them. _Fragmented_, they said. See distribution.

![distribution of lab sizes](/img/fre-researchers-1-graph1.png "distribution of lab sizes")

Those researchers are not as concentrated in Paris and the surrounding area as one might think for a very centralized country like France:

- 29% of researchers are tied to labs with an official address in Paris and the _Ile-de-France_ region
- 71% are in the provinces, with the Auvergne-Rhône-Alpes region centered on Lyon coming second behind Paris: it houses 17% of all identified researchers.

## Identifiers

I tried to found [IdRef](https://www.idref.fr/) IDs, [VIAF](http://viaf.org/) IDs and [WorldCat Identities](https://www.worldcat.org/identities/) for these researchers. It's a first pass and I'll try to get better results later if I can, but I was fairly successful with IdRef: those 31 000 researchers I scooped up all have national IDs, which makes sense because as researchers they have a PhD and you get an IdRef if you registered for a doctorate in France.

And since Abes, which manages IdRef, contributes to VIAF, I also got about 31.000 viaf IDs for French researchers. Which then allowed me to pull other IDs for the same person: Worldcat ID, Library of Congress ID, ORCID, Wikidata ID, etc. IDs galore! 🎉

I'm not really using them just yet, but that's going to be important going forward.

## Case in point: Worldcat Identities

For about 8.300 researchers I could use a known ID to find their [WorldCat Identity](https://www.worldcat.org/identities/) page. It doesn't mean only 8.300 have Worldcat Identities, just that at this stage I found pages for that number.

I have not dealt with the publications linked to those identities, but for that first pass, I did retrieve some general information about worldcat records for those people.

This is interesting because all French Higher Education libraries contribute their holdings to worldcat through the Sudoc union catalog, and I think Worldcat is probably a good proxy for holdings of research monographs by current french researchers internationally. So, what do we have?

### Works

Our 8.300 French researchers have 295 000 works registered to them in Worldcat, with an average of 36 works per person, and a median of 22 works. The top 4 "producers" are men at the very end of their academic carreer:

- Marc FUMAROLI (780 works)
- Roger CHARTIER (705)
- Georges DIDI-HUBERMAN (694)
- Pascal ORY (675)

### Holdings

These 295 000 works correspond to about 6.9 millions library holdings worldwide, an average of 841 holdings per researcher and 24 holdings per work.

But interestingly the top 5 authors by holdings are different, and holdings might be a better proxy than the number of works for influence.

- Roger CHARTIER
- [Abdelkader HAMEURLAIN](https://www.worldcat.org/identities/lccn-n97077051), a computer scientist who seems to have published about 30 to 40 papers a year for the last 10 years (🤦‍♂) in Conference proceedings widely held in libraries around the world
- François DE SINGLY
- Thomas PIKETTY
- Marc FUMAROLI

The top 1% of authors account for 12% of library holdings, and the top 10% account for 42% of library holdings. There's a very very long tail here, see the complete distribution.

![distribution of library holdings](/img/fre-researchers-1-graph2.png "distribution of library holdings")

### Languages

Another marker of influence might be the languages of the works. Do you write in English, in French, or in another language? If you write in French, are your works translated?

The works held in Worldcat for these authors are in French (63%), English (36%), and only 1% for all other languages put together.

3 233 researchers (39%) have more than 90% of their publications in French. At the other end of the spectrum, 756 (9%) have less than 10% of their publications in French.

Do researchers who publish in English have a disproportionate number of holdings in libraries worldwide, as would seem intuitive, compared to their colleagues who publish in French? The correlation coefficient between the two numbers for that sample of 8 300 researchers turns out to be 0.34, which indeed seems to indicate a (moderate) positive correlation: the more you publish in English, the more your books are held in libraries worldwide.

----------

These were just a few first results from the database, on a fairly general level. I'm working on associated documents right now. I'll then have institutions + researchers + documents, _id est_ the basics blocks I need to then be able to play around with the data. I'll keep you posted here.
