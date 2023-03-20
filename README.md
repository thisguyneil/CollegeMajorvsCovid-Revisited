
# CollegeMajorvsCovid-Revisited

# How To Run
## Instructions:

<p> 

1. Clone this repository to your machine from GITHUB to your local environment
2. Navigate to this new repository through terminal in MacOs/Linux or command prompt in Windows
3. Check to see you are in the correct location using 'ls' if you're on a Mac or Linux, if you are on windows use 'dir' and check to see if the output is the same as the files listed in this repository 
4. Create a virtual environment within your terminal, you will know this is successful if your terminal or command prompt displays "venv" in parenthesis 
5. Install the requirements using the command "pip install -r requirements.txt"
6. Once all required packages are installed, open the .ipynb file 

</p>

# About the project
## A simple analytical look at a psychology project for my Graduate Psychology program in 2021. 

<p> 
I believe that a college or university's top goal is to prepare students for their eventual place in their field of choice. Educators must adapt to new and changing job requirements and the knowledge needed to make an impact in the field. For cutting edge fields like medicine and STEM, this dedication to the implementation of emerging technology is paramount. The global pandemic of Covid-19 requires these cutting edge fields to prioritize the training of nurses, biologists, and medical field workers to new methods of stopping transmission and curing patients. My main questions are to see if students of various college majors have a difference in perceived importance of Covid-19 and its preventative measures and to see if there are any significant difference variances in their data. Would a history major have a higher perceived importance of Covid-19 vs a nursing major? Does the biological sex or college grade (Freshman-Graduate) of the student have any impact in their perceived importance of Covid-19?

This project collected anonymous data from students from Union College of various grade levels, biological sex, and college majors and tested to see if there was any relation to the students college major and their perceived importance of Covid-19. Besides the basic demographic questions, most questions asked to the students are based off of the Likert scale that spans from "strongly disagree", "disagree", "neither agree nor disagree", "agree", and "strongly agree" and a few additional questions that ask True/False, Yes/No responses.  The question inventory is a custom inventory created by the study's author as there are very few related question inventories at the time of this study's creation. 
</p>

# 1. Read the Data In

<p> 
This section is to help clean up our responses, which are all stored in an external excel (xlsx) document called Raw_Study_Responses.xlsx in the assets folder. 
1. I read the data in by using the pd.read_excel command and loaded it into a dataframe. I then displayed the headers of the file to show not only some of the original questions (which were stored in the headers) of the project, but also to make sure my data was read into the notebook correctly.
</p>

# 2. Clean the data

<p> 
This data has some formatting I do not like including some blank cells, n/a answers, and other data I do not want to be included in my analysis, so I will clean and format this data and save it to a new excel file.
1. I wanted to shorten the names of my columns into a basic "question 1, question 2, etc" style formatting to make sure that when visualized later the code is not super long, plus I wanted to try out this batch renaming function for my columns, so I created a dictionary called "new_names" that linked the old column names to the new column names and used the "df.rename(columns)" function to rename my columns.
2. There are questions in this study that I need to drop because they will not be used in this analysis. I can use the "df.drop" command and select multiple columns to drop.
3. Those students who are uner 18 cannot accept an informed consent form (which was the first question and link in the study) without their parent/guardian's consent, so the few subjects who are under 18 I will remove those rows from the data.
4. The main part of the study is about nursing majors due to the high number of nursing majors at our college. I can easily create a function to just include nursing majors from the college major column, but I wanted to take this one step further and make a new column that would show whether or not the student is a STEM (science, technology, engineering or mathematics) major, this way I can vizualize if there is a difference between soft sciences and STEM in relation to the questions above. 
</p>