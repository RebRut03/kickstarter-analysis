# **Kickstarter Campaign Funding Analysis - To Pay or Not to Play, That is the Questions?**

## **Overview of Project**

 - ### Project Purpose
   - The purpose of this project is to analyze kickstarter campaign data for an emerging playwright Louise. The goal of  this project is for Louise to gain a better understanding of different campaigns’ success rates in relation to their launch dates and their funding goals in order for her to make an informed decision on her next steps. 
   - In this report, I will focus on how successful theater campaigns were based on their launch dates, and I will also compare how play campaigns fared based on their associated funding goals.

## **Analysis and Challenges**

 - ### Analysis of Theater Campaign Outcomes Based on Launch Date
   -  The line chart titled "Theater Outcomes Based on Launch Date" below illustrates how successful theater campaings were based on their launch date.
   -  This chart was created by converting the kickstarter campaign data into a pivot table and includes data from 2010 to 2017.  The `Year()` function was utilized to convert the Date Created Conversion column in the kickstarter data to a year column.  
   -  On the x axis you'll notice, the years are grouped by month.  This was accomplished by grouping the dates in the pivot table by month and represents the campains' launch month.. 
   -  The y axis shows the number of successful, failed, and canceled theater campains. 

   ![Theater_Outcomes_vs_Launch](Resources/Theater_Outcomes_vs_Launch.png)
    For further details on how analysis was performed, please see source spreadsheet. 
    [Kickstarter_Challenge](Kickstarter_Challenge.zip)

 - ### Analysis of Play Campaign Outcomes Based on Goals
   - The line chart titled "Outcomes Based on Goals" below illustrates how successful play projects were compared to differnt levels of funding goals.
   - This chart was created by converting the kickstarter campaign data into a pivot table.  The `COUNTIFS()` function was used to populate the number of successful, failed and canceled play projects.  The `SUMS()` function was used to come up with a total of the play projects based on the numbers returned by the `COUNTIFS()`.  A percentage was calculated based on the number of succesful, failed and canceled divided by the total projects per funding level. 
   -  The x axis shows the differnt funding goal levels utilized for the sake of this analysis.  
   -  The y axis shows the percentage successful, failed, and canceled play projects based on the goal funding levels.
   
   ![Outcomes_vs_Goals](Resources/Outcomes_vs_Goals.png)
   For further details on how analysis was performed, please see source spreadsheet. 
   [Kickstarter_Challenge](Kickstarter_Challenge.zip)

 - ### Challenges and Difficulties Encountered
   - Being unfamiliar with `COUNTIFS` statements presented a challenge during the course of this analysis. Specifically, I struggled with how to input the higher end of the range.  
     - For example, when trying to calculate, the number of successful, failed and canceled play projects, i initially input `=COUNTIFS(Kickstarter!$D:$D, ">=1000" AND "<=4999" ,Kickstarter!$F:$F, "successful",Kickstarter!$R:$R, "plays")` thinking it would work to use an `AND` function to combine the lower and higher end of the funding range, but I received an error.  
     - Utimatley, I used the following formula and received the apprporiate calculation `=COUNTIFS(Kickstarter!$D:$D, ">=1000",Kickstarter!$F:$F, "successful",Kickstarter!$R:$R, "plays", Kickstarter!$D:$D, "<=4999")`.
   - Also, if someone doing this was unaware of the `YEAR()` and the abiality to group by months in the pivot table for Theater outcomes vs the launch date, that could create issues coming up with the final anlaysis goal of the first exercise.


## **Results**

 - ### Outcomes Based on Launch Date - Theater Campains
   - It is recommended to launch theater campaigns in May and June because these months show to be the highest success rates.
     - May - 111 successful campaigns out of 166 total campains or 67% 
     - June - 100 successful campaigns out of 153 total campaigns or 65%. 
   - 47% of theater campaigns launched in December failed, followed closely by 43% in October, so it is not suggested to launch campaigns in these months.  
   - The cancellations are relatively low comparatively speaking, but the highest cancellation month is January at 7%.
  
 - ### Outcomes Based on Goals - Play Projects
   - It appears that the lower funding goal categories produce a high success rate.  
   - Play campaigns with a goal of less than $1,000 were 76% successful.  Play campaigns with a goal between $1000 and $4,999 were 73% successful.  Though it was out of scope, I calculated the total funding raised between 0 and $4,999 which totaled approximately $1,170,000.
   - Play projects between 35000 and 44999 were 67% successful; however, there were only 9 project included in this funding level and only approximatley $270,000 raised in this funding category.  
   - One thing to note, the percentages are only calculated within each funding level and not over the entirety of the project.  For example Less than 1000 in funding is 75% successful, but it only takes into acccount fuding goals less than 1000 and only makes up 18% (186 of the 1043) of the total play projects.
   - Given the current data, my recomendation would be for Louise to focus her efforts on smaller fudning campaigns.  
   
 - ### Limitations in Dataset
   - Regarding play campaigns and their outcomes based on goals, there is significantly less data from the higher funding campaigns which could limit realiablity of using that data as a sample for that funding level.  Appoximately 85% of the campaign data falls under $10,000; while, only 15% of the campaign data was above $10,000.

 - ### Additional Suggested Tables or Graphs
   - As mentioned previously, in this project, we did not take into account the amount pledged to aid in determining success.  
   - I would recommend adding a box and whisker plot, to compare the distribution of campaign goals and the distribution of total amounts pledged.  This would illustrate measures of central tendency, spread, and identification of outliers to see if the data is skewed in any way.
