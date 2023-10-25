### Plink
Plink in Rstudio/ or HPC cluster envirenment

1. Downlaod Plink source file from here [https://zzz.bwh.harvard.edu/plink/download.shtml]
2. Create a folder and set it as working directory then copy downloaded file to this directory/ any files that you want use in the analysis must be copied in the directory
3. You must use system() to run Plink command in Rstudio
   
``` {r}
   # Set directory
   setwd("C:/Users/arsangjang/Desktop/plink")
   # Check the plink in your system // you sould get plink version
   system("plink")
   ```
##### Read the bed files // your bed files (HM_CEU_REF) must be in the directory folder
```{r}
   system("plink --bfile HM_CEU_REF")
```
##### Frequency of HM_CEU_REF data and save the results in text file (HM_CEU_REF_frequency)
```{r}
   system("plink --file HM_CEU_REF --freq --out HM_CEU_REF_frequency")
```
   
   
