# Lab Report 3: Researching Commands

In this report, we will research the grep command further. 

## Grep Command
When I asked ChatGBT `What are some grep command line options?` it returned

![Image](Screen Shot 2023-05-09 at 2.06.52 PM.png)

## -w Command
The -w command makes it so that only whole words are matched. 
```
christydeliivanov@christys-air-2 911report % grep -w "we" preface.txt
the United States. The nation was unprepared. How did this happen, and how can we
                areas determined relevant by the Commission. In pursuing our mandate, we have
                From the outset, we have been committed to share as much of our investigation as we
                can with the American people. To that end, we held 19 days of hearings and took
            At the outset of our work, we said we were looking backward in order to look forward.
                positive-an America that is safer, stronger, and wiser. That September day, we came
            As we complete our final report, we want to begin by thanking our fellow
                of several previous Commissions, and we thank the Congressional Joint Inquiry, whose
                the importance of the work we have undertaken.
            We want to note what we have done, and not done. We have endeavored to provide the
                most complete account we can of the events of September 11, what happened and why.
                This final report is only a summary of what we have done, citing only a fraction of
                the sources we have consulted. But in an event of this scale, touching so many
                issues and organizations, we are conscious of our limits. We have not interviewed
                number of them. We decided consciously to focus on recommendations we believe to be
                pause, reflect, and sometimes change our minds as we studied these problems and
``` 
We specify that the grep command is of the -w type and specify that we are searching for the word 'we' in the file preface.txt.
This command will only return lines with the word 'we' inside the preface.txt file and will not include any words that may contain we. 

```
christydeliivanov@christys-air-2 technical % grep -w "glioblastoma" biomed/*.txt
biomed/1471-2199-2-2.txt:        such as glioblastoma and carcinomas of the prostate,
biomed/1471-2199-3-11.txt:        PTEN gene into anchorage-independent human glioblastoma
biomed/1471-2199-3-11.txt:          U87 glioblastoma tumor cell line has been described [ 57
biomed/1471-2407-2-15.txt:        glioblastoma, melanoma, ovarian carcinoma, prostatic
biomed/1471-2407-2-15.txt:          Receptor inhibits growth of U87 glioblastoma cells
biomed/1471-2407-2-8.txt:        promoter activity in human glioblastoma and transformed
biomed/1476-4598-2-1.txt:          including glioma and glioblastoma, pancreatic and colonic
biomed/gb-2002-3-9-research0051.txt:          cell cultures [ 32]. In glioblastoma cells (and
biomed/gb-2003-4-7-r46.txt:        from human brain glioblastoma. Our study examined the
biomed/gb-2003-4-7-r46.txt:          U118 brain glioblastoma cell line were cultured at 37°C
```
We specify that the grep command is of the -w type and specify that we are searching for the word "glioblastoma" in files any of the biomed. Here it returns the file and line the word is found in.  

## -n Command
The -n command prints the line number of each line that contains the searched word.

```
christydeliivanov@christys-air-2 technical % grep -n "glioblastoma" biomed/*.txt
biomed/1471-2199-2-2.txt:79:        such as glioblastoma and carcinomas of the prostate,
biomed/1471-2199-3-11.txt:52:        PTEN gene into anchorage-independent human glioblastoma
biomed/1471-2199-3-11.txt:350:          U87 glioblastoma tumor cell line has been described [ 57
biomed/1471-2407-2-15.txt:93:        glioblastoma, melanoma, ovarian carcinoma, prostatic
biomed/1471-2407-2-15.txt:371:          Receptor inhibits growth of U87 glioblastoma cells
biomed/1471-2407-2-8.txt:39:        promoter activity in human glioblastoma and transformed
biomed/1476-4598-2-1.txt:270:          including glioma and glioblastoma, pancreatic and colonic
biomed/bcr294.txt:14:          carcinomas, glioblastomas and invasive breast carcinomas
biomed/bcr294.txt:158:          glioblastomas and a small series (14) of invasive breast
biomed/bcr294.txt:201:            carcinomas and glioblastomas [ 1, 2]. Forward primers
biomed/gb-2002-3-9-research0051.txt:331:          cell cultures [ 32]. In glioblastoma cells (and
biomed/gb-2003-4-7-r46.txt:30:        from human brain glioblastoma. Our study examined the
biomed/gb-2003-4-7-r46.txt:148:          glioblastomas and astrocytomas, generated from previous
biomed/gb-2003-4-7-r46.txt:166:          were also higher in high-grade glioblastomas over U118
biomed/gb-2003-4-7-r46.txt:439:          U118 brain glioblastoma cell line were cultured at 37°C
```
We specify that the grep command is of the -n type and specify that we are searching for the word "glioblastoma" in any of the biomed files. Here it returns the file, line number, and the line that contains it. Compared to the -w search we actually see more lines becuase now -w is also returning lines that have words that contain 'glioblastoma' (ex. glioblastomas). 

