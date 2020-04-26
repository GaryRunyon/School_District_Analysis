# School_District_Analysis

In Py_City_schools.ipynb, school district data was filtered an analyzed to determine student and school perfromance based on factors such as school size, school type, funding (overall and per-student), etc. 

In PyCitySchool_Challenge, the aforementioned analyses were revised to include amended data for Thomas High School, secondary to a cheating scandal involving their 9th graders. This was accomplished by using code that sorted the school_summary_df "grade" column by 9th, and the "school name" column by Thomas High School. The math and reading scores in the columns that fit the criteria were replaced with the value, "NaN." The code used was as follows:

student_data_df.loc[(student_data_df.grade=='9th') & (student_data_df.school_name=='Thomas High School'), ['reading_score', 'math_score']]=np.NaN
student_data_df

The amended data frame was then merged with the pre-existing frame and new summaries were calculated accordingly.



Per the challenge: 

*** Recreate the district and school summary DataFrames.
1) How is the district summary affected? - The district_summary_df is affected only by changes in the "% Passing Math" (from 75 yo 74%), the "% Passing Reading" (from 86 to 85%) and the "% Overall Passing" columns (65 to 64%). This is due to the relative size of the 9th grade class at Thomas High School as compared to all other classes in all other (14) schools. 
2) How is the school summary affected? - Similarly, the school_summary_df is affected only by changes in the rows for Thomas High School, namely the "% Passing Math","% Passing Reading", and "% Overall Passing" columns. More specific changes are outlined below. 



*** Recalculate the high- and low-performing schools.

1) How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance, relative to the other schools? Thomas High School went from an overall rank of 2nd to 8th, in terms of the "% Overall Passing" students. The percentage dropped from 90.95 to 65.08% per the new_school_ranking_df, where the column "% Overall Passing" was sorted by descending value. 


*** Recalculate the scores by grade, scores by school spending, scores by school size, and scores by school type. How does replacing the ninth-grade scores affect the following?

1) Math and Reading Scores by Grade - The average passing reading and math scores were not affected. The NaN isn't incorporated into mathematical calculations such as mean(), sum(), etc. It only affected the number of passing students because it is Not A Number but can populate cells where calculations using INT or FLOAT64 variables are being used. So, the NUMBER of passing students in the 9th grade changed but the AVERAGE PASSING GRADE did not change, as NaN is not counted as a value of zero. 

2) Scores by School Spending - The Budget for Thomas High School falls in the "$630 to $644 per student" bin. Therefore, the new data only affected this bin in the spending_summary_df. In this bin, the "% Passing Math" dropped from 73.5 to 66.9%, the "% Passing Reading" dropped from 84.4 to 77.5%, and the "% Overall Passing" dropped from 62.9 to 56.4%. 

3) Scores by School Size - Thomas High School is a "Medium-Size School"so the "% Passing Math" for "Medium (1,000 to 2,000 students) dropped from 94 to 88%, "% Passing Reading" dropped from 97 to 91%, and the "% Overall Passing" dropped from 91 to 85%. This is depicted in the size_summary_df. 

4) Scores by School Type - Since Thomas High School is a "Charter School," this affected the "% Passing Math (94 to 90%), the "% Passing Reading" (97 to 93%) and "Overall Passing" (90 to 87%). This is depicted in the type_summary_df. 


