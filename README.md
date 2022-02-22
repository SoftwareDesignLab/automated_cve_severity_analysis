# CVE Severity and Exploitability Analysis

This repository contains training and test datasets for CVE severity analysis.
A model is trained with Deeplearning4J and its serialized version is also included.
The architecture of the model is shown below
![alt text](https://github.com/SoftwareDesignLab/automated_cve_severity_analysis/blob/main/cnn.png =250x250)


- If you want to update/customize the training data provided in the ARFF(Attribute-Relation File Format), download and install [Weka ML Software Package](https://www.cs.waikato.ac.nz/ml/weka/)
- To deserialize and use the Convolutional Neural Nets trained for the severity and exploitability prediction in your project, you can use [Deeplearning4J](https://deeplearning4j.konduit.ai/)

## severity model data
Includes the training (train.arff) and test (test.arff) datasets, and the serialized version of the trained model (severity.model).


## License
[MIT](https://choosealicense.com/licenses/mit/)