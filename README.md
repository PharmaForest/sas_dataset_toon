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
<img width="499" height="68" alt="image" src="https://github.com/user-attachments/assets/3a8f7359-f995-4708-b8f2-5adf3e7bf3b6" />  

▽  

▽  

▽  
<img width="369" height="352" alt="image" src="https://github.com/user-attachments/assets/35eafa38-2459-4973-a658-ccf44d237214" />






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
[TOON_format_Specification.txt](https://github.com/PharmaForest/sas_dataset_toon/blob/4e03654fbc406a2167c5cb03c3e31b1dfee8ccbb/TOON_format_Specification.txt)

For SAS macros issues or questions, Please raise your issues directly here.  

# version history
1.0.0(15Nov2025): Initial version

## What is SAS Packages?  
The package is built on top of **SAS Packages framework(SPF)** developed by Bartosz Jablonski.
For more information about SAS Packages framework, see [SAS_PACKAGES](https://github.com/yabwon/SAS_PACKAGES).  
You can also find more SAS Packages(SASPACs) in [SASPAC](https://github.com/SASPAC).

## How to use SAS Packages? (quick start)
### 1. Set-up SPF(SAS Packages Framework)
Firstly, create directory for your packages and assign a fileref to it.
~~~sas      
filename packages "\path\to\your\packages";
~~~
Secondly, enable the SAS Packages Framework.  
(If you don't have SAS Packages Framework installed, follow the instruction in [SPF documentation](https://github.com/yabwon/SAS_PACKAGES/tree/main/SPF/Documentation) to install SAS Packages Framework.)  
~~~sas      
%include packages(SPFinit.sas)
~~~  
### 2. Install SAS package  
Install SAS package you want to use using %installPackage() in SPFinit.sas.
~~~sas      
%installPackage(packagename, sourcePath=\github\path\for\packagename)
~~~
(e.g. %installPackage(ABC, sourcePath=https://github.com/XXXXX/ABC/raw/main/)) 
