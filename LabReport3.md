#Lab Report 3  
  
Today we will look at four interesting commands of `grep`.  
* `grep -r "pattern" /path/to/directory`
* `grep -l "pattern" /path/to/directory/*`
* `grep -w "pattern" /path/to/file`
* `grep -v "pattern" /path/to/file`  
  
Each commands will be offer two different examples to illustrate its functions.  
  
For convenience, I used `grep ".txt" find-results.txt > grep-results.txt' to put all txt files into a new file named grep-results.txt. Right now, the file grep-results.txt should have a bunch of file direcotories in it.  
  
`cd technical`. Now the pwd is `/Users/qianzhijun/Documents/GitHub/docsearch/technical`

Let's try the first command `grep -r "pattern" /path/to/directory`. My first example is `grep -r "UCSD" biomed/*` 
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -r "UCSD" biomed/*
biomed/1471-2091-3-30.txt:        Insel, UCSD) demonstrated constitutive activation of ERKs
biomed/1471-2407-2-15.txt:          UCSD Viral Vector Core. The plasmids were co-transfected
biomed/1471-2407-2-15.txt:          approved by the animal care committee at UCSD. The cells
biomed/1471-244X-3-5.txt:          UCSD Medical Center, La Jolla, during July and August of
biomed/1472-6823-2-2.txt:          respective local human IRBs (UCSD, La Jolla, CA; Veterans
biomed/1476-4598-2-2.txt:          Ludwig Institute of Cancer Research at UCSD. The tumor
biomed/bcr620.txt:          UCSD Medical Center. Samples were obtained in random
biomed/bcr620.txt:          approval of the UCSD Institutional Review Board for
```
This command allow users to search for the word `UCSD` recursively in all files and directories under biomed/*.  

The second example is `grep -r "Toronto" government/`
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -r "Toronto" government/
government//About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:beautiful city of Toronto to talk with you about the subject that
government//Gen_Account_Office/pe1019.txt:Educational Research Association meeting, Toronto, Canada, April
```
This command allow users to search for the word `Toronto` recursively in all files and directories under `government/`.
