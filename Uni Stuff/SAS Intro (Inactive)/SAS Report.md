            

### Safalya Pal - A90555919003
### STAT329 - Lab Report
---
<br></br>
# Creating Tables

CODE:

```sas
data weight_club;
input IdNumber 1-4 Name $ 6-24 Team $ StartWeight EndWeight;
Loss = StartWeight - EndWeight;
datalines;
1023 David Shaw         red 189 165
1049 Amelia Serrano     yellow 145 124
1219 Alan Nance         red 210 192
1246 Ravi Sinha         yellow 194 177
1078 Ashley McKnight    red 127 118
;
run;
```

EXPLANATION:

- `data` keyword is used to define the table name (table names must not contain spaces)

- `input` keyword is used to define the column names.

- `IdNumber 1-4` is used to state that the characters in position `1-4` of each row would fall under the column `IdNumber` and similarly for  `Name $ 6-24`. This eliminates the need of delimiters. 

- The `$` after `Name` and `Team` indicates that values of the `Name` and `Team` columns are strings.

- `Loss = StartWeight - EndWeight` is used to defined a new colum named `Loss` derived from `StartWeight` and `EndWeight`.

- `dataline` or `cards` is used to indicate the beginning of the table.

- All command lines end with semicolons `;`.

# **Importing Excel File**

CODE:

```sas
*Command for importing excel file;

proc import datafile = "/home/u59242738/Data Files/SAS Data1.xlsx"

 out=SASOD_data1 dbms = xlsx replace;

run;

*modifing the given data file (creating variables);

Data SASOD_data1modified;

 set SASOD_data1;

 weightloss=StartWeight - EndWeight;

run;

proc print data=SASOD_data1modified;

run;
```

OUTPUT:

![[Pasted image 20211119173924.png|500]]

EXPLANATION:

-  We can add a comment line inside the SAS code starting with star ( ***** ) and ending with semi-colon ( **;** ) in the same line.

-  “ **Proc import datafile=** ” is used to import a datafile and the **position of the file** which we want to import is written next to it inside **“”**. We can get the position from **datafile properties**.

-  **Out =** we give the name to the datafile.

-  **Dbms =** for excel file we write xlsx, for csv file we write csv.

-  Then we include **replace** so that if by the same name another datafile is saved this new datafile will replace that dataset and then we use semi-colon to end this particular program.

-  Then we write **run;** to run this particular lines of codes.

-  Then for modifying this data, at first we give a datafile name with the code **data** new_name;

-  Then we call the datafile which we want to modify by the code **set** old_name.

-  In this program we had StartWeight and EndWeight columns and we want a new program by the name **weightloss** and then we will simply just put the formula/equation like **weightloss = Startweight – EndWeight.**

-  Then we put **run;** and run this particular lines of codes.

-  We can also print the data in beautiful form with this code **proc** **print data = datafile_name** which we want to see.

            
CODE:

```sas
/* importing file*/

proc import datafile="/home/u59242738/Data Files/SAS Data2.xlsx"

 out=data2

 dbms=XLSX replace;

run;

/* modifying the data*/

data data2_modified;

 set data2;

 total_NCI = (NCI_2021 + NCI_2020 + NCI_2019 + NCI_2018 + NCI_2017);

 total_NCI_2 = sum(NCI_2021, NCI_2020, NCI_2019, NCI_2018, NCI_2017);

 average_NCI = total_NCI / 5;

 average_NCI_2 = mean(NCI_2021, NCI_2020, NCI_2019, NCI_2018, NCI_2017);

run;

proc print data= data2_modified;

run;
```

OUTPUT:

![[Pasted image 20211119174054.png|500]]
![[Pasted image 20211119174104.png|500]]

EXPLANATION:

In this program the things we learnt new are pointed below:

-  In case of modifying a datafile, we can simply put the **new_variable_name = equation** like previous work or we can also use **new_variable_name = formula.**

-  Here we used

total_NCI = (NCI_2021 + NCI_2020 + NCI_2019 + NCI_2018 + NCI_2017);

which is the **equation.**

total_NCI_2 = sum(NCI_2021, NCI_2020, NCI_2019, NCI_2018, NCI_2017);

but in this case we simply put the **sum** formula

-  Also in case of finding average we used **mean** formula.

# **Infile Statement**

CODE:

