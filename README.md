# Simple Concept DataBase

SCDB is a synthetic dataset developed for concept localization and inspired by the challenges of skin lesion classification using dermatoscopic images. It mimics the complex composition of diagnostic criteria in skin lesions e.g. spatial overlap, providing concept annotations and concept segmentation masks.

If you use this dataset, please consider citing our associated [paper](https://arxiv.org/pdf/2005.01399.pdf):
```
    @InProceedings{lucieri2020explaining,
    author="Lucieri, Adriano
    and Bajwa, Muhammad Naseer
    and Dengel, Andreas
    and Ahmed, Sheraz",
    title="Explaining AI-Based Decision Support Systems Using Concept Localization Maps",
    booktitle="Neural Information Processing",
    year="2020",
    publisher="Springer International Publishing",
    address="Cham",
    pages="185--193",
    isbn="978-3-030-63820-7"
    }
```

<p align="center">
  <img src="Fig/000044.png" width="200" />
  <img src="Fig/000158.png" width="200" /> 
  <img src="Fig/000233.png" width="200" />
  <img src="Fig/000335.png" width="200" />
</p>

## Dataset Description
Skin lesions are represented as big geometric base shapes filled with concepts, that are represented as smaller geometries that are randomly coloured, shaped and oriented. 10 shapes representing single concepts are used:

+ Cross
+ Ellipse
+ Hexagon
+ Line
+ Pentagon
+ Rectangle
+ Star
+ Starmarker
+ Triangle
+ Tripod

Concepts relevant to the target classifciation task occure only within the area of the base shape. 8 out of 10 concept classes are relevant for classifciation. Two concept classes (Cross, Line) are non-correlated to target classes. Target classes are indicated by following concept combinations:

Target Class| Indicative Concept Combinations
---|:-:
C1|Hexagon&Star, <br>Ellipse&Star, <br>Triangle&Ellipse&Starmarker
C2|Pentagon&Tripod, <br>Star&Tripod, <br>Rectangle&Star&Starmarker

## Dataset Files
For each dataset split (*train*, *val*, *test*), label annotations (.csv) as well as concept annotations (.npy) are available. A separate concept split can be used for CAV training.

### Label Files
The .csv files are provided in the form "filepath|label".

### Concept Files
Concept annotations are provided in the form of binary, multilabel vectors of the size [Nx10], with *N = number of samples*. 

### Segmentation Files
Each split folder contains a *Segmentation* folder that contains a maximum of 10 concept-specific segmentation maps per sample. The concept's outline is segmented through a circle, covering the complete outline of the shape.

### Dataset Distribution

Split|Datafile|Annotations|Samples
---|---|---|:-:
Train|train.csv|train.npy|4800
Validation|val.csv|val.npy|1200
Test|test.csv|test.npy|1500
Concept|concept.csv|concept.npy|6000

