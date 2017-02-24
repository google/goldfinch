# Goldfinch: GOogLe image-search Dataset for FINe grained CHallenges

Goldfinch is a dataset for fine-grained recognition challenges. It contains a list of bird, butterfly, aircraft, and dog categories with relevant Google image search and Flickr search URLs. In addition, it also includes a set of active learning annotations on dog categories. Goldfinch was published along with our [ECCV'16](http://www.eccv2016.org/) paper [The Unreasonable Effectiveness of Noisy Data for Fine-Grained Recognition](https://arxiv.org/abs/1511.06789).

Here we list the files included in this release and their formats. Where possible, we have mapped category names to freebase ids as a form of canonicalization. Questions can be directed to jkrause@google.com and howardzhou@google.com.

----
## Class files

### cub_classes.txt:
For each category in the CUB dataset:
```
CUB class name,freebase id
```
E.g.
```
Black-footed Albatross,/m/04njb7
Laysan Albatross,/m/0544gc
Sooty Albatross,/m/07yydf
...
```

### birdsnap_classes.txt:
For each category in the Birdsnap dadataset:
```
Birdsnap class name (scientific),freebase id
```
E.g.
```
Accipiter cooperii,/m/01_ryh
Accipiter gentilis,/m/01vl7n
Accipiter striatus,/m/01_rvy
...
```

### fgvc_classes.txt:
For each category in the FGVC-Aircraft dataset:
```
FGVC class name
```
Note: no freebase id is used for aircraft since not all aircraft in FGVC
correspond to a freebase entity.
E.g.
```
ATR-42
ATR-72
Airbus A300B4
...
```

### sdog_classes.txt:
For each category in the Stanford Dogs dataset:
```
Stanford Dogs class name,freebase id
```
E.g.
```
affenpinscher,/m/01p2dp
afghan_hound,/m/011l1
african_hunting_dog,/m/02twvh
...
```

### bird_classes.txt:
For each category in L-Bird:
```
scientific name (estimated),freebase id
```
E.g.
```
"lithoptila abdounensis",/m/0100hjcf
"kurrartapu johnnguyeni",/m/010hmtwz
"zosterops kirki",/m/011l7vvz
...
```

### lepidoptera_classes.txt:
For each category in L-Butterfly:
```
scientific name (estimated),freebase id
```
E.g.
```
"sibirarctia kindermanni",/m/0100bkjp
"zamarada metallicata",/m/0100jnk9
"secusio strigata",/m/0100mnkj
...
```

### dog_classes.txt:
For each category in L-Dog:
```
breed name,freebase id
```
E.g.
```
"greyhound",/m/03d12
"boykin spaniel",/m/08s0ws
"white shepherd",/m/05912f
...
```

### aircraft_classes.txt:
For each category in L-Aircraft:
```
category name
```
E.g.
```
"aai rq 7 shadow"
"aero ae 45"
"aero boero ab 95"
...
```

----
## Image URLs

Compressed version of URL text files. Github has a 100MB file size limit. As a
result, we had to split bird_urls into 2 files: bird_urls1, bird_urls2 and
compress them separately.
### aircraft_urls.txt.7z
### bird_urls1.txt.7z
### bird_urls2.txt.7z
### dog_urls.txt.7z
### lepidoptera_urls.txt.7z

For each image search image:
```
freebase id (or category name for aircraft),urls
```
Note that if more than one url is given, that indicates the same image is hosted
at more than one url, which we provide for convenience in case one of the urls
goes down. Where possible, we have provided links to full resolution images, but
when not possible a link to a thumbnail is provided.

E.g.
```
"Airbus A330-300",http://cdn1.airplane-pictures.net/images/uploaded-images/2011/10/12/162077.jpg,http://parvaneganup.ir/images/6uhb245d7xyce2osaol3.jpg
"lockheed c 5 galaxy",http://www.davidandivy.co.uk/images/ac1_lockheed_c5a_galaxy.jpg
"breda ba 88",http://www.slitherine.com/forum/download/file.php?id=1535
...
```

### flickr_{aircraft,bird,lepidoptera}.txt:
For each image in the Flickr testing set:
```
freebase id (or category name for aircraft),urls
```
E.g.
```
"northrop f 20 tigershark",http://farm8.staticflickr.com/7151/6387816433_fbf6240392_b.jpg
"transall c 160",http://farm1.staticflickr.com/292/19707583438_e199092d07_c.jpg
"mikoyan mig 29",http://farm3.staticflickr.com/2831/9358339349_271a6f28cd_c.jpg
...
```

----
## Active learning files

### sdogs_active_learning_iteration{1,2}.txt: 
Images mined from Yahoo Flickr Creative Commons 100M dataset.  Format of each
line, with values delimited by commas:
```
1. Freebase id (see sdog_classes.txt for mapping to human-readable names)
2. Rater majority vote (boolean)
3. Url
4-7. Generic dog detector pixel coordinates xmin,ymin,xmax,ymax
8. Rating 1 (boolean)
9. Rating 2
11. Rating 3
12. (Optional) Rating 4
```
E.g.
```
/m/0353qr,1,http://farm9.staticflickr.com/8254/8683911774_a6fc49bdc0.jpg,85,61,196,288,0,1,1,0
/m/071jj,1,http://farm8.staticflickr.com/7323/9986061755_4ca1cd84db.jpg,160,122,236,203,1,1,1,
/m/03w0j9,0,http://farm6.staticflickr.com/5022/5685535269_dd9ee7cbb1.jpg,69,23,473,351,0,1,0,
...
```

Questions can be directed to jkrause@google.com and howardzhou@google.com.
