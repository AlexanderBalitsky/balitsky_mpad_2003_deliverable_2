**November 5th 2026**<br>
**MPAD2003A Introductory Data Storytelling**<br>
**Alexander Balitsky**<br>
**Presented to Jean-Sébastien Marier**<br>

# Deliverable 2: Exploratory Data Analysis (EDA)

## Foreword

For this assignment, you must clean and analyze the dataset from Deliverable 1, create exploratory charts/visualizations, and identify a potential story. Your assignment must clearly detail your process. You are expected to write about 1,000-1,200 words, and to include several screen captures showing the different steps you went through. Your assignment must be written with the Markdown format and submitted on GitHub.

I have been assigning different versions of this project to my digital journalism and data storytelling students for a few years now. Its structure was inspired by the main sections/chapters of [*The Data Journalism Handbook*](https://datajournalism.com/read/handbook/one/). This version was further inspired by the [Key Capabilities in Data Science](https://extendedlearning.ubc.ca/programs/key-capabilities-data-science) program offered by the University of British Columbia (UBC).

**Here are some useful resources for this assignment:**

* [GitHub's *Basic writing and formatting syntax* page](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [The template repository for this assignment in case you delete something by mistake](https://github.com/jsmarier/jou4100_jou4500_mpad2003_project2_template)

Did you notice how to create a hyperlink? In Markdown, we put the clickable text between square brackets and the actual URL between parentheses.

And to create an unordered list, we simply put a star (`*`) before each item.

## 1. Getting Data
For this exploratory data analysis, I'll be analyzing 3 City of Ottawa datasets about outdoor water facilities. This includes outdoor pools, wading pools, and splash pads. 

**Orginal Datasets**
[Outdoor Pools Dataset](https://open.ottawa.ca/datasets/909df725a735445cbed1ac82f0f9001f_10/explore)
[Outdoor Wading Pools Dataset](https://open.ottawa.ca/datasets/7a66e4301c60460c97f0d7c2830fb855_11/explore?location=45.272344%2C-75.773591%2C1)
[Splash Pads Dataset](https://open.ottawa.ca/datasets/1bb9d909a84540cf99e2ed2106c7cad5_18/explore?location=45.272344%2C-75.773591%2C1)

The way I went about importing this data into Google Sheets was to simply download the CSV files of each dataset, press *File>Import>Upload*, then select my first CSV file, followed by *"insert new sheet(s)"*, kept *"detect automatically"* for the separator, and repeated this for each file. 

***[Link to my Public Spreadsheet](https://docs.google.com/spreadsheets/d/1G--GYr34FMQL5pQnfjmRqWdeEZHLuaQNkMd06S7RDMU/edit?usp=sharing)***<br>
![](Screenshot-2026-10-30225910.png)
*Figure 1: Screen capture of my dataset just after importation*

**Observations**
All together the files hold 225 rows: 11 outdoor pools, 53 wading pools, and 161 splash pads. Outdoor pools contains 23 columns, wading pools 41, and splash pads 25. The data itself isn't very clean, with almost every text column having a french equivalent (ex. NAME_FR, ADDRESS_FR), and a lot of columns are just empty.

- The "OPEN" column, which is shared by all 3 data sets, is a nominal (binary) variable which in this case is stored bilingually as a "yes/oui", "no/non". All 11 of the outdoor pools are listed as "no/non" which as somewhat surprising as this data was last modified in late august and early september.
- "PARKADDRESS", which is also shared by all 3 data sets, is also a nominal text variable. When a former municipality is listed it is placed at the end of the address (ex. ...Kanata, ...Gloucester), but 43 of the 161 splash pad addresses leave that part out.
- The "X" and "Y" columns are continuous variables that are measured in metres in the Web Mercator system, for example, "X -8,424,589, Y 5,657,945" instead of longitude and latitude. 

Based on the raw data I think it goes without saying that the type of facility somebody can access highly depends on where they live, as a lot of wading pools cluster more towards the downtown area while splash pads and outdoor pools city further out and around the city.

## 2. Understanding Data

### 2.1. VIMO Analysis



Support your claims by citing relevant sources. Please follow [APA guidelines for in-text citations](https://apastyle.apa.org/style-grammar-guidelines/citations).

**For example:**

As seen in Bounegru & Gray (2011), a data visualization should be clear...

### 2.2. Cleaning Data



### 2.3. Analyzing Data



**This section should include a screen capture of your pivot table, like so:**

![](pivot-table-screen-capture.png)<br>
*Figure 2: This pivot table shows...*

**This section should also include a screen capture of your exploratory chart, like so:**

![](chart-screen-capture.png)<br>
*Figure 3: This exploratory chart shows...*

## 3. Delivering Data
I still need to look at population by neighbourhood in Ottawa and dive deeper into the Neighbourhood Equity Index (NEI) scores to see if there is any correlation to find there.

A possible interviewee could include someone from the city of Ottawa parks and recreation that manages or oversees water facility related issues. It could also possibly be a councillor or representative from a ward that could give more insight into these water facilities.

## 4. References
City of Ottawa. (2021). Parks and recreation facilities master plan. https://documents.ottawa.ca/sites/default/files/MasterPlan_parks_and_facilities-en.pdf

City of Ottawa. (2022). Splash pads / Aire de jeux d'eau [Data set]. Open Ottawa. https://open.ottawa.ca/datasets/1bb9d909a84540cf99e2ed2106c7cad5_18/explore

City of Ottawa. (2022). Outdoor pools / Piscines extérieure [Data set]. Open Ottawa. https://open.ottawa.ca/datasets/909df725a735445cbed1ac82f0f9001f_10/explore

City of Ottawa. (2024). Outdoor wading pools / Pataugeoires extérieure [Data set]. Open Ottawa. https://open.ottawa.ca/datasets/7a66e4301c60460c97f0d7c2830fb855_11/explore