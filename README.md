# Recreating a Dashboard in PowerBI
In htis workhsop we will recreate the following dashboard in PowwrBI.

![](image-2.png)
https://app.powerbi.com/view?r=eyJrIjoiOTNjNTRhZDQtOTFhNy00MTNmLWIxODgtNTZiNWQ5YWViYTc4IiwidCI6IjUwZjYwNzFmLWJiZmUtNDAxYS04ODAzLTY3Mzc0OGU2MjllMiIsImMiOjh9

# Step 1 - Download the data
Download hospital_activity_data.csv from this repo

# Step 2 - New report
Open up PowberBI and select "Blank report"

![alt text](image.png)

# Step 3 - Import the data
Select:\
&nbsp;&nbsp;&nbsp;&nbsp;[1] Down arrow on "Get data" then\
&nbsp;&nbsp;&nbsp;&nbsp;[2] "Text/CSV" from the sub menu\
The navigate to the the downloaded hospital_activity_data.csv 

![alt text](image-1.png)

A PowerQuery Window will now open giving you an overview of the data.\
This data is clean and we can directly\
&nbsp;&nbsp;&nbsp;&nbsp;[1] "Load" the data\
Even though we know the data is clean it is a good idea to view the data, have a look through the columns and emsureyou dont see any obvious errors.

![alt text](image-3.png)

You will see that the file appears on the far right Data Panel \
Select:\
&nbsp;&nbsp;&nbsp;&nbsp;[1] The down arrow to the left of the file to expand and view all columns 

The columns with:\
&nbsp;&nbsp;&nbsp;&nbsp;  - Σ denote that they are numerical\
&nbsp;&nbsp;&nbsp;&nbsp;  - Calendar Icons denote they are dates\
&nbsp;&nbsp;&nbsp;&nbsp;  - No icon before Age_Band deontes it being intrepreted as Text

![alt text](image-4.png)

# Step 4 - First Visual - Line Chart
Select \
&nbsp;&nbsp;&nbsp;&nbsp; [1] Line chart from the Visualisations Panel

![alt text](image-5.png)

This will create a placeholder for the chart in the main canvas. 

![alt text](image-6.png)

We will add the fields from the data panel and drag them to the visualistaion panel.

For the X-axis, drag in\
&nbsp;&nbsp;&nbsp;&nbsp; Month_ending

For the Y-axis drag in:\
&nbsp;&nbsp;&nbsp;&nbsp; FAE\
&nbsp;&nbsp;&nbsp;&nbsp; Emergency\
&nbsp;&nbsp;&nbsp;&nbsp; FCE\
&nbsp;&nbsp;&nbsp;&nbsp; FCE_DAY_CASES\
&nbsp;&nbsp;&nbsp;&nbsp; Ordinary_Admission_Episodes \
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

Of this list, the easiest thing to address is the outline and the mot difficult is the X-Axis Values.

## Title
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Format Visuals" in the "Visualisations" panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select the "General" Tab\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select "Title" and rename to "Inpatient Monthly Activity by episode / admission type"

![alt text](image-12.png)

## Outline
Ensure you have the Line chart Selected in the main canvas then:\
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Format Visuals" in the "Visualisations" panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select the "General" Tab\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select the "Effects" Tab\
&nbsp;&nbsp;&nbsp;&nbsp; [4] Turn on "Visual Border", select light blue from for the colour and round the corners to 30 pixels

![alt text](image-11.png)

## Axis Labels
Ensure you have the Line chart Selected in the main canvas then:\
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Format Visuals" in the "Visualisations" panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select the "Visual" Tab\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select the "Title" Tab\
&nbsp;&nbsp;&nbsp;&nbsp; [4] Change the text to "Month of Activity" (none of the data is provisional now)\
Repeat the same steps for the Y-axis labelling it "Episodes / Admissions"

![alt text](image-13.png)

