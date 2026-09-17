# 2ECEB-ECE2112-PA4

**Made by: Lanz Joseph S. Pelayo || 2ECE-B**

# Introduction
This repository contains an explanation of the code for the programming assignment, which the author has made available for viewing. Specifically, the 
contents of this repository aim to address Programming Assignment #3, which comprises 3 problems, for the 2026-2027 academic year in ECE 2112. This aims to 
help viewers explain how the author used the program's functions to organize dataframes, visualize them in plots and bar graphs. This was drawn from the 
author's knowledge of Data Wrangling and Visualization from module 4.

# 0. Preliminary Setup:

The following commands were used in this problem to create an overall function used in the program:

• `import pandas as pd` - Command used to import the Python Data Analysis into the program in order to use the functions of the  pandas Library by using pd as 
a shortcut. 

• `import pandas as pd` - Command used to import the Matlab plot Library into the program in order to use the functions of the,Library such as plots and
graph in order to visualize dataframes in a program.

• `pd.read_excel('')` - Command used to read Xlsx files or Microsoft Excell Files in order to introduce them in the notebook and store them in a dataframe 
variable.

• `.mean(axis=1)` - Allows taking the average of the values set in a data set specified in the axis, which is horizontal.

With this preliminary setup, the author is able to introduce the needed libraries in order for the future functions of the programs to work. Additionally
Reading the ECE Board exam file and assigning it to a dataframe variable allows it to be stored. And lastly, to add a new category, taking the average 
scores by using `.mean(axis=1)` where it will take out the average score of each category of the test and create a new row for its average by putting 
`board['Average']` at the front. This allows us to complete the dataframe required that will be utilized in the next problems.


# A. VISAYAS COMMUNICATION DATAFRAME

A. VISAYAS COMMUNICATION DATAFRAME
Create a DataFrame named VisComm containing students whose Hometown is Visayas and whose Track
is Communication. Retain only these columns, in the stated order:
Name, Gender, Math, Electronics, Average
Display the resulting DataFrame and its number of rows. Both filtering conditions must be applied to
the source dataset before the columns are selected.


The following functions were used in this problem to create a unique function:

•`.loc[[M],[N]` - Label Location,A built-in function within the Pandas Library, which outputs the value at specific rows X and Y of the said variable 
before the dot. where it can be used with slicing and even names of specific rows and columns that are wished to be output.

• `.shape[]`- A built-in function within the Pandas Library to measure the shape of a dataframe or series variable, it usually measures how many rows and 
columns a dataframe has. If entered 0, it  gives the total Rows and 1 will be Columns.

 • Boolean Indexing - A type of method used to extract portions of data based on the said conditions within either rows or columns. These conditions can be 
 based on numbers within the columns, and if they are equal to the said name.

 This allows the author to create a program to store and display students from the Visayas whose track is Communication. By using the `.loc` function,
 this allows the program to extract and slice while also choosing specific parts to be presented and chosen, thanks to boolean indexing from the board 
 variable. This completes the selection of the required people in a certain category and stores it in the variable `Viscomm`. Also by using 
 `.shape[]` with a value inputted at 0, This allows the  program to count how many rows were presented which was 5.

 ```python
VisComm = board.loc[(board['Hometown'] == 'Visayas') & (board['Track'] == 'Communication'),['Name', 'Gender','Math', 'Electronics', 'Average']]
# Above code allows to take the Students who have a hometown of Visayas, and the Communications track from the Board variable and choose specific columns
# to ben stored.
VisComm.shape[0] #--> Allows to output how many rows there are
```

# B. VISAYAS FEMALE DATAFRAME
Create a second DataFrame named VisFemale containing students whose Hometown is Visayas and
whose Gender is Female. Retain only:
Name, Track, GEAS, Electronics, Average
Display VisFemale. Then display only the rows of VisFemale whose Average is at least 60. Do not
overwrite VisFemale when performing this second filter.


The following functions were used in this problem to create a unique function:

•`.loc[[M],[N]` - Label Location,A built-in function within the Pandas Library, which outputs the value at specific rows X and Y of the said variable 
before the dot. where it can be used with slicing and even names of specific rows and columns that are wished to be output.

