# Election_Analysis
![image](https://user-images.githubusercontent.com/112978144/226445157-f5c85a03-31e2-4ac2-9950-3ea310d722ab.png)

Overview of Election Audit: The purpose of this challenge was to provide the audit of election results among three different counties. The election commission has requested some additional data to complete the audit:

* The voter turnout for each county
*  The percentage of votes from each county out of the total count
* The county with the highest turnout
 * Total votes
   * Candidates names who participated in election.
   * Total votes each candidate received.
   * Percentage of votes each candidate received.
   * Winner of the election.
# Resources: Election_Analysis
# Code Language: Python

# Deliverable 1
For deliverable one there were different steps to work on to get the required out put. 
# Step 1
In step one we initialize a county list, like the candidate_options list, that holds the names of the counties and initialize a dictionary, like the candidate_votes dictionary, that hold the county as the key and the votes cast for each county as the values.
# Step 2
we initialize an empty string, like winning_candidate, that hold the county name for the county with the largest turnout and initialize a variable, like the winning_count variable, that hold the number of votes of the county that had the largest turnout.
# Step 3
we wrote a script that gets the county name from each row while reading the election results from each row inside the for loop.
# Step 4
* Step 4a:

We wrote a decision statement with a logical operator to check if the county name acquired in Step 3 is in the county list we created in Step 1.
* Step 4b:

We wrote a code to check if the county is not in the list created in Step 1, we added it to the list of county names like we did when adding a candidate to the candidate_options list.
* Step 4c:

We wrote a script that initializes the county vote to zero, like we did when we began to track the vote counts for the candidates.
# Step 5:

We wrote a script that adds a vote to the county’s vote count as we were looping through all the rows, like we did for the candidate’s vote count.
# Step 6a:

We wrote a repetition statement to get the county from the county dictionary that was created in Step 1.
* Step 6b:

We initialize a variable to hold the county’s votes as they are retrieved from the county votes dictionary.
* Step 6c:

We wrote a script that calculates the county’s votes as a percentage of the total votes.
* Step 6d:

We wrote a print statement that prints the current county, its percentage of the total votes, and its total votes to the command line.
# Deliverable 2
Deliverable two is linked with deliverable one and started from the point where we finished deliverable one.
* Step 6f:

We wrote a decision statement that determined the county with the largest vote count and then added that county and its vote count to the variables created in Step 2.
# Step 7:

We wrote a print statement that printed out the county with the largest turnout.
After taking all these steps we got the following output in the terminal that matched exactly the same as it was mentioned in the module.
![image](https://user-images.githubusercontent.com/112978144/226438090-87afadc6-da1c-4c68-95cd-4f2f5588c637.png)

Using our knowledge of writing data to a text file, we wrote the winning candidate results and the county election results to the election_results.txt file.

# Step 6e:
Step 6e is from deliverable one and in this step
We wrote a script that saved each county, the county’s total votes, and the county’s percentage of total votes to the election_results.txt file.
# Step 8:

We wrote a script that saved the county with the largest turnout to the election_results.txt file.
After we run our solution to Deliverable 2, we confirmed that our election_results.txt file matched the results provided in the module
![image](https://user-images.githubusercontent.com/112978144/226439314-ca0a02c6-0859-44d6-bebe-515e79f168a3.png)

# Election-Audit Results 
Using a bulleted list, we addressed the following election outcomes. Use images or examples of our code as support where necessary to answer following questions.

* How many votes were cast in this congressional election?
There were total 369711 vote cast in the congresssional elections.
* Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.
Following is the breakdown of the number of votes and percentage of total votes for each county
County Votes:
Jefferson: 10.5% (38,855)
Denver: 82.8% (306,055)
Arapahoe: 6.7% (24,801)

* Which county had the largest number of votes?
Denver had the largest number of votes with 82.8%.
* Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.
Following is the breakdown of the number of votes and the percentage of the total votes each candidate received
Charles Casper Stockham: 23.0% (85,213)
Diana DeGette: 73.8% (272,892)
Raymon Anthony Doane: 3.1% (11,606)
* Which candidate won the election, what was their vote count, and what was their percentage of the total votes?
Diana DeGette was the winner who got 272,892 vote with 73.8%.

# Election_Audit Summary
Expanding the Election Audit to include voter turnout by county along with candidates results was a smart way to take advantage of the data provided for this challenge. The delivered outcomes can be benificial for future election performance, so anyone might properly find resources where turnout is low or demographics are hard to reach.

 In order to customize the script it can provide on-demand analysis for years to come.

Modifying the script to produce turnout results by county is just one of the way that minor changes to the code can provide critical data. As we could also work a little more and determine what percentage of each county voted for each candidate by adding an if-statement to the code. These type of Statements are how the code runs calculations.

if this was a federal election, we can use the same script and change the county to states.

 
 

# How these results can be modified to use for other elections:
1: We can use these results by inputing name of the required file and folder and then use indirect method to reader the file.
2: By code modification we can allow any other file's input then it can match the input from  our csv file.
 By these modifications we can use this script for anyother election results.
 



 
 
 
 
 
 
 
 
 



 
 
 