```sas
/*reading data separated by blank*/

data sdata_blank;

 infile "/home/u59242738/Data Files/DATA_blanks.txt";

 input Names $ Gender $ Age Weight;

run;

proc print data=sdata_blank;

run;

/*reading Data separated by comma(csv file)*/

Data sdata_commas;

 infile "/home/u59242738/Data Files/DATA_commas.csv" dsd;

 input Names $ Gender $ Age Weight;

run;

proc print data=sdata_commas;

run;

/*reading data separated by other deliminators like colon in this case*/

data sdata_otherdel;

 infile "/home/u59242738/Data Files/other_del_data.txt" dlm= ":";

 input Names $ Gender $ Age Weight;

run;

proc print data= sdata_otherdel;

run;
```

OUTPUT:

![[Pasted image 20211119174253.png|200]]

EXPLANATION:

-  At first, we give the datafile name we want to give the data for this particular notebook as **data** name.

-  Next, we write **infile “datafile location”** to import the datafile.

-  In case of this datafiles imported here the variables names were not defined in the text/csv files. So, we used **input** and wrote the variable names one by one.

-  In case of character type variables we have to use $ sign after the variable name to define it as character type and in case of numeric values we don’t have to put any sign after the variable names.

-  After that, when we imported the same datafile from a csv file instead of a text file we had to include **dsd** after the infile “location” statement. This dsd specifies that when data values are enclosed in quotation marks, delimiters within the value and are treated as character data. The DSD option changes how SAS treats delimiters when you use LIST input and sets the default delimiter to a comma. When we specify DSD, SAS treats two consecutive delimiters as a missing value and removes quotation marks from character values.

-  In case of importing a text file where the values are separated with any delimiters like semi-colon, comma, colon, or any others then we simply have to define the delimiter like **dlm = “ : ”** after the infile “location” statement.

            

# **Importing Text Files with Header**

CODES:

```sas
/*import txt file with data infile statement(blank delimiter), first row as header*/

data bank_full_blank;

 infile "/home/u59242738/Data Files/Bank_full_Blank.txt" firstobs= 2

 delimiter= " ";

 input age job $ marital $ education $ default $ balance housing $ loan $ contact $ day month $ duration campaign pdays previous poutcome $ y $;

run;

/*import txt file with proc import (blank delimiter) first row as header*/

proc import datafile="/home/u59242738/Data Files/Bank_full_Blank.txt"

 out=data_full_blank_2_sasdata dbms=dlm replace;

 delimiter=" ";

 getnames=yes; /*including first line as heading in the data*/ 

run;
```
OUTPUT:

![[Pasted image 20211119174429.png|500]]
![[Pasted image 20211119174436.png|500]]

EXPLANATION:

-  In case of comment lines inside the codes we can also use **/* comment */** .

-  In case of **infile** statement we have to define the names of the variables ourselves and as the first row is our header in the datafile, so we have to define **firstobs = 2** so that the sas environment takes the values of the variables from the second row ignoring the first row.

-  As there is no delimiter used, we will simply define **delimiter = “ ”** putting a blank inside the quotations.

-  Then we will have to manually put the variable names in the input statement.

-  In case of importing the same file by proc print statement, we will just simply put a code **getnames = yes;** and the sas environment will understand and take that first line as heading or simply variable names.

            

# **Various Datafiles**

CODE:

```sas
/* Reading datafiles in different format using informat statement

SAS has different formats but we'll work with only two kinds

i. standard numeric which is in the format w.d

ii. character value which is in the format $w.

eg, in w.d format, 145 kg is 3. format and 2.1 is 3.1 format*/

data sdata_column;

 infile "/home/u59242738/Data Files/DATA_column.txt";

 input

 @1 Name $5.

 @6 Gender $1.

 @7 Weight 3.

 @10 DOB mmddyy10.;

run;

/* 1 Jan 1960 = 1, 2 Jan 1960 = 2 and so on for date format*/

/* display DDMonth YYYY format */

proc print data= sdata_column;

format DOB date9.;

run;

/* display MM/DD/YYYY format */

proc print data= sdata_column;

format DOB mmddyy10.;

run;
```

OUTPUT:

![[Pasted image 20211119174537.png|200]]

EXPLANATION:

-  During importing a file through infile statement from a text file, if there is no blanks or space or delimiters or the space between one value from the next one is not equal but the variable values are are in same space length then we can read the datafile in **informat statement.**

