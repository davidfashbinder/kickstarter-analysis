# Kickstarting with Excel

## Overview of Project
---
The purpose of this project is to perform further analysis on the Kickstarter data that we gathered for Louise.  Specifically, to determine the following:
---
1. Campaign Outcomes based on their Launch Dates
2. Campaign Outcomes based on their Funding Goals
---
### Purpose
-We will determine if Launch Date and the Funding Goal of a Kickstarter Campaign have any significant bearing on its outcome.  
## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
####It's important to examine the differences in the 3 Outcomes and their trends.  Cancelations were very flat across all months, and Failed Campaigns were relatively flat, with the most being in May (52) and the lowest November (31).  Comparitvely, the range of values for Successful campaigns was much larger.  May (111) and June (100) had significant lifts in successes compared to the other months.  December posted the lowest number of successes (37). 
---
####To determine these outcomes, I utilized a pivot table filtered to only the Theater Category of campaigns.  While I examined data from every year on the dataset, the data was filtered to month of the year in order to make the information more usable for Louise.  The date data also had to be converted to a usable format, which can be seen in the Data Created Conversion column.  The pivot table was then turned into a PivotChart, which mapped the values of the Campaign Outcomes and their frequency against the Months of the year.  
---
![Theater_Outcomes_vs_Launch](https://github.com/davidfashbinder/kickstarter-analysis/blob/master/Theater_Outcomes_vs_Launch.png?raw=true)

### Analysis of Outcomes Based on Goals
---
####With no canceled campaigns from this dataset, we need to examine only Successful and Failed campaigns.  Campaigns under 15000 are more likely to Succeed than those between 15000 and 34999.  There is an improvement in success rate for those campaigns with goals between 35000 and 44999, but then a sharp decline to a 0% success rate at 45000 to 49999.  Less than 20% of campaigns with goals over 50000 have been successful.  
---
####This data was harvested from the dataset using the COUNTIFS function along with multiple criteria.  The formula would check for successful, failed, or canceled from the Outcomes column, and use a fixed crtiera "Plays" from the subcategory column.  Since Louise is only concerned with the success of Plays, this was an appropriate filter.  The data would be filtered yet again by the goal range that we created for this measurement.  The ranges were created in 5000 increments, starting at 1000.  Anything less than 1000 was its own range, and anything more than 50000 was counted together.  Once the COUNTIFS function was successful in getting totals, I performed a simple calculation to display the Percentages of Successful, Failed, and Canceled Campaigns.  
---
![Outcomes_vs_Goals](https://github.com/davidfashbinder/kickstarter-analysis/blob/master/Outcomes_vs_Goals.png?raw=true)
### Challenges and Difficulties Encountered
1. Outcomes Based on Launch Date was very straightforward since it used the PivotTable and PivotChart features of Excel.  Difficulty could arise if improper filters were used on the dataset sheet, or if the incorrect items were set for the rows, columns, and values fields in the Chart Wizard.  
---
2. The Outcomes Based on Goals Analysis added some challenge, due to being unable to simply extend the formulas created to the other columns/rows.  Since each row needed to apply a different Criteria (goal range) to the formula, I still had to visit each cell and update the formula.  
---
I was also concerned since the data set showed 0 Canceled Campaigns, but the PivotTable & Chart used in Part 1 showed several Canceled Campaigns in the data.  Upon examining the differences in the calculations, it was determined that the only Canceled Campaigns were NOT Plays, since the first exercise does not filter the subcategory to plays like the second one does.  
---
When creating the Line Chart for Outcomes Based on Goal, I was struggling to get the values and axis measurements to mirror the example in the Module.  I determined that this was because I was accidentally capturing the column headers in addition to the data range.  Once I eliminated the column headers, the chart looked appropriate.  
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
1. The summer months are best for launching Theater campaigns on Kickstarter, especially May and June.  The latest I would recommend launching a Theater Campaign is July.  
2. Failure of a campaign is largely independent from Launch Date.  
---
- What can you conclude about the Outcomes based on Goals?
1. The best odds for success for any Play Campaign will be if the goal is less than $15000.

- What are some limitations of this dataset?
This data set, while robust, does not speak to any marketing techniques used to gain backers and donations.  It's possible, for example, that a very successful Campaign also invested significant money into Facebook Ads, or an email campaign.  Also, the success of the Kickstarter Campaign does not necessarily mean the production was successfully launched - it simply means the funding goal was achieved for the Kickstarter Campaign.  

- What are some other possible tables and/or graphs that we could create?
1. Outcomes based on Number of Backers
2. Outcomes based on Average Donation
3. Outcome % based on Number of Backers
4. Outcome % based on Average Donation
5. Average Length of Successful Theater Campaigns
