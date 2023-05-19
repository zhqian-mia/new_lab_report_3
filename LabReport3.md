# Lab Report 3  #
***
  
Today we will look at four interesting commands of `grep`.  
* `grep -r "pattern" /path/to/directory`
* `grep -l "pattern" /path/to/directory/*`
* `grep -w "pattern" /path/to/directory/*`
* `grep -v "pattern" /path/to/directory/*`  
  
**All the sources above comes from chatGPT, below is the prompt and respond.**  
  
![Image](https://github.com/zhqian-mia/new_lab_report_3/blob/main/chatGPT%20grep%20respond.png?raw=true)

***
  
Each commands will be offer two different examples to illustrate its functions.  
  
For convenience, I used `grep ".txt" find-results.txt > grep-results.txt' to put all txt files into a new file named grep-results.txt. Right now, the file grep-results.txt should have a bunch of file direcotories in it.  
  
Enter `cd technical` in my terminal. Now the pwd is `/Users/qianzhijun/Documents/GitHub/docsearch/technical`


## Let's try the first command `grep -r "pattern" /path/to/directory`.  
* My first example is `grep -r "UCS" biomed/*`    
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
**This command allow users to search for the three continuous letters `UCS` recursively in all files and directories under `biomed/*`. Both files name and the lines which contain the three letters `UCS` are printed out, which means it could be `UCSD` or `UCSC`. `-r` only show the files name and lines that contain the pattern, but not in whole word.**

* My second example is `grep -r "Toronto" government/`  
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -r "Toronto" government/
government//About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:beautiful city of Toronto to talk with you about the subject that
government//Gen_Account_Office/pe1019.txt:Educational Research Association meeting, Toronto, Canada, April
```
**This command allow users to search for the word `Toronto` recursively in all files and directories under `government/`. Both files name and the lines which contain the 7 letters `Toronto` are printed out.**
  
## Now let's try the second command `grep -l "pattern" /path/to/directory/*`.  
* My first example is `grep -l "UCSD" biomed/*`  
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -l "UCSD" biomed/*
biomed/1471-2091-3-30.txt
biomed/1471-2407-2-15.txt
biomed/1471-244X-3-5.txt
biomed/1472-6823-2-2.txt
biomed/1476-4598-2-2.txt
biomed/bcr620.txt
```
**The output show in the terminal only shows unique file names. To be more specific, the terminal print out all the file under biomed directory that contain the word `UCSD`.**  

* My second example is `grep -l "Alcohol" biomed/* `  
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
**As the above, this command find all the unique files' name whose file inside contain the word "Alcohol" under the `biomed` directory.**  
  
## Now, let's move to the third command choice `grep -w "pattern" /path/to/directory/*`.   
* My first example is:`grep -w "UCSD" biomed/*`  
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -w "UCSD" biomed/*
biomed/1471-2091-3-30.txt:        Insel, UCSD) demonstrated constitutive activation of ERKs
biomed/1471-2407-2-15.txt:          UCSD Viral Vector Core. The plasmids were co-transfected
biomed/1471-2407-2-15.txt:          approved by the animal care committee at UCSD. The cells
biomed/1471-244X-3-5.txt:          UCSD Medical Center, La Jolla, during July and August of
biomed/1472-6823-2-2.txt:          respective local human IRBs (UCSD, La Jolla, CA; Veterans
biomed/1476-4598-2-2.txt:          Ludwig Institute of Cancer Research at UCSD. The tumor
biomed/bcr620.txt:          UCSD Medical Center. Samples were obtained in random
biomed/bcr620.txt:          approval of the UCSD Institutional Review Board for
```
**This command will search all lines in the files or directories under the `biomed/*` that has the word `UCSD`. It will print out the non-unique files name that contain the whole word `UCSD`. The difference between `-r` and `-w` is that `-r` will print out both files names and lines (files name may repeat) as long as it has the pattern, while `-w` will only print out the lines and file names (files name may repeat) that has the whole word.**  
  
## My second example is `grep -w "accident" plos/*`  
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -w "accident" plos/*
plos/journal.pbio.0020101.txt:        blood cortisol (Sapolsky 1994). An accident of history, however, selectively wiped out all
plos/journal.pbio.0020216.txt:        without accident. Furthermore, even though bees experience only a small increase in
```
**This command will print out the file names and the lines that contain the whole word `accident` under the `plos/*` directory. `-w` will print out the lines and file names that contain the pattern as a whole word.**  
  
## Now, let's move to the last command `grep -v "pattern" /path/to/directory/*`.    
* My first example is `grep -v -l "alcohol" government/Alcohol_Problems/*`.  
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -v "alcohol" government/Alcohol_Problems/*
government/Alcohol_Problems/Session4-PDF.txt:the model.
government/Alcohol_Problems/Session4-PDF.txt:Robert Woolard favored continuing intervention research in EDs.
government/Alcohol_Problems/Session4-PDF.txt:He believed that the realities of our practice settings help drive
government/Alcohol_Problems/Session4-PDF.txt:the development of new ways of delivering counseling, for example,
government/Alcohol_Problems/Session4-PDF.txt:computer-based methods. While emergency physicians may not have the
government/Alcohol_Problems/Session4-PDF.txt:time or interest, the patients do. He suggested that research in
government/Alcohol_Problems/Session4-PDF.txt:about the interventions they have already developed and can even
government/Alcohol_Problems/Session4-PDF.txt:lead to novel interventions.
```
**This command will print out all the lines in the `government/Alcohol_Problems/*` that does not contain `alcohol`. The output is too long so I only copy part of the terminal and paste it here. The `grep -v "pattern" /path/to/file` will print out all lines in the specific directories that do not contain the pattern.**  
  
* The second examples that I choose is `grep -v  "death" 911report/*`
```
qianzhijun@qianzhijundeMacBook-Pro technical % grep -v  "death" 911report/*
911report/preface.txt:            We have listened to scores of overwhelming personal tragedies and astounding acts of
911report/preface.txt:                heroism and bravery. We have examined the staggering impact of the events of 9/11 on
911report/preface.txt:                the American people and their amazing resilience and courage as they fought back. We
911report/preface.txt:                have admired their determination to do their best to prevent another tragedy while
911report/preface.txt:                preparing to respond if it becomes necessary. We emerge from this investigation with
911report/preface.txt:                enormous sympathy for the victims and their loved ones, and with enhanced respect
911report/preface.txt:                for the American people. We recognize the formidable challenges that lie ahead.
911report/preface.txt:            We also approach the task of recommendations with humility. We have made a limited
911report/preface.txt:                number of them. We decided consciously to focus on recommendations we believe to be
911report/preface.txt:                most important, whose implementation can make the greatest difference. We came into
911report/preface.txt:                this process with strong opinions about what would work. All of us have had to
911report/preface.txt:                pause, reflect, and sometimes change our minds as we studied these problems and
911report/preface.txt:                considered the views of others. We hope our report will encourage our fellow
911report/preface.txt:                citizens to study, reflect-and act.
911report/preface.txt:            Thomas H. Kean, chair
911report/preface.txt:            Lee H. Hamilton, vice chair
```
**This command will search and print out every lines under the `"death" 911report/*` directory that do not contain the word `death`. The output is really long so in here I only copy and paste part of it from the terminal. Therefore we can see that the command `grep -v "pattern" /path/to/file` will print out the lines that does not contain the pattern, and also its corresponding file name. Therefore in the terminal's output, there will be repeat filename.**  


