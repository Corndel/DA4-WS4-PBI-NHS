# Recreating a Dashboard in PowerBI
In this workhsop we will recreate some of the charts in the following published dashboard, namely the line chart and Slicer.\


![alt text](image-2.png) 

https://app.powerbi.com/view?r=eyJrIjoiOTNjNTRhZDQtOTFhNy00MTNmLWIxODgtNTZiNWQ5YWViYTc4IiwidCI6IjUwZjYwNzFmLWJiZmUtNDAxYS04ODAzLTY3Mzc0OGU2MjllMiIsImMiOjh9\

In addition to this we will alter the tables, create a Clustered Bar Char and add two call out cards.

![alt text](image-38.png)

# Step 1 - Download the data
Download hospital_activity_data.csv from this repo\
The data can also be downloaded directly from:\
https://files.digital.nhs.uk/B1/D9317B/HES_M8_OPEN_DATA_AGE_GROUPS.csv

**_NOTE:_** This data is not in the best form for analysis with PowerBI. \
Initially we will use as is, then we will transform using PowerQuery including unpivoting some columns.



# Step 2 - New report
Open up PowberBI and select "Blank report"

![alt text](image.png)

# Step 3 - Import the data
Select: 
1.  Down arrow on "Get data" then 
1.  "Text/CSV" from the sub menuThe navigate to the the downloaded hospital_activity_data.csv 

![alt text](image-1.png)

A PowerQuery Window will now open giving you an overview of the data.This data is clean and we can directly 
1.  "Load" the data 
Even though we know the data is clean it is a good idea to view the data, have a look through the columns and ensure you dont see any obvious errors.

![alt text](image-3.png)

You will see that the file appears on the far right Data Panel Select: 
  1.  The down arrow to the left of the file to expand and view all columns 

The columns with:
* Σ denote that they are numerical
* Calendar Icons denote they are dates
* No icon before Age_Band deontes it being intrepreted as Text

![alt text](image-4.png)

# Step 4 - Add the Title

 1. Select "Insert" from the top left 
 1. Select "Text Box"

![alt text](image-31.png)

 1. Set the font to Verdana, Size 14 and Bold
 1. Enter the title "Monthly HES data for Admited Patient Care by Age Band"

![alt text](image-32.png)

# Step 4 - First Visual - Line Chart
Select  
1. Line chart from the Visualisations Panel

![alt text](image-5.png)

This will create a placeholder for the chart in the main canvas. 

![alt text](image-6.png)

We will add the fields from the data panel and drag them to the visualistaion panel.


For the X-axis, drag in:\
&nbsp;&nbsp;&nbsp;&nbsp; Month_ending


For the Y-axis drag in:
* FAE
* Emergency
* FCE
* FCE_DAY_CASES
* Ordinary_Admission_Episodes 

The default aggregation for numerical columns is Sum and this is what we are going to use.

![alt text](image-7.png)

Resize the visual occupy the top half of the canvas 

![alt text](image-8.png)


There are many things that need to be formatted in this visual to match the published example we are recreating

![alt text](image-9.png)
![alt text](image-10.png)

* Title
* Outline
* Axis Labels
* Line Colours
* Legend
* Y-axis Values Formatting
* Number Formatting
* Monthly View
* X-axis Range
* X-axis Values Formatting

Of this list, the easiest thing to address is the Title and the mot difficult is the X-Axis Values Formatting.

## Title
 1. Select "Format Visuals" in the "Visualisations" panel 
 1. Select the "General" Tab 
 1. Select "Title" and rename to "Inpatient Monthly Activity by episode / admission type"

![alt text](image-12.png)

## Outline
Ensure you have the Line chart Selected in the main canvas then: 
1. Select "Format Visuals" in the "Visualisations" panel 
1. Select the "General" Tab 
1. Select the "Effects" Tab 
1. Turn on "Visual Border", select light blue from for the colour and round the corners to 30 pixels

![alt text](image-11.png)

## Axis Labels
Ensure you have the Line chart Selected in the main canvas then: 
1. Select "Format Visuals" in the "Visualisations" panel 
1. Select the "Visual" Tab 1. Select the "Title" Tab 
1. Change the text to "Month of Activity" (none of the data is provisional now)

Repeat the same steps for the Y-axis labelling it "Episodes / Admissions"

![alt text](image-13.png)

## Colours
Ensure you have the Line chart Selected in the main canvas then: 
1. Select "Format Visuals" in the "Visualisations" panel 
1. Select the "Visual" Tab 1. Select the "Lines" Tab 
1. Select the Series you wish to edit in the "Series" dropdown and chose the colour from the quick list displayed 

Repeat this for all other lines

![alt text](image-14.png)

## Legend
Ensure you have the Line chart Selected in the main canvas then: 
1. Select "Build Visual" in the "Visualisations" panel 
1. In the Y-axis section, select the arrow to the right of a field to get it's menu 
1. Select "Rename for this visual" and adjust accordinglyRepeat this for all other lines

![alt text](image-15.png)

