**November 5th 2026**<br>
**MPAD2003A Introductory Data Storytelling**<br>
**Alexander Balitsky**<br>
**Presented to Jean-Sébastien Marier**<br>

# Deliverable 2: Exploratory Data Analysis (EDA)

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

For this VIMO analysis, I decided to focus more on the variables previously discussed, the OPEN, PARKNAME/ADDRESS, and X/Y. Mostly because these display whether or not a water facility is open and where it sits geographically, which are the most important things to know for my story.

**Valid**
The "FACILITYID" variable is unique in all 3 files, and every single "X" and "Y" point falls inside of Ottawa.

**Invalid**


**Missing**
17 splash pads and 6 wading pools have no former municipality in either address field. The Miikana Park splash pad is marked as "FUTURE" in the "OPEN" column. "LINK_DESCRIPTION" and "LINK_DESCRIPTION_FR" are both empty across all datasets, "CREATED_DATE" is partially filled out in the splash pads dataset (missing 107 entries), and completely empty in the others. "CLASS" is also entirely empty in the splash pads dataset.

**Outliers**


Support your claims by citing relevant sources. Please follow [APA guidelines for in-text citations](https://apastyle.apa.org/style-grammar-guidelines/citations).

**For example:**

As seen in Bounegru & Gray (2011), a data visualization should be clear...

### 2.2. Cleaning Data
- The first thing I did was combine all three datasets into one combined dataset while keeping the shared/relevant columns only (TYPE, PARKID, FACILITYID, PARKNAME, ADDRESS, PARKADDRESS, OPEN, ACCESSIBLE, X, Y, NOTES, & MODIFIEDDATE) and deleting the rest.
- Right after that, I spaced out the columns to improve legibility. 
- Capitalized "TYPE" from "Type" to match the rest of the columns. 
- The next thing I did was use the find and replace tool to remove all French translations and just keep the English ones (yes/oui to yes, no/non to no) as this isn't really needed for my analysis. 
- Seeing as "ADDRESS" and "PARKADDRESS" were basically the same thing, except "PARKADDRESS" tended to be more accurate, I removed the "ADDRESS" column.
- Similarly, I found the "NAME" column to be rather irrelevant as it would either just list the "TYPE" on its own or in combination with the "PARKNAME" column, so removing it was the most resonable option.
- Added underscores (_) to indicate spaces between column titles as some had them but some didn't, just to keep the formatting consistant.
- Bolded column titles to visually seperate them from the data itself.
- Line 160 of the splash pads dataset had a formatting error that caused it to take up 2 rows, so I fixed that.


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

After a bit of research, some sources that could possibly help me provide more context to my story would include:
- The City of Ottawa's parks and recreation facilities master plan (City of Ottawa, 2021). 
- 

## 4. References
City of Ottawa. (2021). Parks and recreation facilities master plan. https://documents.ottawa.ca/sites/default/files/MasterPlan_parks_and_facilities-en.pdf

City of Ottawa. (2022). Splash pads / Aire de jeux d'eau [Data set]. Open Ottawa. https://open.ottawa.ca/datasets/1bb9d909a84540cf99e2ed2106c7cad5_18/explore

City of Ottawa. (2022). Outdoor pools / Piscines extérieure [Data set]. Open Ottawa. https://open.ottawa.ca/datasets/909df725a735445cbed1ac82f0f9001f_10/explore

City of Ottawa. (2024). Outdoor wading pools / Pataugeoires extérieure [Data set]. Open Ottawa. https://open.ottawa.ca/datasets/7a66e4301c60460c97f0d7c2830fb855_11/explore