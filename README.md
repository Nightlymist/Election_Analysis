# Election_Analysis

## Overview of Election Audit
In this simulation, I am going to be working with the Colorado board of elections in election audit for U.S congressional precinct. My task for this job is to report the following tasks; total number of votes, total number and percentage of votes for each candidate, and winner of election. The point of the job is to automate the process that could be done in excel but now are using VS Code to do analysis. 

## Election-Audit Results

Election Results
- Total Votes: 369,711

County Votes:
- Jefferson: 10.5% (38,855)
- Denver: 82.8% (306,055)
- Arapahoe: 6.7% (24,801)

Largest turnout: Denver
Candidate number and Percent
- Charles Casper Stockham: 23.0% (85,213)
- Diana DeGette: 73.8% (272,892)
- Raymon Anthony Doane: 3.1% (11,606)

Winning  
- Winner: Diana DeGette
- Vote Count: 272,892
- Winning Percentage: 73.8%

### Vote calculation

![Screen Shot 2023-01-15 at 8 16 02 PM](https://user-images.githubusercontent.com/110945895/212579068-a913dae9-2d85-4291-8d69-c6ccfa2e1e1b.png)

Figure 1. Creating lists and dictionary with tracking candidate and county. 

![Screen Shot 2023-01-15 at 8 21 49 PM](https://user-images.githubusercontent.com/110945895/212579560-a774a0cf-f0ee-499a-ada3-75414210931a.png)

Figure 2. Read csv and convert csv into a list of dictionaries and adding county name

![Screen Shot 2023-01-15 at 8 24 52 PM](https://user-images.githubusercontent.com/110945895/212579779-bd7f5d60-da67-48f8-84d9-9d4fec3e9dbc.png)

Figure 3. Writing loop for county
    
### Candidate Calculation

![Screen Shot 2023-01-15 at 8 26 01 PM](https://user-images.githubusercontent.com/110945895/212580065-b8b36e09-3691-4c5b-b73a-6bba0c418d08.png)

Figure 4. Candidate Calculations and printing the winner candidate
        
## Election-Audit Summary
There are other ways that this code could be used for other election analysis in different states as well as electoral college vote. Replace data file with different election count file. This is making the vote count to be automatic. This could be used for any election in the future that uses the popular vote. There could be modification with to use this for the electoral college vote. This would be calculate the popular party that would elect the President. Instead of each candidate name being presented, it could be each party that could be calculated for the winning party.


