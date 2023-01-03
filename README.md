# Election_Analysis
For this simulation, the Colorado board of elections will do an election audit for the U.S congressional precint. Currently the votes have been put onto csv file and could be calculated through excel. The problem is that the process of the calculations would take a long time to get what is desired through excel. Through python, the process could be automated and used for other elections. Shown below are the results of the election audit as well as the code preformed to get the results.


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

Initialize a total vote counter.

total_votes = 0

Candidate Options and candidate votes.

candidate_options = []

candidate_votes = {}

1: Create a county list and county votes dictionary.

county_list = []

county_votes = {}

Track the winning candidate, vote count and percentage

winning_candidate = ""

winning_count = 0

winning_percentage = 0

2: Track the largest county and county voter turnout.

county_largest = ""

county_turnout = 0

Read the csv and convert it into a list of dictionaries
with open(file_to_load) as election_data:
    file_reader = csv.reader(election_data)
    Read the header
    header = next(file_reader)

    For each row in the CSV file.
    for row in file_reader:
        Add to the total vote count
        total_votes += 1
        Get the candidate name from each row.
        candidate_name = row[2]
        3: Extract the county name from each row.
        county_name = row[1]
        If the candidate does not match any existing candidate add it to
        the candidate list
        if candidate_name not in candidate_options:
            Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)
            And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0
        Add a vote to that candidate's count
        candidate_votes[candidate_name] += 1
        4a: Write an if statement that checks that the
        county does not match any existing county in the county list.
        if county_name not in county_list:
            4b: Add the existing county to the list of counties.
            county_list.append(county_name)
            4c: Begin tracking the county's vote count.
            county_votes[county_name] = 0
        5: Add a vote to that county's vote count.
        county_votes[county_name] += 1
Save the results to our text file.

with open(file_to_save, "w") as txt_file:

    Print the final vote count (to terminal)
    
    election_results = (
    
        f"\nElection Results\n"
        
        f"-------------------------\n"
        
        f"Total Votes: {total_votes:,}\n"
        
        f"-------------------------\n"
        
        f"County Votes:\n")
    print(election_results, end="")
    Print results in txt file
    txt_file.write(election_results)
    
### Candidate calculation
    6a: Write a for loop to get the county from the county dictionary.
    for county_name in county_votes:
        6b: Retrieve the county vote count.
        votes_count = county_votes[county_name]
        6c: Calculate the percentage of votes for the county.
        vote_percentage_county = float(votes_count) / float(total_votes) *100
        county_results = (
            f"{county_name}: {vote_percentage_county:.1f}% ({votes_count:,})\n")
        6d: Print the county results to the terminal.
        print(county_results)
        6e: Save the county votes to a text file.
        txt_file.write(county_results)
        
### Largest county results
        6f: Write an if statement to determine the winning county and get its vote count.
        if (votes_count > county_turnout) and (vote_percentage_county > winning_percentage):
            county_turnout = votes_count
            winning_percentage = vote_percentage_county
            winning_county = county_name
    7: Print the county with the largest turnout to the terminal.
    winning_county_summary = (
    
        f"-------------------------\n"
        
        f"Largest turnout: {winning_county}\n"
        
        f"-------------------------\n")
        
    print(winning_county_summary)
    8: Save the county with the largest turnout to a text file.
    txt_file.write(winning_county_summary)
    
### Candidate Calculation

Reset winning percentage

    winning_percentage = 0
    
    Save the final candidate vote count to the text file.
    
    for candidate_name in candidate_votes:
    
        Retrieve vote count and percentage
        
        votes = candidate_votes[candidate_name]
        
        vote_percentage = float(votes) / float(total_votes) * 100
        
        candidate_results = (
        
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
            
        Print each candidate's voter count and percentage to the terminal.
        
        print(candidate_results)
        
        Save the candidate results to our text file.
        
        txt_file.write(candidate_results)
        
### Winning Candidate Calculation

Reset winning percentage

    winning_percentage = 0
    
    Save the final candidate vote count to the text file.
    
    for candidate_name in candidate_votes:
    
        Retrieve vote count and percentage
        
        votes = candidate_votes[candidate_name]
        
        vote_percentage = float(votes) / float(total_votes) * 100
        
        candidate_results = (
        
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
            
        Print each candidate's voter count and percentage to the terminal.
        
        print(candidate_results)
        
        Save the candidate results to our text file.
        
        txt_file.write(candidate_results)
        
## Election-Audit Summary
There are other ways that this code could be used for other election analysis in different states as well as electoral college vote. Replace data file with different election count file. This is making the vote count to be automatic. This could be used for any election in the future that uses the popular vote. There could be modification with to use this for the electoral college vote. This would be calculate the popular party that would elect the President. Instead of each candidate name being presented, it could be each party that could be calculated for the winning party.


