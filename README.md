### Plink
#### Plink in Rstudio

1. Downlaod Plink source file from here [https://zzz.bwh.harvard.edu/plink/download.shtml]
2. Create a folder and set it as working directory then copy downloaded file to this directory/ any files that you want use in the analysis must be copied in the directory
3. You must use system() to run Plink command in Rstudio
   
``` {r}
   # Set directory
   setwd("C:/Users/arsangjang/Desktop/plink")

   # Check the plink in your system // you should get plink version
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

#### Find and remove duplicated samples in .bed file // Check folder for results (plink.dupvar) // then save .dupvar as txt format (Exm: Duplicate.txt)
**Change the HM_CEU_REF according to your file name*
```{r}
system("plink --bfile HM_CEU_REF --list-duplicate-vars")

system("plink --bfile HM_CEU_REF --list-duplicate-vars suppress-first")

system("plink --bfile HM_CEU_REF --list-duplicate-vars suppress-first --exclude Duplicate.txt --make-bed --out HM_CEU_REF_no_duplicate")
```
#### Convert VCF/vcf.gz/vcf.gz.tbi (or Ped) file to bed file (plink format) 
```{r}
system("plink --vcf yuor_vcf_data.vcf.gz --make-bed --out output_data")
```
#### unzip tar.bz2 file
```{r}
system("bunzip -c your_file.tar.bz2 | tar xvf -")
```
#### Run plink in HPC cluster 
```
# Set directory in HPC
(base) [sarsangjang@ln03 ~]$ cd /home/arsangjang/plink

# Check the plink and its version in the cluster
(base) [sarsangjang@ln03 plink]$ module spider plink

# load plink module/ packge
(base) [sarsangjang@ln03 plink]$ module load plink/2.0.0
```
   
   
