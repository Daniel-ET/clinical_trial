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

```clinical_study.info()```

|#|Column|Non-Null Count|Dtype|
|-|------|--------------|-----|
|0|subject_id|772 non-null|object|


