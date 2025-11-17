# sas_dataset_toon
This package contains SAS macros for converting between SAS datasets and  TOON (Token-Oriented Object Notation) format.

### This repository is an adapted version of Saikrishnareddy Yengannagari’s original package (https://github.com/kusy2009/sas_dataset_toon) tailored for the SAS Package Framework, and the original license remains the property of Saikrishnareddy Yengannagari.　　

<img width="360" height="360" alt="Image" src="https://github.com/user-attachments/assets/f2818d5e-84fe-4c1c-8f6e-809311f279ed" />

## CONTENTS

06_macro/  
  - sas2toon.sas        		Main macro to convert SAS dataset to TOON format  
  - toon2sas.sas        		Main macro to convert TOON file to SAS dataset  

07 tests/  
  - test_sas2toon.sas   		Test suite for SAS to TOON conversion  
  - test_toon2sas.sas   		Test suite for TOON to SAS conversion  

TOON_format_specification.txt    	TOON format specification   
   
## QUICK START
/* 1. Convert SAS dataset to TOON */  
~~~sas
%sas2toon(
    libname=WORK,
    dataset=MYDATASET,
    outfile=/path/to/output.toon
);
~~~
/* 2. Convert TOON back to SAS */  
~~~sas
%toon2sas(
    infile=/path/to/input.toon,
    libname=WORK,
    dataset=NEWDATA
);
~~~
## REQUIREMENTS

- SAS 9.4 or later  
- BASE SAS license  
- File system access for reading/writing TOON files  

## SUPPORT
For issues or questions about TOON, refer to the TOON format specification documentation.  
For SAS macros issues or questions, Please raise your issues directly here.  
