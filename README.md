# Evaluation Data for the Annotation of German and English New Testament Texts with Strong's Numbers

This repository provides a gold standard for parallel Bible texts and offers annotation of 20 New Testament verses with Strong's numbers referring to Greek words, see https://doi.org/10.5281/zenodo.8024803.

We considered three German texts (Luther 2017, Schlachter, and Hoffnung für alle) and two English texts (New Revised Standard Version and World English Bible):       

| Name        | Language | Year | Approach            |
|-------------|----------|------|---------------------|
| Luther 2017 | German   | 2017 | thought-for-thought |
| Schlachter  | German   | 2000 | word-for-word       |
| HFA         | German   | 2021 | paraphrase approach |
| NRSV        | English  | 1989 | paraphrase approach |
| WEB         | English  | 2015 | paraphrase approach |

## Background
Text concordance building, automated text alignment, and automated text translation are well-studied research topics. The data in this repository can be used to evaluate the task of automatically annotating words within New Testament texts in order to create parallel Bible corpora in different languages. The goal is to produce cross-lingual concordances for New Testament texts and translations. These are widely used in research and teaching. For an example of a use case, see [https://www.stepbible.org/].  

## Selected verses

To evaluate unannotated texts, we created gold standards for several verses and translations. We chose 20 verses from different books, both from the Gospels and the Acts of the Apostles, and from different epistles. It was important to choose a variety of verses, both from narrative texts (e.g. Mark 10:3; Luke 1:9; John 12:2, 21:1; Acts 8:14) and from Gospel-specific verses (e.g. Mark 1:1; John 19:35), enumerations (e.g, Acts 27:5), apocalyptic texts (Rev 1:19; 14:5), and letters (e.g., Rom 1:1; 12:4; Eph 1:8; 1 Peter 1:10; 1 John 1:5; Jude 1:8). 

## Documentation and Usage

The data comes as generic json file. In Python you may read this data with ```json``` library:
```Python
import json
f = open('bible-gs.json')
data = json.load(f)
```

Defining a Bible text and a verse makes the data directly accesible: 

```Python
verse = "1 John 1:5"
bible = "WEB"
text = "This is the message which we have heard from him and announce to you, that God is light, and in him is no darkness at all."
# Pick a position and output the example annotation
i = 4
print ("'"+text.split(" ")[i]+"' -> G"+data[verse][bible][i])
```

## Citation

If you use this work, please cite:


```bibtex
@inproceedings{dorpinghaus2021automated,
  title={Automated creation of parallel Bible corpora with cross-lingual semantic concordance},
  author={D{\"o}rpinghaus, Jens and D{\"u}ing, Carsten},
  booktitle={2021 16th Conference on Computer Science and Intelligence Systems (FedCSIS)},
  pages={111--114},
  year={2021},
  organization={IEEE}
}
```
```bibtex
@dataset{dorpinghaus_jens_2023_8024803,
  author       = {Dörpinghaus, Jens},
  title        = {{Evaluation Data for the Annotation of German and 
                   English New Testament Texts with Strong's Numbers}},
  month        = jun,
  year         = 2023,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.8024803},
  url          = {https://doi.org/10.5281/zenodo.8024803}
}
```

