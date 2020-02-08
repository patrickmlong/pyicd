# pyicd (WIP)
A python package for ICD analysis.


## Functionality
<b>Convert between ICD-9-CM and ICD-10-CM using General Equivalency Map (GEMs)</b>
- Forward and backward ICD mapping
- Map by GEMs cross-walk flag type

<b>Lexical ICD-9-CM and ICD-10-CM querying</b>
- Search ICD9 or ICD10 codes by clinical keyword 
- Query ICD codes by Word2Vec imbeddings

## Examples
<b>GEMS mapping</b>

<i>Forward mapping (from ICD-9-CM to ICD-10-CM)</i>

```python
from pyicd.utils.icd_tools import icd9_to_icd10

icd9_to_icd10(icd_code = "59972", flag = "approximate")

source  icd10                                description
59972   R311     BENIGN ESSENTIAL MICROSCOPIC HEMATURIA
59972  R3121         ASYMPTOMATIC MICROSCOPIC HEMATURIA
59972  R3129                OTHER MICROSCOPIC HEMATURIA
``` 


<i>Backward mapping (from ICD-10-CM to ICD-9-CM)</i>

```python
from pyicd.utils.icd_tools import icd10_to_icd9

icd10_to_icd9(icd_code = "R6521", show_flags = True)

source   icd9    description  approximate  no map  combination    scenario  choice list  
R6521  99592  SEVERE SEPSIS            1       0            1           1            2  
R6521  78552   SEPTIC SHOCK            1       0            1           1            1          
```


<b>Search by clinical term</b>
  
 ```python
from pyicd.utils.icd_tools import search_icd10

search_icd10(search_term = "fibrillation")

source  icd10                        description
42731  I4891    UNSPECIFIED ATRIAL FIBRILLATION
42741  I4901           VENTRICULAR FIBRILLATION

```





## Notice of Non-Affiliation and Disclaimer 
The author of this library is not affiliated, associated, authorized, endorsed by, or in any way officially connected with CMS, or any of its subsidiaries or its affiliates.

