# Kickstarting with Excel

## Analysis of Kickstarter campaigns to aid in planning and launching a new successful campaign

### Purpose
The purpose of this research is to analyze previous Kickstarter theatre campaigns to identify trends in launch date and goal amounts in order to guide the successful launch of a new project. 

## Analysis and Challenges
A dataset of approximately 4000 Kickstarter campaigns was used to filter campaigns by launch date, category, goal, and outcome. 
Microsoft excel was used to filter and analyse the data. 

Extracting the year from the date conversion column was difficult as simply using the Excel function =YEAR() did not work. This was likely becasue the Date conversion column was not in the proper format for the =Year() function to work. Ultimately the =TEXT(T2,"YYYY") function was used.  

![excel_year_extract](https://github.com/andrej-arsovski/kickstarter-analysis/blob/master/resources/excel_year_extract.png)

A pivot table was used to examine the effect on launch date on outcome. Data was filtered on Parent Category and years. Outcomes was used as "legend" or rows, Date created conversion was used as "axis" or columns, with the "quarter" and "years" removed from the field (see image below). "Outcomes" were used in the Values field.

![launch_pivot](https://github.com/andrej-arsovski/kickstarter-analysis/blob/master/resources/Launch_pivot.png)

To determine whether the goal amount had an effect on campaign success the raw kickstarter data was used to filter out only the subcategory "plays" and those were filtered by the goal amount and whether it was successful. The campaigns were binned in 12 categories ranging from less that 1000, then in 5000 dollar bins until 50000. Campigns with goal amounts greater than 50000 comprised the last bin. The Excel function =COUNTIFS was used to count the number of successful, failed, and canceled projects. The percent of each was determined using these numbers.

example:

=COUNTIFS(kickstarter!$D:$D,">=1000",kickstarter!$D:$D,"<4999",kickstarter!$F:$F,"successful",kickstarter!$R:$R,"plays")

![countifs_table](https://github.com/andrej-arsovski/kickstarter-analysis/blob/master/countifs_table.png)

  
### Analysis of Outcomes Based on Launch Date

There is a clear trend in the outcome of a campaign depending on the launch date. There is a large peak in the number of successful campaigns launched in May (111) compared to 52 failures. The number remains high in June with 100 successful campaigns and 49 failed. Then follows and sustained drop off in the number of successful campaigns with the lowest in December (37). The nubmer of cancelled campaigns never exceeds 10 in any month, suggesting theatre people are a determined bunch. There may be a number of reasons for this trend. It may be that theatre season is in the winter and so the summer is when backers are at maximum withdrawal and are eager to support the arts. More in depth research is needed to explain these trends.

![theater_outcomes_vs_launch](https://github.com/andrej-arsovski/kickstarter-analysis/blob/master/resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals

Here the majority of the data falls within the first 4 bins, or categories. The majority of campaigns ask for less that 15000. Therefore we focus out analysis here as the results in the higher categories are based on sample sizes that are much too small to be significant and are easily skewed by outliers. The highest percentage of successful plays have goals of less than $1000 or between $1000 and 4999. They are successful 76 and 73% of the time respectively. The success rate decrease after that to 55% in the $5000 to $9999 range and 45% in the $20000 to $24999 range. The data becomes too erratic after that, again likely to the small sample sizes.

![outcomes_vs_goals](https://github.com/andrej-arsovski/kickstarter-analysis/blob/master/resources/Outcomes_vs_Goal.png)

### Challenges and Difficulties Encountered

Other than the difficulty with using the =Years() function in Excel the analysis was straight forward.

## Results
Launch
  - Launch should be aimed for May or June.
  - Campaign should not be launched in November or December.  
  
Goal
  - The majority of plays ask for less than $20000.
  - Plays are most successful when they ask between $1000-$4999.
## Caveats and Additional analyses
- We do not know if this data set includes all campaigns in Kickstarter history. Additionally there are other crowdfunding platforms not included in this set. Additionally, applications for funding from government organizations, non profits or other sources may be even more successful. Experienced goups may be more successful at creating Kickstarter campaigns, we do not have data on whether these campaigns were made by first timers or experienced fundraisers.

- Additional analyses could be done looking at whether being a "staff pick" influences the outcome and whether certain countries are more amenable to theater productions. # An analysis of Kickstarter Campaigns
Uncovering and reporting trends in Kickstarter data to maximize chances of a succesful theatre campaign


