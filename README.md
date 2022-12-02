# Election_Analysis: Overview of Election Audit: The purpose of this challenge was to provide the audit of election results among three different counties. This challenge was to extract the following basic information about elections.
    Total votes
    Candidates names who participated in election.
    Total votes each candidate received.
    Percentage of votes each candidate received.
    Winner of the election.
# Resources: Election_Analysis
# Code Language: Python

*  There were 369711 total votes cast in the elections.
# Each county vote turnout was:
County Votes:
--- Jafferson = 38,855 with (10.5%)
--- Denver = 306,055 with (82.8%)
---Arapahoe = 24,801 with (6.7%)
# County with largest number of vote: Denver with 82.8% of votes.

# Total votes each candidate received in the elections:

*  Charles Casper Stockham received 85,213 votes with 23.0%
*  Diana DeGette received 272,892 votes with 73.8%
*  Raymon Anthony Doane received 11,606 votes with 3.1%
# Candidate who won:
* Diana DeGette who received 272,892 votes with 73.8% of votes won the election.

# Election_Audit Summary: This election analysis chanllenge is to provide the overview of election results for three different couties and to provide the following information: 
        * Total votes turnout.
        * Each county votes.
        * Each Candidates votes and their percentages
        * Winning conty of the election.
        * Winning candidate of the election.
 All information is based on the election data csv file.
 Following code is used to extract the above results.
 
 
 # Code Used to get results:
 
  # -*- coding: UTF-8 -*-
"""PyPoll Homework Challenge Solution."""

# Add our dependencies.
import csv
import os

# Add a variable to load a file from a path.
file_to_load = os.path.join("election_results.csv")
# Add a variable to save the file to a path.
file_to_save = "election_data.txt"
# Initialize a total vote counter.
total_votes = 0

# Candidate Options and candidate votes.
candidate_options = []
candidate_votes = {}

# 1: Create a county list and county votes dictionary.
county_votes = {}
county_location = ["Jafferson", "Denver", "Arapahoe"]



# Track the winning candidate, vote count and percentage
winning_candidate = ""
winning_count = 0
winning_percentage = 0

# 2: Track the largest county and county voter turnout.
largest_county = ""
largest_turnout = 0
winning_percentage = 0



# Read the csv and convert it into a list of dictionaries
with open(file_to_load) as election_data:
    reader = csv.reader(election_data)

    # Read the header
    header = next(reader)

    # For each row in the CSV file.
    for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1

        # Get the candidate name from each row.
        candidate_name = row[2]

        # 3: Extract the county name from each row.
        county_name = row[1]


        # If the candidate does not match any existing candidate add it to
        # the candidate list
        if candidate_name not in candidate_options:

            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

        # Add a vote to that candidate's count
        candidate_votes[candidate_name] += 1

        # 4a: Write an if statement that checks that the
        # county does not match any existing county in the county list.
        if county_name  not in county_name:



            # 4b: Add the existing county to the list of counties.
            county_location.append (county_name)


            # 4c: Begin tracking the county's vote count.
            county_votes[county_name] = 0


        # 5: Add a vote to that county's vote count.
        county_votes[county_name] += 1



# Save the results to our text file.
with open(file_to_save, "w") as txt_file:

    # Print the final vote count (to terminal)
    election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"County Votes:\n")
    print(election_results, end="")

    txt_file.write(election_results)

    # 6a: Write a for loop to get the county from the county dictionary.
    for county_name in county_votes: 

        # 6b: Retrieve the county vote count.
        cvotes = county_votes.get(county_name)
    

        # 6c: Calculate the percentage of votes for the county.
        cvote_percentage = (float(cvotes)/float(total_votes))*100


         # 6d: Print the county results to the terminal.
        county_results = (
            f"{county_name}: {cvote_percentage:.1f}% ({cvotes:,})\n")
        print(county_results)

         # 6e: Save the county votes to a text file.
        txt_file.write(county_results)

         # 6f: Write an if statement to determine the winning county and get its vote count.
        if (cvotes > largest_turnout) and (cvote_percentage > winning_percentage):
            largest_turnout = cvotes
            largest_county = county_name

        # 7: Print the county with the largest turnout to the terminal.
    largest_county_summary = (
        f"---------------------\n"
        f"largest_county turnout: {largest_county}\n"
        f"----------------------\n")
    print(largest_county_summary)



    # 8: Save the county with the largest turnout to a text file.
    txt_file.write(largest_county_summary)


    # Save the final candidate vote count to the text file.
    txt_file.write("final_candidate_summary")
    for candidate_name in candidate_votes:

        # Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = (float(votes) / float(total_votes)) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")

        # Print each candidate's voter count and percentage to the
        # terminal.
        print(candidate_results)
        #  Save the candidate results to our text file.
        txt_file.write(candidate_results)

        # Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

    # Print the winning candidate (to terminal)
    winning_candidate_summary = (
        f"-------------------------\n"
        f"Winner: {winning_candidate}\n"
        f"Winning Vote Count: {winning_count:,}\n"
        f"Winning Percentage: {winning_percentage:.1f}%\n"
        f"-------------------------\n")
    print(winning_candidate_summary)

    # Save the winning candidate's name to the text file
    txt_file.write(winning_candidate_summary)
    
    # Results Summary:
    
   ![Screenshot_20221201_083423](https://user-images.githubusercontent.com/112978144/205221548-40f6cedd-50f1-426d-ab7c-084e65761a5f.png)
   
 
    
    
    
Election Results
-------------------------
Total Votes: 369,711
-------------------------

County Votes:
Jefferson: 10.5% (38,855)
Denver: 82.8% (306,055)
Arapahoe: 6.7% (24,801)
---------------------
largest_county turnout: Denver
----------------------
final_candidate_summaryCharles Casper Stockham: 23.0% (85,213)
Diana DeGette: 73.8% (272,892)
Raymon Anthony Doane: 3.1% (11,606)
-------------------------
Winner: Diana DeGette
Winning Vote Count: 272,892
Winning Percentage: 73.8%
-------------------------

# How these results can be modified to use for other elections:
1: We can use these results by inputing name of the required file and folder and then use indirect method to reader the file.
2: By code modification we can allow any other file's input then it can match the input from  our csv file.
 By these modifications we can use this script for anyother election results.
 



 
 
 
 
 
 
 
 
 



 
 
 