For eg, if 1-5 available space uses for Name variable and 6th space is available for gender, 7th-9th space takes weight and from 10th till end it takes dob then we can define them just by using **@1 variable_name $5.** This @1 define that this particular variable will take value from 1st place and $sign will define that it is a character variable and this 5. Will define that it will take 5 places from 1 till 5.

-  **Similarly @6 Gender $1.** Will define that Gender variable will start taking values from 6th space till only 1 space from that which means only 6th space and it will be a character type variable.

-  **Date** has many formats in SAS environment.

Normally if we don’t define any format it will take 1st January 1960 as 1, 2nd January 1960 as 2 and so on for date format.

But, we can change it according to our needs.

Like, here we used 2 formats.

i) **Format DOB date9.** which will show us the date as 01JAN1960 or 11NOV2021 like that.

**ii)** **Format DOB mmddyy10.** which will show us the date as 01/01/1960 or 11/11/2021 like that.

            

# **Importing Multiple Excel Sheets**

CODE:
```sas
/* Importing different sheet other than the first one from Excel to Sas*/

proc import datafile= "/home/u59242738/Data Files/excel_data.xlsx"

out= dataset1 dbms= XLSX replace;

sheet= "name_class";

run;

/* Importing some selected ranges of a sheet from Excel to SAS*/

proc import datafile= "/home/u59242738/Data Files/excel_data.xlsx"

out= dataset1 dbms= XLSX replace;

sheet= "name_class";

range= "A1:B8";

run;

proc print data= dataset1;

run;

/* by using noobs we are ignoring the obs no column*/

proc print data= dataset1 noobs;

run;
```

OUTPUT:

![[Pasted image 20211119174801.png|200]]

EXPLANATION:

-  Here, we imported the datafile by the same process and just added an extra code line which is

**Sheet= “name_class”;**

By this way, no matter how many sheets are there in that particular excel file, only the sheet named as name_class will be imported.

-  Similarly, if we want to take only some particular values/observations from a particular sheet of the excel file we will simply define the range we want to take like

**Range= “A1:B8”** like that.

-  No matter the dataset, sas environment always put observation number by default in the imported dataset. If we want to ignore that observation number column from our output we will add a command **noobs** after the proc print data= dataset_name. That way, when we print our results at the end, the observation number column is not printed.

            

# **CREATE A DATAFILE**

CODE:
```sas
/* Create datafile*/

libname scores "/home/u59242808";

/* Permanent Data File*/

data scores.student_math;

input stu_names $ math_score;

datalines;

Speedy 90

Tim 91

Shawn 100

Mike 60

;

run;

proc print data= scores.student_math;

run;

/*Temporary data file (data go away the next time i login)*/

data student_math2;

input stu_names $ math_score;

datalines;

Speedy 90

Tim 91

Shawn 100

Mike 60

;

run;

proc print data = student_math2;

run;
```

OUTPUT:

![[Pasted image 20211119174859.png|200]]

EXPLANATION:

-  We can create a datafile by ourselves in SAS environment as well

i) Permanent datafile

ii) Temporary datafile.

-  In case of creating a permanent datafile we will have to save the datafile in a library.

Here, I saved it in my **scores** library by and saved the datafile as **student_math** by using the code data scores.student_math.

-  Then, I have to put the variable names as input

-  Then, by defining datalines, we will just simply put the values and observations.

-  In case of a temporary datafile, we don’t have to define any library name and we can simply just start by defining data dataset name as **data student_math2** and then put the input variable names and observations.

            

# **SAS function**

CODE:
```sas
proc import datafile= "/home/u59242738/Data Files/score_data.xlsx"

out= score_data1 dbms= XLSX replace;

run;

/* converting Gender variable from small to upper letter

another function is used to find out the length of name variable observations*/

data score_data_new;

set score_data1;

gender_func = upcase(gender);

length_name = length(name);

run;

proc print data= score_data_new;

run;
```

OUTPUT:

![[Pasted image 20211119174942.png|500]]

EXPLANATION:

-  At first we imported the data.

-  Then we saw that the gender variable was in lowercase we want the uppercase values and we also need the length of the names.

-  So, we created a new variable as **gender_func** and used the upcase statement to convert the alphabets present in the gender to uppercase using the statement

**Gender_func = upcase(gender);**

