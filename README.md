# Gramac Detector 

## Usage
- for classification
```
python3 Gramac_classifier -i "FILE_PATH"
```

- for detection
```
python3 Gramac_detection -i "FILE_PATH"
```
note : 
> "FILE_PATH" is the path of the binary file which you want to predict。

note : 
> you need to unzip the model


## file description
* **Model**
classifier_model : the saving model of classification by randomforest
detection_model : the saving model of detection by randomforest
* **somethings_unimportant**
Ben_Result2 .csv : store the result of feature_extract_ben.py。
construct_FCG .py : reverse the binary file to function call graph(FCG) by r2pipe。
FCG_to_api .py : convert it into api-call graph。
feature_extract_ben .py : extract the feature of benign sample。
feature_extract_mal .py : extract the feature of malware sample。
Gramac .py : feature extract method code。
Mal_Result2 .csv : store the result of feature_extract_mal.py。
train .py : to train the model for the detector。
* **Gramac_classifier.py** : the classifier
* **Gramac_detection.py** : the detector
* **param_parser.py** :  for parsing args

## Detail work of our implement

* We first reverse the binary file to function call graph(FCG) by r2pipe, then convert it into api-call graph 。
* Next ,to extract the attribute of FCG:


the attribute we extract:
>* No. of vertices
>* No. of edges
>* No. of in degree
>* No. of out degree
>* No. of connected Component
>* No. of loops
>* No. of parallel edges

The dimension of feature is 7.


## Requirements

* python3
* radare2
* python package
  * r2pipe
  * networkx
  * pickle
  * sklearn