## Colours
Ensure you have the Line chart Selected in the main canvas then:\
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Format Visuals" in the "Visualisations" panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select the "Visual" Tab\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select the "Lines" Tab\
&nbsp;&nbsp;&nbsp;&nbsp; [4] Select the Series you wish to edit in the "Series" dropdown and chose the colour from the quick list displayed\
Repeat this for all other lines

![alt text](image-14.png)

## Legend
Ensure you have the Line chart Selected in the main canvas then:\
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Build Visual" in the "Visualisations" panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] In the Y-axis section, select the arrow to the right of a field to get it's menu\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select "Rename for this visual" and adjust accordingly\
Repeat this for all other lines

![alt text](image-15.png)

## Y-axis Values Formatting
Ensure you have the Line chart Selected in the main canvas then:\
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Format Visual" in the "Visualisations" panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Expand the Y-axis section, select "Display units" and set to "None"\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select "Display units" and set to "None"

![alt text](image-16.png)


## Number Formatting
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Table View" in the far left panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select the "FCE" column\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select the COMMA icon in the "Formatting" pane of the "Column tools" Menu\

This add commas to the number display. Go back to the report view and see how it changes the formatting for this series only in the tool tip.\
The tool tip is what it displayed when you hover the cursor over the line chart. It will respond dynamically to where the curosor is on the graph.

Return to the "Table view" and repeat for all columns used in the display.\
Once finished, this will now change the formatting on the Y-axis

![alt text](image-17.png)


## Monthly View
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Report view" if you are not there\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select "Expand all down one level" Until you have the monthly view

Monthly view is the most granular level of our Data as it is recorded as month end.

![alt text](image-18.png)

## X-axis Range
Ensure you have the Line chart Selected in the main canvas then:\
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Format Visual" in the "Visualisations" panel*\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Expand the X-axis section\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Set the Range from 01/04/2019 to 31/03/2021\
*Note how the Data Type for the X-axis is continuous

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

In order to format the X-axos exaclty as the example we will need to:
* Restrict the range of the data as the X-axis needs to be categorical*
* Create a new column with the month, as 3 letters, and the year
* Sort this by the original month end column
* Make this column the new X-axis\
*When a column is categorical we cannot restrict the range as we did before in the "Format Visual" panel

## Restrict Range

&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Table View" in the far left panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select the "Home" tab\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select "Transform Data"\
&nbsp;&nbsp;&nbsp;&nbsp; [4] Select "Transform Data"\

![alt text](image-22.png)

A Power Query Window will open\
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select the "Filteres" button on the Month_Ending" column\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select "Date Filters" and choose "Between" in the sub menu\

![alt text](image-23.png)

&nbsp;&nbsp;&nbsp;&nbsp; [1] In the pop up dialogue window enter the range 30/04/2019 to 31/03/2021

![alt text](image-26.png)

&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Close & Apply"

![alt text](image-27.png)

The changes will now take effect.
## Create column for Abbreviated Month and Year

&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Table View" in the far left panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select "New Column", you should be in "Column tools" by default\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Enter "Short_Month = FORMAT([Month_Ending], "MMM yyyy")" as the calculation*\
*Note how this column is interpreted as Text and not Date, this will change how the axis is displayed.

![alt text](image-24.png)

&nbsp;&nbsp;&nbsp;&nbsp; [1] Select the newly created "Short_Month" column \
&nbsp;&nbsp;&nbsp;&nbsp; [2] Select "Sort by column"\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select "Month_ending"

![alt text](image-25.png)

## Assigning to the X-axis
&nbsp;&nbsp;&nbsp;&nbsp; [1] Select "Report View" in the far left panel\
&nbsp;&nbsp;&nbsp;&nbsp; [2] Deselest "Month_Ending"\
&nbsp;&nbsp;&nbsp;&nbsp; [3] Select "Short Month"\
&nbsp;&nbsp;&nbsp;&nbsp; [4] Note how it updates in the X-axis\
&nbsp;&nbsp;&nbsp;&nbsp; [5] Note how the X-axis formatting changes\

![alt text](image-28.png)