-  We also used length statement to find out the length of the name observations in our data and put the output in a new variable by the name length_name like

**Length_name = length(name);**
           
# **IF-THEN STATEMENT**

CODE:
```sas
/* using if-then statement*/

data score_data1_ifthen;

set score_data1;

if gender = "m" then gender_num = 1;

else gender_num = 2;

run;

proc print data= score_data1_ifthen;

run;
```

OUTPUT:

![[Pasted image 20211119175029.png|500]]

EXPLANATION:

-  We used the previous dataset here and that’s why we didn’t have to import the datafile again here.

-  Here we want to convert the gender m-f values to binary form.

So, we used if then statement here and made a new variable as gender_num which will give us value 1 if gender is mail and 2 if gender is female.

-  By using if then statement we wrote here if gender = “m” then gender_num = 1 else gender_num=2 and then printed the output.

            

# **IF ELSE THEN STATEMENT**

CODE:
```sas
proc import datafile= "/home/u59242738/Data Files/score_data_miss.xlsx"

out= score_data_miss dbms= xlsx replace;

run;

data score_data_miss_cond;

set score_data_miss;

if gender = "m" then gender_num = 1;

else if gender = "f" then gender_num = 2;

else gender_num = .;

avg_marks = mean(score1, score2, score3);

run;

proc print data= score_data_miss_cond;

run;

data score_data_miss_cond2;

set score_data_miss_cond;

length take $12;

if avg_marks >= 90 then do

 grade = "A";

 result = "Pass";

 end;

else if avg_marks >= 80 then do

 grade = "B";

 result = "Pass";

 end;

else if avg_marks >= 70 then do

 grade = "C";

 result = "Pass";

 end;

else if avg_marks >= 60 then do

 grade = "D";

 result = "Pass";

 end;

else if 0 <= avg_marks < 60 then do

 grade = "F";

 result = "Fail";

 end;

else do

 grade = ".";

 result = ".";

 end;

/* create two variables i) complete when all the marks are given and ii) pass if the average score is >= 60*/

if score1 ~=. and score2 ~=. and score3 ~=. then take = "Complete";

else take = "Incomplete";

run;

proc print data= score_data_miss_cond2;

run;

/* Divide the file into two parts using if statement where part 1= who complete the assignment and 2= incomplete*/

data subset_1;

set score_data_miss_cond2;

if take = "Complete";

run;

data subset_2;

set score_data_miss_cond2;

if take = "Incomplete";

run;

proc print data= subset_1;

proc print data= subset_2;

run;

/* Divide the file into two parts using delete statement where part 1= who complete the assignment and 2= incomplete*/

data subset_3;

set score_data_miss_cond2;

if take = "Incomplete" then delete;

run;

data subset_4;

set score_data_miss_cond2;

if take = "Complete" then delete;

run;

proc print data = subset_3;

proc print data = subset_4;

run;
```

OUTPUT:

![[Pasted image 20211119175419.png|500]]

![[Pasted image 20211119175425.png|500]]

![[Pasted image 20211119175435.png|500]]

![[Pasted image 20211119175442.png|500]]

EXPLANATION:

-  Here, at first we imported the datafile which is the first output.

-  Then, we used if then statement to convert gender to binary in a new variable **gender_num** and made another variable avg_marks which implies the average of score1, score2, score3 and printed the first output.

-  Then, we made 3 new variables take, grade and result.

We take the length of take variable as 12 as by default it takes only 8 length.

We defined if avg_marks >= 90 then grade will show A and result will show pass

If avg_marks >= 80 then grade will show B and result will show pass and so on.

If avg_marks lies between 0 to 60 then grade will show F and result will show Fail and at last, when there is no avg_marks given, then grade and result will also show blank.

Later, in case of take variable where there is atleast 1 missing value in score1, score2, score3, take will show incomplete and if for any student, all 3 marks are given, it will show complete.

And this result is shown in output2.

-  Then we made 2 subset of this output by 2 different processes where 1 subset will show all the student who has take = complete and another output will show who has take = incomplete.

i) We simply took the dataset and checked if take = complete given, then it will be printed in the subset1.

ii) If take = incomplete, then those observations will be printed on subset2

iii) Then again we took the entire dataset and checked if take = incomplete then deleted those values and saved it as subset3.