• Boolean Indexing - A type of method used to extract portions of data based on the said conditions within either rows or columns. These conditions can be 
based on numbers within the columns, and if they are equal to the said name.

This allows the author to create a program that extracts only students from Visayas who are female. By using `.loc` to choose which students to
be chosen through the use of Boolean indexing, which allows the author to extract the Visayas and Female students and choose selected columns from the board 
variable that will be  stored in a variable named "VisFemale". In a separate, to show the students who are in the VisFemale variable that has an average 
score 
higher than 60, the author used boolean indexing to show and display it in the notebook.

VisFemale = board.loc[(board['Hometown'] == 'Visayas') & (board['Gender'] == 'Female'),['Name', 'Track', 'GEAS', 'Electronics', 'Average']] #--> Selects
# Students From Visayas and are female, where selected Columns are shown, where it was taken from the board variable and stored in the VisFemale Variable.

VisFemale.loc[VisFemale['Average'] >=60] --> Only show the students in the variable got a average score greater than 60.

# C. CATEGORY-AVERAGE VISUALIZATION
Examine how the recorded Average differs across the three categorical features Track, Gender, and
Hometown.
a. For each feature, compute the mean of Average for every category using Pandas.
b. Display the three summary tables.
c. Create one figure containing three bar charts: mean Average by Track, by Gender, and by
Hometown.
d. Below the figure, write three concise statements identifying the category with the highest sample
mean for each feature.
Interpretation rule: Describe the observed dataset only. A difference in group means does not, by
itself, establish that a feature causes a higher board-exam score.

The following functions were used in this problem to create a unique function:

• `.mean()` - = A function automatically takes the average or mean value from a list or an array without manually calculating the mean through hard code.

• `.groupby()` - A function that allows grouping and combining according to its category and performs certain functions as one aggregated dataframe within a 
dataframe instead of hardcoding it and extracted it to another variable.

• `plt.subplot ` - A function in the matlabplot library that allows to create a plot with multiple subplots in image with multiple dataset included.

• `.plot` - A function the MATLABplot library that allows creating ae plot where it can be customized and set how the plot, kind of
graph, Title, labels, Colors, Font Size, Values in the graph, Which position in the subplot in a plot, and etc... to be set in the plot.

• `plt.show()` - Allows to show the plot made in the function.

This allows the Author to create a program that takes the average of the average scores by track, gender and hometown which is done thanks to 
the groupby function separately. This further allows the author to create the plots using `.plot` and `plt.subplot` commands to make a plot and using the 
average of each category of track, gender and hometown can allow the author to encode and edit the plot more neatly and visualize the group of students 
performance. By setting each subplot with the kind of graph (which is bar), which subplot or ax to occupy, edit the title of the subplot and y label, Its 
color, fontsize and ylimit, this allows author to creata well presented visualized graph of the function.

```python

trackmean = board.groupby('Track')['Average'].mean()
gendermean = board.groupby('Gender')['Average'].mean()
hometownmean = board.groupby('Hometown')['Average'].mean()
# The above code groups the students according to their category and takes the average score, where the mean is taken.

fig, ax= plt.subplots( 1, 3, figsize = (15,5)) #--> Makes a Plot with subplots of 1 row and 3 columns where the figure size is 15 inches wide and 5 tall.

trackmean.plot(kind='bar', ax=ax[0], title = 'Average Score By Track', ylabel = 'Average Scores', color= 'teal', rot = 0, fontsize = 9, ylim = (0,100))
gendermean.plot(kind='bar', ax=ax[1], title = 'Average Score By Gender', ylabel = 'Average Scores', color= 'Purple', rot = 0, ylim = (0,100))
hometownmean.plot(kind= 'bar', ax=ax[2], title = 'Average Score By Hometown', ylabel = 'Average Scores', color= '#012db9', rot = 0, ylim = (0,100)) 
# The above code shows that the subplots were made  of what graph, which subplot to take, what title named, ylabel, color, rotation of the categorical
# score, its y-limit, and font size.

plt.show() # --> Shows the plot
```
Version History\
9/17/2026 - Uploaded Content\






