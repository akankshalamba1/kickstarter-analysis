# kickstarter-analysis

## Overview of Project

Kickstarter analysis is based on our client Louise, who we helped in starting a crowdfunding campaign to help her fund her play, "Fever". Her estimated budget was over $10,000, she was unsure of what factor she should consider while planning her first fundraiser campaign, so she needed help in analyzing crowdfunding data from 2009 to 2017. Now her play "Fever" came close to her fundraising goal in a very short term. She wants us to analyze how other campaigns did in relation to their launch date and their funding goal.

Our analysis based on data of 4115 crowdfund fundraisers in 22 countries. Dataset is very detailed and contain crowdfunds in various categories such as film and video, food, games, journalism, music, photography, publishing, technology and theater. Data provided various outcome of the crowdfund as well as the goal and pledged amount. In the process of making an analysis based on the data we perform various data interpretation technique, filters and functions on the data to make it readable and easy to understand. 

Microsoft Excel was used as the main tool to analyze the data for this project. The data file for this project is Kickstarter_challenge and could be reviewed below:

[kickstarter_challenge](/kickstarter_challenge.zip)

### Purpose 

Purpose of Analysis is to provide a deeper understanding of the various factors responsible for success of various crowdfund fundraising campaigns. For this project we will only be considering two aspects of comparison of various plays that are Outcome based on the Launch Date and Outcome based on Goals.

## Analysis and Challenges

The analysis is based on a large chunk of data with 4115 rows and 12 columns. In the beginning of the analysis it was tough to analyze or visualize the data to make a recommendation. We had to apply various techniques to make the data understandable. We went though following steps:

#### Filtering and Formatting Data

Various filters were applied to the data to make it more organized and filter tab was added to each column so its easier to look-up any specific details that need to be pulled up by Louise. 
Its done as follows:

Highlight the top row of the file and select Sort & Filter option from the right corner of the toolbar then choose Filter. Filters will appear on all the column headings.

![Test Image](/Screenshot/Fiter.png)

---
**Formatting**: We used Conditional formatting to the data file twice by highlighting the specific column we need to be color coded then, go to the conditional formatting icon on the toolbar then select highlight text rules then select equal to from the dropdown menu a pop up window will appear on the screen then type the outcome then select custom color for that outcome. Screenshot of the process attached below:

![Test Image](/Screenshot/Formatting.png)

---
![Test Image](/Screenshot/Formatting2.png)
 
>Conditional formatting provide a visual sorting to the outcomes and thus is a great way for the viewer to find information at a glance.

#### Performing calculations

Few calculations were performed with the data to make data tell a story of various campaigns:
1. ##### Percentage Funded: Percentage funded was calculated by dividing *Pledge* amount to *Goal* amount multiple by 100, to get whole numbers we used Round function to 0 decimal places. The formula is a follows:

> =ROUND(E2/D2*100,0)

2. ##### Average Donations: Average donations were calculated by dividing the Pledged amount to backers count, round function was used to round it off to 2 decimal places. 