iv) Lastly, if take = complete, then deleted those observations and saved it as subset4.

            

# **1D ARRAY**

CODE:

* ARRAY;

proc import datafile= "/home/u59242738/Data Files/score_data_miss999.xlsx"

out= score_data_miss999 dbms=xlsx replace;

run;

proc print data = score_data_miss999;

run;

* One-dimensional ARRAY, converting the 999 values to period( . / space );

data dataset1;

set score_data_miss999;

array score_var(3) score1 score2 score3;

do i = 1 to 3;

if score_var(i) = 999 then score_var(i) = .;

end;

run;

proc print data = dataset1;

run;

OUTPUT:

![[Pasted image 20211119175640.png|300]]

EXPLANATION:

-  At first, we imported the datafile.

-  As we can see that there are some 999 values there which are wrong and we want to convert those to . null values and we used 1Dimensional array here for that purpose.

-  We defined a array as score_var here which has 3 variables score1, score2, score3.

-  Then for every ith variable of score_var we checked if any value is 999 or not and if it is 999 then we changed it to “.” (null value) and if it is not 999 then we stopped for that particular value and checked the next one.

            

# **GIVING TITLE TO A DATASET**

CODE:
```sas
proc import datafile= "/home/u59242738/Data Files/score_data_miss777.xlsx"

dbms = xlsx out = score_data0 replace;

run;

proc print data= score_data0;

title "missing values are shown as 777";

run;
```

OUTPUT:

![[Pasted image 20211119175804.png|300]]

EXPLANATION:

-  Here, the dataset is imported through proc print statement.

-  Then while print the output data we used a **title** code after the proc print data statement and before running it. That way we can give any title to any dataset.

            

# **ADDING LABELS TO THE VARIABLES**

-  We generally add labels for listing and reporting purpose.

-  Syntax for label:

label var_name = "Variable name";

or

label var_1 = "variable_label1"

var_2 = "variable_label2"

var_3 = "variable_label3";

-  there are generally permanent & temporary label

i) if label statements are included in data step then labels are permanent, whereas,

ii) if the label statements are included in proc step then labels are temporary.

CODE:
```sas
proc import datafile= "/home/u59242738/Data Files/score_data.xlsx"

out = adding_labels dbms=xlsx replace;

run;

data adding_labels_mod;

set adding_labels;

LABEL score1 = "Math score"

 score2 = "Stats score"

 score3 = "English score" ;

run;

proc print data= adding_labels_mod LABEL;

run; 

/* using label in proc print statement */

proc print data= adding_labels_mod LABEL;

LABEL name = "Students name";

run;

proc print data= adding_labels_mod;

run;

/* Splitting the labels */

proc print data= adding_labels_mod label split= "*";

label name = "student*name";

run;
```

OUTPUT:

![[Pasted image 20211119175917.png|500]]

![[Pasted image 20211119175924.png|500]]

EXPLANATION:

-  At first, we imported the data.

-  Then we used the label syntax for sas in our program and gave the label for Math score, Stats score, English score for score1, score2, score3 respectively through the datastep and printed it keeping in mind that we have to add LABEL statement in while printing the dataset.

-  Later, we gave the label for name as Students name and printed it.

-  Later, we only printed the data not using the LABEL statement in the proc print statement and got the original variable names in our output.

-  We can also split the label name in two different lines in the variable column by defining some concatenation as label split and using it in the label name code itself. We used * as concatenation here and used label name = student*name and got student and name splitted in two different lines in the variable name space.

# **ASSIGNING FORMAT INTO VARIABLE**

CODE:
```sas
proc import datafile= "/home/u59242738/Data Files/score_data_miss.xlsx"

out = data0 dbms = xlsx replace;

run;

data dataset1;

set data0;

total_score = sum(score1, score2, score3);

average_score = mean(score1, score2, score3);

run;

data dataset2;

set dataset1;

format average_score 5.2;

run;

proc print data = dataset2;

title "Permanent Format for average_score";

run;

/* Using temporary format in proc print statement */

proc print data= dataset2;

format score1 4.1;

format score2 4.1;

format score3 4.1;

title "Temporary Format for score1, score2, score3";
```
RUN;

OUTPUT:

![[Pasted image 20211119180113.png|500]]

EXPLANATION:

-  At first, we imported the dataset in SAS environment.