## Y-axis Values Formatting
Ensure you have the Line chart Selected in the main canvas then:
 1. Select "Format Visual" in the "Visualisations" panel
 1. Expand the Y-axis section, select "Display units" and set to "None"
 1. Select "Display units" and set to "None"

![alt text](image-16.png)


## Number Formatting
 1. Select "Table View" in the far left panel
 1. Select the "FCE" column 
 1. Select the COMMA icon in the "Formatting" pane of the "Column tools" Menu

This adds commas to the number display. Go back to the report view and see how it changes the formatting for this series only in the tool tip.The tool tip is what it displayed when you hover the cursor over the line chart. It will respond dynamically to where the curosor is on the graph.

Return to the "Table view" and repeat for all columns used in the display.Once finished, this will now change the formatting on the Y-axis

![alt text](image-17.png)


## Monthly View
 1. Select "Report view" if you are not there 
 1. Select "Expand all down one level" Until you have the monthly view

Monthly view is the most granular level of our Data as it is recorded as month end.

![alt text](image-18.png)

## X-axis Range
Ensure you have the Line chart Selected in the main canvas then: 
1. Select "Format Visual" in the "Visualisations" panel* 
1. Expand the X-axis section 
1. Set the Range from 01/04/2019 to 31/03/2021*Note how the Data Type for the X-axis is continuous

**_NOTE:_**  Change the "type" to categorical and see that you cannot limit the range anymore. \
To revert select "Reset to default" at the bottom of all X-axis options.

![alt text](image-19.png)


Our charts are now very close. However, we still some issues:
* X-axis not the same
* Charts look different at extremes
* Tool tips display differently

##### Ours

![alt text](image-20.png)

##### Target

![alt text](image-21.png)

## X-axis Values Formatting

In order to format the X-axis exactly as the example we will need to:
* Restrict the range of the data as the X-axis needs to be categorical*
* Create a new column with the month, as 3 letters, and the year
* Sort this by the original month end column
* Make this column the new X-axis

*When a column is categorical we cannot restrict the range as we did before in the "Format Visual" panel

## Restrict Range

 1. Select "Table View" in the far left panel 
 1. Select the "Home" tab 1. Select "Transform Data" 
 1. Select "Transform Data"

**_NOTE:_** We will now be performing transformations in PowerQuery.

![alt text](image-22.png)

A Power Query Window will open 
1. Select the "Filters" button on the Month_Ending" column 
1. Select "Date Filters" and choose "Between" in the sub menu

![alt text](image-23.png)

 1. In the pop up dialogue window enter the range 30/04/2019 to 31/03/2021

![alt text](image-26.png)

While in PowerQuery we can streamline our pipline. \
1. Remove any columns that we are not using
1. Rename columns, these names will be the defaults for all visuals



 1. Select "Close & Apply"

![alt text](image-27.png)

The changes will now take effect.

## Create column for Abbreviated Month and Year

 1. Select "Table View" in the far left panel 
 1. Select "New Column", you should be in "Column tools" by default 
 1. Enter "Short_Month = FORMAT([Month_Ending], "MMM yyyy")" as the calculation**Note how this column is interpreted as Text and not Date, this will change how the axis is displayed.

![alt text](image-24.png)

 1. Select the newly created "Short_Month" column  
 1. Select "Sort by column" 
 1. Select "Month_ending"

![alt text](image-25.png)

## Assigning to the X-axis

 1. Select "Report View" in the far left panel 
 1. Deselest "Month_Ending" 1. Select "Short Month" 
 1. Note how it updates in the X-axis 
 1. Note how the X-axis formatting changes

![alt text](image-28.png)

Your Chart should now be very similair to the example. \
The tool tips shoulld display properly as well as the correct format for the X-axisOurs

![alt text](image-30.png)

Target

![alt text](image-29.png)


## Step 5 - Add the Slicer

Ensure you have Selected white Space in the main canvas then: 
1. Select "Build Visual" in the "Visualisations" panel 
1. Select "Slicer" from the choarts menu 
1. Add "Age_Band" to "Field" 
1. Rename to "Age Breakdown"

![alt text](image-33.png)


 1. Select "Format Visual" in the "Visualisations" panel 
 1. Select "Dropdown" from the "Style" menu in "Slicer Settings"

![alt text](image-34.png)

Resize and move the visuals to match the target dashboard. \
Experiement with the Slicer and note the fieldormat of the data within.

![alt text](image-35.png)

## Step 6 - Clustered Bar Chart

![alt text](image-39.png)

In order to Create the Clustered Bar chart we must first "Unppivot some columns"

## Step 6 - Summary Tables

We will create a table 

![alt text](image-36.png)

Firstly, to explore another way to change the name of fields on the display, we will change the name of the fields in "Data view". Changes made here will affect all visuals that the fields are involved in.

 1. Select "Data View" in the far left panel 
 1. Right click on a column you wish to rename 
 1. Enter the new name, and continue for all relevant columns, these will be the columns with "commas" that you inserted before


![alt text](image-37.png)