## Lab Report 3  ##
  
Today we will look at four interesting commands of `grep`.  
* `grep -r "pattern" /path/to/directory`
* `grep -l "pattern" /path/to/directory/*`
* `grep -w "pattern" /path/to/file`
* `grep -v "pattern" /path/to/file`  
**All the sources above comes from this [link](https://chat.openai.com/)**
  
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
  
Now let's try the second command `grep -l "pattern" /path/to/directory/*`. My first example is `grep -l "UCS" biomed/*`
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -r "UCS" biomed/*
biomed/1471-2091-3-30.txt:        Insel, UCSD) demonstrated constitutive activation of ERKs
biomed/1471-2121-3-12.txt:          (UCSF). In this plasmid, mouse α 
biomed/1471-2121-3-12.txt:          Morales (UCSF). EE-tagged α 
biomed/1471-2407-2-15.txt:          UCSD Viral Vector Core. The plasmids were co-transfected
biomed/1471-2407-2-15.txt:          approved by the animal care committee at UCSD. The cells
biomed/1471-244X-3-5.txt:          UCSD Medical Center, La Jolla, during July and August of
biomed/1472-6823-2-2.txt:          respective local human IRBs (UCSD, La Jolla, CA; Veterans
biomed/1476-4598-2-2.txt:          Ludwig Institute of Cancer Research at UCSD. The tumor
biomed/1478-1336-1-4.txt:          Biomolecular Resource Center at UCSF.
biomed/1478-1336-1-4.txt:          Center, UCSF) containing EcoRI and SalI sites, the PCR
biomed/bcr620.txt:          UCSD Medical Center. Samples were obtained in random
biomed/bcr620.txt:          approval of the UCSD Institutional Review Board for
biomed/gb-2001-2-7-research0025.txt:          Ensembl or UCSC [ 85] maps. The resulting contigs were
biomed/gb-2001-2-7-research0025.txt:          orientation information in the UCSC genome assembly,
biomed/gb-2001-2-7-research0025.txt:          (> 50 kb) available from the UCSC assembly was
biomed/gb-2002-3-12-research0081.txt:        examples are the University of California Santa Cruz (UCSC)
biomed/gb-2003-4-2-r16.txt:          (UCSC) genome browser [ 21]. Figure 3ashows how these
biomed/gb-2003-4-2-r16.txt:          locus on chromosome 12 using the UCSC genome browser
biomed/gb-2003-4-2-r16.txt:          the UCSC genome browser (data not shown). TC575977 and
biomed/gb-2003-4-8-r50.txt:        from the University of California at Santa Cruz (UCSC)
biomed/gb-2003-4-8-r50.txt:        UCSC Genome Browser [ 14 16 ] . The first is derived from
biomed/gb-2003-4-8-r50.txt:          UCSC Genome Browser, August 2001 assembly, displays
biomed/gb-2003-4-8-r50.txt:          available through the UCSC Genome Browser [ 14 15 16 ]
```
Compare to the first example of the first command, now the output show in the terminal only shows unique file names. To be more specific, the terminal print out all the file under biomed directory that contain the word `UCS`. It could be `UCSD` or `UCSC`.    

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
  
Now, let's move to the third command choice `grep -w "pattern" /path/to/file`