> =(ROUND(E2/L2,2)

<sub>As some of the pledge amount are 0 for the cancelled campaigns an Error message appeared for some of the cells, to avoid that we used IFERROR function and set the error value to "No Backers. The formula is as follows</sub> 
 
> =IFERROR(ROUND(E3/L3,2),"No backers")
 
#### Date calculations
The original data had some information that was not in readable form like the Launch and the Deadline dates. They are recorded in Unix timestamps. By applying the formula the dates were convert to actual dates.

 >=(((J2/60/60/24)+DATE(1970,1,1)))
 
 <Sub>Unix timestamps measure time as the number of seconds since midnight of January 1, 1970</sub>
 
Year function was applied to just take the years from the launch date. The formula is as follows:
 >YEAR(Launch_date_column)
All these steps were followed to analyze the data.
 
### Analysis of Outcomes Based on Launch Date

#### Pivot table to provide data clarity
Analysis based on the Launch date included creating a pivot table on a new sheet labeled "Theater Outcomes by Launch Date". Pivot table was filtered based on "Parent Category" and "Years" with "Outcome" on columns and "Date" on rows and "count of outcomes" on the Value. It provide a deeper understanding of theater outcomes for various months in a very simplified manner and we could easily observe that Month of May had that most successful theater shows with 111 successful shows out of 166 total shows.  

#### Steps to create a pivot table
Following are the steps to create a pivot table:

- click "Insert" on the toolbar followed by selecting "PivotTable" on toolbar
- A dialog box will appear "PivotTable from table or range" it by default selects the whole table, choose "New Worksheet" and click "Ok"

![Test Image](/Screenshot/pivot_table0.png)
---
A Task panel will appear on the right-hand side of the new worksheet named "PivotTable Fields" rows, columns, filters and values can be set by dragging the headings to the respective field. 
As shows below:

![Test Image](/Screenshot/pivot_table1.png)

To make more detailed analysis we arranged the column labels in ascending order to show the successful outcome first and we only considered on successful, failed and canceled outcomes. The tables appears as follows:

![Test Image](/Screenshot/pivot_table2.png)

#### Line chart to visualize
In order to get a clear picture of how the Launch months effect the outcomes we created a line chart by highlighting the pivot table and selecting "PivotChart" from the toolbar on the top of the screen it will show up a dialog box with a suggested chart and all charts options from the pivot table data to choose from. The dailog box looks like 

![Test Image](/Screenshot/Line_chartdate.png)

Click "Ok"
Then the chart appears on the screen. For this dataset the line chart with theater outcomes based on the launch data looks like the following:

![Test Image](/Resources/Theater_outcome_vs_Launch.png.png)

### Analysis of Outcomes Based on Goals

#### Data divided by Ranges
To Analyze the outcome based on the goals, we created a column with Ranges of Goals in a new worksheet from less than 1000 to greater than 50000 to dissect the outcome data even further based on Louise's instructions, various goal ranges are separated by successful, failed and canceled outcomes for only "plays" subcategory. 
The column looks like following picture:

![Test Image](/Screenshot/Goal_range.png)

#### Outcome for each goal range
To calculate the data for Number Successful, Number Failed and Number Canceled plays in the particular range we used the COUNTIFS function. The following formula has to be changed for different ranges:

>=COUNTIFS('Kickstarter sheet'!$F:$F,"Successful",'Kickstarter sheet'!$D:$D, "<1000",'Kickstarter sheet'!$R:$R, "Plays")

#### Percentage of Successful, failed and canceled plays
Once we receive the outcome of all the three columns, create a new column titled "Total Projects" by adding all outcomes for each range. To evaluate the success rate of the plays by the goal range we calculated the percentage of each outcome by dividing the number successful, Failed, Canceled by Total project multiply by 100. The table will look like this:

![Test Image](/Screenshot/goal_table.png)

#### Line chart
To make the data visually presentable and to back up our recommendation we created a line chart based on the data.
Attached is the outcome based on goal line chart:

![Test Image](/Resources/Outcomes_vs_Goals.png.png)

### Challenges and Difficulties Encountered

Following are some of the difficulties Encountered while working on this project:
- **Unclear Data**: At first glance the data file appeared to alien, it take time get familiarize with the data as well as we cant use the data in the original form to base our analysis on. Data values such as Launch and Deadline is not easily interpreted as dates. For someone new to excel it will take them a while to point it out, as well as category and subcategory are combined into one set, which make the data complicated
- **Huge dataset**: Grasping the huge amount of data in one go is really tedious task. It could be overwhelming for someone like Lousie who is new to excel. Data could have been more organized and shrunk.
- **Use of multiple constrains**: Data range is too wide spread, data from 2009 to 2017 compressed together, with multiple countries and currencies at the same time.

#### Overcoming difficulties
To overcome the difficulties of data we used filters, formatting tools and created simplified outlook of the Excel sheet by creating columns like "Parent Category" and "Subcategory", as well as "Date Creation Conversion" and "Date Ended Conversion". By using features like pivot table and pivot chart we were able to narrow down the data which is important for this analysis

## Results

#### What are two conclusions you can draw about the Outcomes based on Launch Date?

By Analyzing the outcomes based on the Launch date we were able to focus on which time of the year is best to do theater shows. Some conclusions draws by this analysis are as follows:
- **Most successful month**: Based on our observation it is clear that the month of "May" has the most successful plays as compared to other months. Maximum failed theatricals are in the month of May as well. It provides Louise a clear picture that for her next plays she should prefer doing them in the months of May June and July as they turned out to be more successful as compared to the other months.

- **Trend in the success rate based on the months**: If we look at the line chart based on the Theater outcomes based on launch date as linked above in the Analysis tab it appears that the success rate follows a trend which increases in the beginning of the year and reach its peak in the month of May and then starts to fall back and reach its lowest in the month of December. A lot of constrains could have resulted this. There is a possibility that as month of May, June and July are spring months, people like to go out to view theater shows more often as compared to cooler months like November and December where shows are less successful. Louise should surely keep weather and other constrain that could effect people going out to watch plays in mind while planning for her next plays.

#### What can you conclude about the Outcomes based on Goals?

Analysis of Outcome based on Goals we could conclude that the most number of plays have goal amount between $1000 to $4999, around 388 plays out of 534 were successful. The plays with goal amount Less than $1000 has the most percentage of successful outcomes with 75.81% of plays being successful. We can observe from the line chart of Outcomes based on goals attached in the Analysis tab that as the dollar amount of the goals increase the plays tend to be more Failed than Successful out of the total Projects.

So Louise, should Try to keep the anticipated Goals for her future plays to be under $4999 as it will have the least probability of getting failed based on the outcomes of other crowdfunds. 

#### What are some limitations of this dataset?

- **Data Modelling is tough**: Modelling this huge amount of data is a tedious task at first. I could only be possible by converting the data in a human readable form, as well as data is not very systematic with data from different countries, currencies and vast time period of 2009 to 2017 it makes it hard to drive a accurate conclusion.
- **External factors affecting outcome not considered**- As no activity is one in isolation, so there are so many external factors that could affect or manipulate the outcomes. There could be so many constrains responsible for the success and failure of a play such as Economic factors, currency fluctuation, weather condition and Government stability of the country at that time of the year all these are the external factors that could affect the results or outcomes that are not taken into consideration at all.
- **Excessive information**: Dataset is providing so much of the information, some of it is irrelevant to our analysis like the Staff_pick and Spotlight those information could be eliminated for this Analysis

#### What are some other possible tables and/or graphs that we could create?
Following are some of the charts that could be possibly created:
- *Bar Chart of Outcomes*: Bar chart could provide a much clear view of each outcome based on every month

![barchart_outcome](https://user-images.githubusercontent.com/111251560/187781841-d0cc5028-710d-4cc0-bb1c-2a4a37fe107a.png)

- *Vlookup table for the Louise's top 5 favorite plays*: It provide a drill down overview of just the 5 plays

![Vlookup](https://user-images.githubusercontent.com/111251560/187781850-4f38d86b-f854-4904-ad6b-cdf55870ba3d.png)

- *Pie-chart*: For showing the data of small data set pie chart could be a great way to represent which play did better than the other based on the pledged amount

![piechart](https://user-images.githubusercontent.com/111251560/187781843-af4ae7d0-8205-4fb1-8d68-32bbc16cb52b.png)

- *Insight of US theater industry*: This bar chart shows the data specific to US theaterical based on the Parent Categories

![UStheater](https://user-images.githubusercontent.com/111251560/187781849-8e16412f-91cf-4eb7-a279-f689a44032b7.png)

- *US Plays outcome based on Subcategories*: As Louise is considering US her potential market then she will need an insight of Plays outcome based on the plays specific  to US
![USplay](https://user-images.githubusercontent.com/111251560/187781846-7436ba5b-50ed-4c2d-9ddb-9b68687e4f8d.png)