```
christydeliivanov@Christys-MacBook-Air-2 911report % grep -n "we" preface.txt
12:                the United States. The nation was unprepared. How did this happen, and how can we
14:            To answer these questions, the Congress and the President created the National
17:            Our mandate was sweeping. The law directed us to investigate "facts and circumstances
22:                areas determined relevant by the Commission. In pursuing our mandate, we have
23:                reviewed more than 2.5 million pages of documents and interviewed more than 1,200
27:                From the outset, we have been committed to share as much of our investigation as we
28:                can with the American people. To that end, we held 19 days of hearings and took
37:                and equal rights for women. It makes no distinction between military and civilian
42:                fault lines within our government-between foreign and domestic intelligence, and
43:                between and within agencies. We learned of the pervasive problems of managing and
46:            At the outset of our work, we said we were looking backward in order to look forward.
48:                positive-an America that is safer, stronger, and wiser. That September day, we came
51:                the long haul, to attack terrorists and prevent their ranks from swelling while at
54:                agencies that prevailed in the great struggles of the twentieth century must work
55:                together in new ways, so that all the instruments of national power can be combined.
56:                Congress needs dramatic change as well to strengthen oversight and focus
58:            As we complete our final report, we want to begin by thanking our fellow
62:                of our colleagues, as well as our great affection for them.
70:                officials, past and present, who were generous with their time and provided us with
73:                assistance. We owe a huge debt to their investigative labors, painstaking attention
75:                of several previous Commissions, and we thank the Congressional Joint Inquiry, whose
82:                the importance of the work we have undertaken.
83:            We want to note what we have done, and not done. We have endeavored to provide the
84:                most complete account we can of the events of September 11, what happened and why.
85:                This final report is only a summary of what we have done, citing only a fraction of
86:                the sources we have consulted. But in an event of this scale, touching so many
87:                issues and organizations, we are conscious of our limits. We have not interviewed
99:                number of them. We decided consciously to focus on recommendations we believe to be
102:                pause, reflect, and sometimes change our minds as we studied these problems and
```
Here we specify that the grep command is of type n and searching for the word 'we' in the preface.txt. It returns all the lines that contain the word we within the preface.txt file. 

## -c Command
The -c command prints the number of lines that contain the greped word. 

```
christydeliivanov@Christys-MacBook-Air-2 911report % grep -c "we" preface.txt
29
```
Here the grep command is searching for the word 'we' in the preface.txt file as we did before. However, this time the count of lines that contain 'we' is printed. 

```
christydeliivanov@Christys-MacBook-Air-2 technical % grep -c "cancer" plos/*.txt
plos/journal.pbio.0020001.txt:0
plos/journal.pbio.0020010.txt:0
plos/journal.pbio.0020012.txt:0
plos/journal.pbio.0020013.txt:1
plos/journal.pbio.0020019.txt:0
plos/journal.pbio.0020028.txt:5
plos/journal.pbio.0020035.txt:2
plos/journal.pbio.0020040.txt:9
plos/journal.pbio.0020042.txt:0
plos/journal.pbio.0020043.txt:0
plos/journal.pbio.0020046.txt:0
plos/journal.pbio.0020047.txt:0
plos/journal.pbio.0020052.txt:1
plos/journal.pbio.0020053.txt:2
plos/journal.pbio.0020054.txt:0
plos/journal.pbio.0020063.txt:1
plos/journal.pbio.0020064.txt:0
plos/journal.pbio.0020067.txt:0
plos/journal.pbio.0020068.txt:0
plos/journal.pbio.0020071.txt:1
plos/journal.pbio.0020073.txt:0
plos/journal.pbio.0020100.txt:0
plos/journal.pbio.0020101.txt:0
plos/journal.pbio.0020105.txt:0
plos/journal.pbio.0020112.txt:1
plos/journal.pbio.0020113.txt:1
...
```
Here we used the -c command within the plos directory to see which files talk about cancer. Here we searched for the word cancer in all the txt files in plos and a count was returned for each file.