-  Later, from score1, score2, score3 we made 2 new variables as total_score and average_score which defines the sum and mean of these 3 score values respectively.

-  There we got some average values like 91.66666667, 59.6666667 like that and that’s why we used formatting here.

-  At first, we permanently formatted the average_score in 5.2 rule by which it will take only 2 decimal places and can take 5 values before the point and printed the first dataset with a title permanent format for average_score.

-  Later, we temporary formatted the 3 scores available (score1, score2, score3) in our dataset by 4.1 rule by which it can take 4 number values before point and can take only 1 decimal place and printed it with the title temporary format for score1, score2, score3.

            

# **USER DEFINE FORMAT**

CODE:
```sas
proc import datafile= '/home/u59242738/Data Files/score_data_miss.xlsx'

out= score_data0 dbms= xlsx replace;

run;

data score_data1;

set score_data0;

total_score = sum(score1, score2, score3);

average_score = mean(score1, score2, score3);

run;

proc format;

value $genderf 'f' = 'female'

'm' = 'male';

/* this $genderf variable will be created having the values female and male from f and m respectively*/

value as_group 0 - <60 = 'F'

60 - <70 = 'D'

70 - <80 = 'C'

80 - <90 = 'B'

90 - High = 'A'

other = 'Missing';

run;

proc print data = score_data1;

format gender $genderf. average_score as_group.;

title "User Define Formal Table"

run;
```

OUTPUT:

![[Pasted image 20211119180537.png|500]]

EXPLANATION:

-  At first, we imported the dataset and find out the total score and average score in numerical values.

-  Now, we had ‘m’ and ‘f’ values in gender variable and numerical mean values in average_score variable.

-  We used proc format here and defined gender f value as female and m value as male.

-  Then we took value from average_score and took them in group values like if the average_score is between 0 to 60 then it will return F, if its between 60 to 70 it will return D, like that we converted the average scores to grades and if there is any null value in average_score it will return missing.

-  Then we printed our data with proc print statement and used format statement to change these given gender values to formatted genderf character values and changed average_score to as_group which we defined and also gave a title to our dataset and printed it.

            

# **STORING AND REFERING AND USING USER DEFINE FORMAT**

CODE:
```sas
libname myfmts "/home/u59242738/SAS_code";

proc format library= myfmts;

value $genderf 'm' = 'Male'

 'f' = 'Female';

value asgroup 0-<60 = 'F'

 60-<70 = 'D'

 70-<80 = 'C'

 80-<90 = 'B'

 90- High = 'A'

 other = 'Missing';

run;

proc format library= myfmts fmtlib;

run;

proc import datafile= "/home/u59242738/Data Files/score_data_miss.xlsx"

out = scoredata0 dbms= xlsx replace;

run;

data scoredata1;

set scoredata0;

total_score = sum(score1, score2, score3);

avg_score = mean(score1, score2, score3);

libname myfmts "/home/u59242738/SAS_code";

option fmtsearch = (myfmts work library);

proc print data= scoredata1;

format gender $genderf. avg_score asgroup.;

run;
```

OUTPUT:

![[Pasted image 20211119180643.png|500]]

![[Pasted image 20211119180704.png|500]]

EXPLANATION:

-  If we have a lot of datasets and there are some primary formatting which has to been done in all of these datasets, we can use this method of storing the user define format and can use for all of the datasets in very simple 2 steps and don’t have to define again and again.

-  For this we have to call out our library to store the data and have to make a library for storing it.

-  Then we can define the values and grades as we did previously.

-  Then we printed the stored data in which we can check what exactly we defined.

-  Later, we imported a data and find out total and mean of the dataset.

-  Later, we called out the data where we stored our user defined format and refered to it.

-  Then we printed our data and just used the format statement so that sas environment can understand exactly in which dataset we want to use the use define format and for exactly which variables we want to use it and got our output.

            

# **USING CONDITIONAL CLAUSE WHILE ITTERATING DO-WHILE STATEMENT**

CODE:

```sas
/* Using conditional clause while itterating do-while statement */

/* In this dataset suppose we want to limit the number of years to invest in the capital to 10 years

and add the UNTIL expression to determine years it take for investment to reach 50 thousand to control the

number of years */

data invest;

do year = 1 to 10 until (capital >= 50000);

capital + 2000;

capital + capital * 0.10; /* if the interest rate is 10% */

output;

end;

/* if year = 11 then year = 10; */

run;

data invest;

do year = 1 to 10 until (capital >= 50000);

capital + 4000;

capital + capital * 0.10; /* if the interest rate is 10% */

output;

end;

if year = 11 then year = 10;

run;
```
OUTPUT:

![[Pasted image 20211119180759.png|200]]

EXPLANATION:

-  Here we tried to find out at 10% interest rate after investing some exact amount each year + gained amount how long will it take to reach that capital amount to 50000 in maximum of 10 years time.

-  Here at first out investment amount was 2000 each year and we can see that we couldn’t make 50000 at the end of 10th year and it seems like we need more time.

-  So, later we tried to invest 4000 each year and got the result with the help of do-while loop that we can gain 50000 capital plus some amount at the end of 8th year and don’t have to wait till 10th year.

            

# **CREATING VARIABLES IN ARRAY STATEMENT**

-  array array_name {dimension}

-  if variables are not specified then new variables name will be created like array_name1, array_name2 ... till dimension specification

-  if we want to specify the character array then syntax will be:

array array_name {5}$;

-  if we don't specify the length of the character it becomes 8

-  if we want to increase the length of the asssigned variable then syntax will be:

array array_name {5}$ 24; 

-  Assigning initial value in array & creating temporary array element Syntax:

array Goal{3} G1 G2 G3 (50 32 41)

-  if array is string,

then, array string{3} $ str1-str3 ('red','green','blue')

-  temporary array element which is not written in output,

array var{4}_temporary_(40 41 42 43) */

CODE:
```sas
proc import datafile= "/home/u59242738/Data Files/score_data_miss999.xlsx"

dbms = xlsx out = data0 replace;

run;

data score_data1(drop= i);

set data0;

array score_variable(3) score1 score2 score3;

do i = 1 to 3;

if score_variable(i) = 999 then score_variable(i) = .;

end;

average_score = mean(score1, score2, score3);

run;

proc print data= score_data1;

run;

data score_data2(drop= i);

set score_data1;

array score(3) score1 score2 score3; 

array score_diff(3); 

do i = 1 to 3;

score_diff{i} = score{i} - average_score;

end;

run;

proc print data= score_data2;

title "Creating variables in an Array statement";

run;

proc means data= score_data1; 

var score1 score2 score3;

run;

data score_data3(drop= i);

set score_data1;

array score(3) score1 score2 score3;

array avg{3} (79.5 81.9 80.8); /*Assigning initital values*/

array score_diff(3);

do i = 1 to 3;

score_diff{i} = score{i} - AVG{i};

end;

run;

proc print data= score_data3 (keep= name score_diff1 score_diff2 score_diff3);

title "Finding our X - Xbar using arrays";

run;
```

OUTPUT:

![[Pasted image 20211119181000.png|500]]

![[Pasted image 20211119181007.png|500]]

EXPLANATION:

-  At first, we imported the datafile and converted all the 999 values to missing values (.) and also found out the average score of all the students.

-  Then we again used array statement and found out the difference between each score and the average (per person wise) score for those individual students.

-  Then we found out the subject wise number of available values of students, average score, std deviation, minimum and maximum values of all the 3 subjects available.

-  Then we again used array statement and found out the difference between each score and the average (per subject wise) score for those students.

-  Also, while printing this last output we ignored to print the rest of the columns like score1, score2, score3, gender, and person wise average score.
          
# **CREATING TEMPORARY ARRAY ELEMENTS WHICH WE DONOT NEED TO PRINT IN THE FINAL RESULT**

CODE:
```sas
/* Creating temporary array elements which need not be printed in the final output*/

proc import datafile="/home/u59242738/Data Files/score_data_miss999.xlsx"

out=data dbms=xlsx replace;

run;

data data1 (drop = i);

set data;

array score_array(3) score1 score2 score3;

do i= 1 to 3;

if score_array(i)=999 then score_array(i)= . ;

end;

average_score = mean(score1,score2, score3);

run;

data data2 (drop = i);

set data1;

array score(3) score1 score2 score3;

array average{3}_temporary_(79.5 81.9 80.8); /*We are assigning values to average 1 2 and 3 which is stored

temporarily and does not require in final output*/

/* array average{3}_temporary_(79.5 81.9 80.8); */

array score_diff(3);

do i = 1 to 3;

score_diff{i} = score{i} - average{i};

end;

run;

proc print data=data2;

title "Assingning temporary array elements";

run;
```
OUTPUT:

