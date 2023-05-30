# clinical_trial

Example of analysing data from a clinical trial using synthetic data.

## The data

**clinical_study.csv**

|COLUMNS|DESCRIPTION|
|-------|-----------|
|subject_id|Patient ID|
|sex|Whether the patient is male or female|
|age|The age of the patient|
|weight|The weight of the patient|
|height|The height of the patient|
|trt_grp|Whether patient is in drug or control group|
|response|Whether the patient responsed|

first few rows

|subject_id|age|sex|weight|height|trt_grp|RESPONSE|
|SUBJ_001|46.0|Female|84.66|1.59|DRUG|N|
|SUBJ_002|47.0|Female|71.21|1.64|DRUG|N|
|SUBJ_003|48.0|Female|69.85|1.73|CONTROL|N|
|SUBJ_004|59.0|Female|62.94|1.50|DRUG|Y|
|SUBJ_005|59.0|Female|113.91|1.63|CONTROL|N|
|SUBJ_006|63.0|Male|79.33|1.77|CONTROL|Y|
|SUBJ_007|77.0|Male|96.12|1.77|CONTROL|N|
|SUBJ_008|57.0|Male|93.50|1.63|DRUG|N|
|SUBJ_009|72.0|Male|85.57|1.68|DRUG|N|

