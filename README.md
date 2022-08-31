# kickstarter-analysis

## Overview of Project

Kickstarter analysis is based on our client Louise, who we helped in starting a crowdfunding campaign to help her fund her play, "Fever". Her estimated budget was over $10,000, she was unsure of what factor she should consider while planning her first fundraiser campaign, so she needed help in analzing crowdfunding data from 2009 to 2017. Now her play "Fever" came close to her fundraising goal in a very short term. She wants us to analyze how other campaigns did in relation to their launch date and their funding goal.

Our analysis based on data of 4115 crowdfund fundraisers in 22 countries. Dataset is very detailed and contain crowdfunds in various categories such as film and video, food, games, journalism, music, phtography, publishing, technology and theater. Data provided various outcome of the crowdfund as well as the goal and pledged amount. In the process of making an analysis based on the data we perform various data interpretaion technique, filters and functions on the data to make it readable and easy to understand. 

Microsoft Excel was used as the main tool to analyze the data for his project. The data file for this project is Kickstarter_challenge and could be reviewed below:

*ADD LINK TO EXCEL*

### Purpose 

Purpose of Analysis is to provide a deeper understanding of the various factors responsible for success of various crowdfund fundraising campaigns. For his project we will only be considering on two aspects of comparison of various plays that are Outcome based on the Launch Date and Outcome based on Goals.

## Analysis and Challenges

The analysis is based on a large chunk of data with 4115 rows and 12 columns. In the beggining of the analysis it was tough to analyze or visualize the data to make a recommendation. We had to apply various techniques to make the data understandable. We went though following steps:

#### Filtering and Formatting Data

Various filters were applied to the data to make it more organized and filter tab was added to each column so its easier to look-up any specific details that need to be pulled up by Louise. 
Its done as follows:

Highlight the top row of the file and select Sort & Filter option from the right corner of the toolbar then choose Filter. Filters will appear on all the column headings.

*Add Screenshot*

**Formatting**: We used Conditional formatting to the data file twice by highlighting the specific column we need to be color coded then, go to the conditional formatting icon on the toolbar then select highlight text rules then select equal to from the dropdown menu a pop up window will appear on the screen then type the outcome then select custom color for that outcome. Screenshot of the process attached below:
 *Screenshot 1*
 
 *Screenshot 2*
 
>Conditional formating provide a visual sorting to the outcomes and thus is a great way for the viewer to find information at a glance.

#### Performing calculations

Few calculations were performed with the data to make data tell a story of various campaigns:
1. ##### Percentage Funded: Percentage funded was calculated by dividing *Pledge* amount to *Goal* amount multiple by 100, to get whole numbers we used Round function to 0 decimal places. The formula is a follows:

> =ROUND(E2/D2*100,0)

2. ##### Average Donations: Average donations were calculated by dividing the Pledged amount to backers count, round function was used to round it off to 2 decimal places. 

> =(ROUND(E2/L2,2)

<sub>As some of the pledge amount are 0 for the cancelled campaigns an Error message appeared for some of the cells, to avoid that we used IFERROR function and set the error value to "No Backers"
The formula is as follows 
 
> =IFERROR(ROUND(E3/L3,2),"No backers")
 
#### Dates calculations

 
### Analysis of Outcomes Based on Launch Date

### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
