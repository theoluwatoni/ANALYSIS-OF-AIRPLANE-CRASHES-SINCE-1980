# ANALYSIS-OF-AIRPLANE-CRASHES-SINCE-1980
Data cleaning, analysis, and report creation for Airplane Crashes in PowerBI.

## INTRODUCTION
This project is a product of my participation in the #NG30DaysOfLearning initiative, which was put together by Olanrewaju Oyinbooke and his team to keep students occupied and assist them in learning throughout the 2022 ASUU strike. These items are included in the documentation:
1. Problem Statement
2. Data Collection
3. Data Cleaning Transformation 
4. Report Design
5. Conclusion

## 1. PROBLEM STATEMENT
The topic of airplane crashes is not new. This project examined airplane crashes since 1908 and examined a variety of elements that may contribute to a crash. Some of my personal goals or inquiries were as follows:
1. What number of fatalities were reported?
2. How many of them survived?
3. How many routes were taken, and how many places were visited?
4. What connection exists between fatalities and the days or weeks of the week?
5. Where were the most fatalities reported?
6. What are the most popular places that people visited?
7. What were the reasons of fatalities, as indicated by the comments on each record?
8. Most accidents per operator?
9. When analyzing the dataset, look for any interesting trends or behaviors and add to my report.


## 2. DATA COLLECTION
The data was obtained from kaggle and contained  the full history of airplane crashes throughout the world, from 1908-2009. It was posted in 2016 by SAURO GRANDI. The original version was hosted by Open Data by Socrata at the at: https://opendata.socrata.com/Government/Airplane-Crashes-and-Fatalities-Since-1908/q2te-8cvq, but unfortunately that is not available anymore. The dataset contains data of airplane accidents involving civil, commercial and military transport worldwide from 1908-09-17 to 2009-06-08.
The data originally had 5268 rows and 13 columns. The features of the dataset include:
* Date - Date of the accident in the format (mm/dd/yyyy)
* Time - Local time in 24hr format
* Location - Location of the accident
* Operator - Airline or Operator of the aircraft
* Flight# - Flight number assigned by the aircraft operator
* Route - Complete or partial route flown prior to the accident
* Type - Aircraft type
* Registration - ICAO registration of the aircraft
* Cn/In - Construction or serial number / Line or fuselage number
* Aboard - Total number of persons aboard (passengers & crew)
* Fatalities - Total fatalities aboard (passengers & crew)
* Ground - Total number of persons killed on the ground
* Summary - Brief description of the accident and cause if known

The dataset was then cleaned with Python after being downloaded as a csv file to my local computer.


## 3. DATA CLEANING & TRANSFORMATION
Before being imported into PowerBI, the data was originally converted with Python using Jupyter Notebook.
To carry out fundamental operations and EDA, four major Python libraries (pandas, numpy, matplotlib, and seaborn) were loaded.
In order to start the transformation, Pandas was used to read the data from my local disk into Jupyter Notebook using the pd.read csv method. Now that the dataset had been accessed, we could see that the majority of the columns had empty values. The "Flight#" and "Registration" columns were not helpful for the questions I needed to answer, so I omitted them. The graphic below displays the proportion of empty cells in each of the columns.
The empty fields in the other category columns, such as "Route," "Summary," "Operator," and "Type," were filled with, respectively, "Not Defined," "No Comments," "Unknown," and "No Type."
RegEx was used to extract the 'Military' column and show 'TRUE & FALSE' for cells that contained the string military in them and cells that did not contain the string military, respectively, creating a new column called 'Is Military'. this was done to determine whether or not the ground deaths were caused by a military plane or operator.
In certain instances, the 'Location' column had both states and countries. To establish a new column called "Location County," the countries were separated out using the split function.
A straightforward subtraction was used to determine the number of survivors by deducting the fatalities from the total number of passengers, creating a new column labeled "Survived." There are now 20 blank cells in the Location column, and because we can still access the data for some of them via the Operator column, we filled those manually while choosing random locations from the 'Location Country' column for the other cells.
The 'Aboard, Fatalities & Ground' columns' empty values were filled with the mean of the corresponding columns, and the 'cn/In' column's empty values were filled with the string 'Unidentified'
Now, only the "Time" column had null values, and they were filled with the string "Time Unknown". The data is now tidy and ready for use, so it is once more saved to my local disk as a csv file.
I wrote some DAX functions to split the Date column into its corresponding year, month, day, and weekday after importing the data into PowerBI.


## 4. REPORT DESIGN
The layout for this report was created using Figma, a design tool that enables you to create designs for mobile and web interfaces as well as any other kind of design you can think of. After choosing the queries to be answered and the reports to use, several card designs were created for each viz and integrated into a single design. The figma icon plugin iconify is where all of the icons used in this report were acquired from. Color schemes and shades were selected from adobe.color.com. After putting everything together and making my background in Figma, I uploaded it to PowerBI; the png file can be downloaded here. This is what the initial background looked like.


Here is what the final report design looks like.


## 5. CONCLUSION
My oga, Mr. Olanrewaju Oyinbooke, and his team deserve all the credit for making this project enjoyable to work on. If you want to reproduce, I hope my documentation is clear enough for you to comprehend it. You are welcome to change my scripts or designs to create something more beautiful. If you do, kindly mention me on Twitter by using the handle @superweirdpm. 🚀

