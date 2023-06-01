# clinical_trial

Example of analysing data from a clinical trial using synthetic data.

## The Data

**clinical_study.csv**

|COLUMNS|DESCRIPTION|
|-------|-----------|
|subject_id|Patient ID|
|sex|Whether the patient is male or female|
|age|The age of the patient|
|weight|The weight of the patient|
|height|The height of the patient|
|trt_grp|Whether the patient is receiving the new drug or the standard of care (control)|
|response|Whether the patient responsed|

|subject_id|age|sex|weight|height|trt_grp|RESPONSE|
|----------|---|---|------|------|-------|--------|
|SUBJ_001|46.0|Female|84.66|1.59|DRUG|N|
|SUBJ_002|47.0|Female|71.21|1.64|DRUG|N|
|SUBJ_003|48.0|Female|69.85|1.73|CONTROL|N|
|SUBJ_004|59.0|Female|62.94|1.50|DRUG|Y|
|SUBJ_005|59.0|Female|113.91|1.63|CONTROL|N|
|SUBJ_006|63.0|Male|79.33|1.77|CONTROL|Y|
|SUBJ_007|77.0|Male|96.12|1.77|CONTROL|N|
|SUBJ_008|57.0|Male|93.50|1.63|DRUG|N|
|SUBJ_009|72.0|Male|85.57|1.68|DRUG|N|

**protein_levels.csv**

|COLUMNS|DESCRIPTION|
|-------|-----------|
|participant_id|Patient_ID|
|protein_concentration|Concentration of a blood protein (ug/L) that might be a potential predictive biomarker of response|


|participant_id|protein_concentration|
|--------------|---------------------|
|SUBJ_001|148.0|
|SUBJ_002|85.0|
|SUBJ_003|183.0|
|SUBJ_004|89.0|
|SUBJ_005|137.0|
|SUBJ_006|116.0|
|SUBJ_007|78.0|
|SUBJ_008|115.0|
|SUBJ_009|197.0|

We want to adress questions such as:
* Do patients that take the drug respond more to treatment compared to those in the control group?
* Can we use data science to predict whether a patient will respond better to the new treatment?

## Examining Data

`clinical_study.info()`

|#|Column|Non-Null Count|Dtype|
|-|------|--------------|-----|
|0|subject_id|772 non-null|object|
|1|age|772 non-null|float64|
|2|sex|772 non-null|object|
|3|weight|761 non-null|float64|
|4|height|772 non-null|float64|
|5|trt_grp|772 non-null|object|
|6|RESPONSE|772 non-null|object|

`clinical_study.describe()`

|   |age|weight|height|
|---|---|------|------|
|count|772.00|761.00|772.00|
|mean|61.58|91.11|1.677|
|std|7.87|22.49|0.10|
|min|7.20|22.31|1.19|
|25%|57.00|75.55|1.60|
|50%|62.00|88.87|1.67|
|75%|67.00|104.65|1.76|
|max|79.00|182.50|1.94|

`protein_levels.info()`

|#|Column|Non-Null Count|Dtype|
|-|------|--------------|-----|
|0|participant_id|768 non-null|object|
|1|protein_concentration|763 non-null|float64|

`protein_levels.describe()`

|   |protein_concentration|
|---|---------------------|
|count|763.00|
|mean|121.69|
|std|30.54|
|min|44.00|
|25%|99.00|
|50%|117.00|
|75%|141.00|
|max|199.00|

## Replacing missing values

`clinical_study.isnull().sum()`

|column|# of missing values|
|------|-------------------|
|subject_id|0|
|age|0|
|sex|0|
|weight|11|
|height|0|
|trt_grp|0|
|RESPONSE|0|

`protein_levels.isnull().sum()`

|column|# of missing values|
|------|-------------------|
|participant_id|0|
|protein_concentration|5|

The two columnms with missing values are *weight* and *protein_concentration* There are many ways to deal with missing values. For example depending on the data and task, we could drop the rows with missing values or replace the missing values with the mean, median, mode, or even a constant value . We can use a box plot or density plot to help decide what method to follow

![image](https://github.com/Daniel-ET/clinical_trial/assets/96924468/07944ea7-eb7b-42e6-8e8c-3443a2f731c9)
![image](https://github.com/Daniel-ET/clinical_trial/assets/96924468/cd4aa035-cdb9-4819-b0d3-19e7b5b1ff48)

As we can see, the data for age and protein is slighly skewed. Therefore it would be better to use the median to replace the missing values

```clinical_study = clinical_study.fillna(clinical_study.median())```

```protein_levels = protein_levels.fillna(protein_levels.median())```