![[Pasted image 20211119181118.png|500]]

EXPLANATION:

-  At first we imported the dataset and found out the person wise average score in the 3 scores given.

-  Then we find out the subject wise average score but didn’t store it permanently in the sas dataset but rather found out the difference in subject wise average score and the scores obtained by the students with the help of array statement.

            

# **MERGING TWO DATASETS (ONE TO ONE)**

CODE:
```sas
/* Combining SAS dataset (one-one mail merging) */

/* one-one merging */

proc import datafile= "/home/u59242738/Data Files/score_data_id_partial.xlsx"

out= data_a dbms= xlsx replace;

run;

proc import datafile= "/home/u59242738/Data Files/score_data_id.xlsx"

out= data_b dbms= xlsx replace;

run;

data one2one;

set data_a;

set data_b;

run;

proc print data= one2one;

title "One to One marging";

run;

proc print data= data_a;

title "Partial dataset";

proc print data= data_b;

title "Complete dataset";

run;
```
OUTPUT:

![[Pasted image 20211119181255.png|500]]

![[Pasted image 20211119181300.png|500]]

EXPLANATION:

-  There are 2 datasets given.

i) Full complete dataset given.

ii) Partial dataset given, like details of only 6 students are given out of 11 and score3 variables scores are not present in the dataset.

-  At first, we imported both of these 2 datasets.

-  Then just made a new dataset and set both of the datasets in there and simply we got the one-to-one merged dataset which was required here.

-  For convenience, the 2 given datasets are also printed here.

            

# **CONCATENATING TWO DATASETS**

-  **general form of** **CONCATENATING (syntax):**

data \<file name>;

set \<file name1> \<file name 2>;

run;

CODE:
```sas
/* Concatenating (combining)*/

proc import datafile= "/home/u59242738/Data Files/score_data_id_partial.xlsx"

out= data_a dbms= xlsx replace;

run;

proc import datafile= "/home/u59242738/Data Files/score_data_id.xlsx"

out= data_b dbms= xlsx replace;

run;

data concat;

set data_a data_b;

run;

proc print data= concat;

title "Concatenated dataset";

run;

proc print data= data_a;

title "partial dataset";

proc print data= data_b;

title "complete dataset";

run;
```
OUTPUT:

![[Pasted image 20211119181405.png|500]]

![[Pasted image 20211119181411.png|500]]

EXPLANATION:

-  There are 2 datasets given.

i) Full complete dataset given.

ii) Partial dataset given, like details of only 6 students are given out of 11 and score3 variables scores are not present in the dataset.

-  At first, we imported both of these 2 datasets.

-  Then just made a new dataset and set both of the datasets in there in the same line instead of taking 2 datasets in 2 different sets in 2 different lines and simply we got the concatenated (combined) dataset which was required here.

-  For convenience, the 2 given datasets are also printed here.

            

**APPENDING TWO DATASETS**

-  **syntax:**

proc append base = <filename_1>

data = <filename_2>;

run;

-  Base is the dataset to which observations are added.

-  Data is the name of the dataset containing observation that have to be added in base dataset.

-  We use force command where there is unlike structure of datasets.

CODE:
```sas
/* Appending */

proc import datafile= "/home/u59242738/Data Files/score_data_id_partial.xlsx"

out= data_a dbms= xlsx replace;

run;

proc import datafile= "/home/u59242738/Data Files/score_data_id.xlsx"

out= data_b dbms= xlsx replace;

run;

proc append base= data_a

data= data_b force;

run;

proc print data= data_a;

title "Appending dataset";

run;
```
OUTPUT:

![[Pasted image 20211119181440.png|500]]

EXPLANATION:

-  There are 2 datasets given.

i) Full complete dataset given.

ii) Partial dataset given, like details of only 6 students are given out of 11 and score3 variables scores are not present in the dataset.

-  At first, we imported both of these 2 datasets.

-  Here the appending was not so simple as merging and concatenating.

-  Here, we have to use append command in proc statement taking first data as the base data and second data to add it after the base data and then printed it and got the appending data which was required here.

-  As there is unlike structure of datasets, that’s why we had to use the force command or else there would be the observations from the second dataset used in the command here as there is an extra variable here then the base dataset.