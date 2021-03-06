# Severity Analysis of Exploted CVEs Published by CISA
There is an increasing trend in the yearly volume of published software vulnerabilities [[1](https://www.techrepublic.com/article/2021-marks-another-record-year-for-security-vulnerabilities/)]. Common Vulnerability and Exposure (CVE) reports published by Vulnerability Management Systems are used to evaluate the severity and exploitability of software vulnerabilities. Security professionals keep track of published software vulnerabilities to make sure their systems are not vulnerable to the recently disclosed CVEs.

This repository provides a case study to analyze CVEs included in CISA's [Known Exploted Vulnerabilities Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog).
A binary Convolutional Neural Network is trained on the descriptions of the CVEs published between 1999 and 2019 at [US National Vulnerability Database](https://nvd.nist.gov/) to assess the severity of disclosed software vulnerabilities. The model labels the severity of each CVE either MEDIUM or HIGH depending on its severity and exploitability.
## Case Study Result
- There are 238 total exploited 2020, 2021, and 2022 CVEs published by CISA [here](https://www.cisa.gov/known-exploited-vulnerabilities-catalog), CVE-2022-22587 was ecluded because it was RESERVED and did not had a valid description.
- Our model labeled 214 of these 238 CVEs with a HIGH severity.
- Overall model accuracy is 89.9%.
- ![alt text](https://github.com/SoftwareDesignLab/automated_cve_severity_analysis/blob/main/chart.png)
- For the same set of CVEs, we checked [NVD data](https://nvd.nist.gov/vuln/data-feeds) and found that NVD labeled 215 of these CVEs as either HIGH or CRITICAL severity (Accuracy 90%). 


## Data description
### severity model data
This directory includes the training data (train.arff) and the serialized version of the trained CNN model. 
The training data includes CVEs between 1999 and 2019 (inclusive). 
A test data set(test.arff) is included, to test the model for all CVEs published during 2020.

### cisa_known_exploited_vulnerabilities.csv
This file includes CISA CVEs (test set) used in the case study.
> Becase the training data set included CVEs between 1999 and 2019, CVEs before 2020 were excluded from the tests set during the case stuy.

### How to Use or Customize the Model?
- The architecture of the CNN model used to evaluate the severuty of CVEs 
![alt text](https://github.com/SoftwareDesignLab/automated_cve_severity_analysis/blob/main/cnn.png)
- To customize the data and/or retrain the model:
  - If you want to update/customize the training data provided in the ARFF(Attribute-Relation File Format), download and install [Weka ML Software Package](https://www.cs.waikato.ac.nz/ml/weka/)
  - To train a new model or deserialize and use existing Convolutional Neural Net model, you can use [Deeplearning4J](https://deeplearning4j.konduit.ai/)

## License
[MIT](https://choosealicense.com/licenses/mit/)