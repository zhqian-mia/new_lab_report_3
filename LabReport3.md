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
This command allow users to search for the word `UCSD` recursively in all files and directories under biomed/*. Both files name and the lines which contain the word `UCSD` are printed out.

The second example is `grep -r "Toronto" government/`
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -r "Toronto" government/
government//About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:beautiful city of Toronto to talk with you about the subject that
government//Gen_Account_Office/pe1019.txt:Educational Research Association meeting, Toronto, Canada, April
```
This command allow users to search for the word `Toronto` recursively in all files and directories under `government/`. Both files name and the lines which contain the word `Toronto` are printed out.
  
Now let's try the second command `grep -l "pattern" /path/to/directory/*`. My first example is `grep -l "UCSD" biomed/*`
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -l "UCSD" biomed/*
biomed/1471-2091-3-30.txt
biomed/1471-2407-2-15.txt
biomed/1471-244X-3-5.txt
biomed/1472-6823-2-2.txt
biomed/1476-4598-2-2.txt
biomed/bcr620.txt
```
Compare to the first example of the first command, now the output show in the terminal only shows unique file names. To be more specific, the terminal print out all the file under biomed directory that contain the word `UCSD`.   

My second example is `grep -l "Alcohol" biomed/* `.
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -l "Alcohol" biomed/*                                                                            
biomed/1471-213X-3-4.txt
biomed/1471-2156-3-22.txt
biomed/1471-2210-1-2.txt
biomed/1471-2334-3-11.txt
biomed/1471-2458-2-6.txt
biomed/1471-2466-2-3.txt
biomed/1478-7954-1-3.txt
biomed/bcr605.txt
biomed/gb-2001-2-7-research0025.txt
```
As the above, this command find all the unique files' name who contain the word "Alcohol" under the `biomed` directory. 
