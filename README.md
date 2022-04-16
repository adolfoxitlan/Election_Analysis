# Election_Analysis

## Project Overview
The project's purpose is to conduct an audit of the data collected for the voting results in Colorado. The Colorado Board of Elections needs to get the details for the following points:

    - Total number of votes cast
    - A complete list of candidates who received votes
    - Total number of votes each candidate received
    - Percentage of votes each candidate won
    - The winner of the election based on popular vote

## Resources 
- Data source: [election_results.csv](Resources/election_results.csv)
- Softwate: Python 3.9.6 (tags/v3.9.6:db3ff76, Jun 28 2021, 15:26:21) [MSC v.1929 64 bit (AMD64)] 
![image](Resources/PythonVer.jpg)

## Summary

For this purpose, we use Python. Using some functions such as reading and writing files, calculations, and applying formats for the terminal and for text files, we obtained the following results:

- 369,711 people voted.
- Three candidates participated, Diana DeGette obtained an almost absolute majority with 73.8% of the total votes.
- Not even adding the results of the other 2 participants could they even come close.
- Raymon Anthony Doane has to work hard on increasing his reach to voters, he only got 3.1%.

Resume.

* There were 369,711 votes cast in the election.
* The three candidates were:
    * Charles Casper Stockham
    * Diana DeGette
    * Raymon Anthony Doane
* The candidate results were:
    * Charles Casper Stockham received 23.0% of the vote and 85,213 number of votes.
    * Diana DeGette received 73.8% of the vote and 272,892 number of votes.
    * Candidate 3 received 3.1% of the vote and 11,606 number of votes.
* The winner of the election was:
    * Diana DeGette, who received 73.8% of the vote and 272,892 number of votes.

![image](Resources/Voting_Resultsjpg.jpg)

* The voter turnout for each county and the percentage of votes from each county out of the total count.

                                            |   County  |   %   |  Votes  |
                                            | --------- | ----- | ------- |
                                            | Jefferson | 10.5% | 38,855  |
                                            | Denver    | 82.8% | 306,055 |
                                            | Arapahoe  | 6.7%  | 24,801  |
                                            
 * The percentage of votes from each county out of the total count.

      # Largest County Turnout: Denver with 306,055 votes       :+1:

## Challenge Overview
Meeting the requirements of the Colorado Board of Elections was rigorous and required extensive Python functionalities like:
* Importing modules; `import csv` and `import os`. 
    * It is essential to mention that `import csv` takes precedence in this kind of data project; opening, reading, and writing data into files was crucial.
* Using dictionaries and lists to hold data meanwhile calculations.
    * `candidate_options = []`
      `candidate_votes = {}`
* Loops, were essential to go through all the data repeatedly to get the perfect calculation.

         6a: Write a for loop to get the county from the county dictionary.
        for county in county_list:

          6b: Retrieve the county vote count.
        county_vote = county_votes.get(county)

          6c: Calculate the percentage of votes for the county.
        county_vote_percentage = float(county_vote) / float(total_votes) * 100

          6d: Print the county results to the terminal.
        county_results = f"{county}: {county_vote_percentage:.1f}% ({county_vote:,})\n"
        print(county_results)

          6e: Save the county votes to a text file.
        txt_file.write(county_results)

          6f: Write an if statement to determine the winning county and get its vote count.
        if (county_vote > largest_county_turnout_count) and (
            county_vote_percentage > largest_county_percentage):
            
            largest_county_turnout_count = county_vote
            largest_county_percentage = county_vote_percentage
            largest_county_turnout = county

    The next loop has become one of my favorites because it integrates calculations and formatting; which makes it more complex in its development.

        Save the final candidate vote count to the text file.
        for candidate_name in candidate_votes:

        Retrieve vote count and percentage
        ---->votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")<----

        Print each candidate's voter count and percentage to the terminal.
        print(candidate_results)
        Save the candidate results to our text file.
        txt_file.write(candidate_results)

        Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage
            
* Formatting; the format becomes very important after the calculations and the analysis and entering the results; a lousy presentation and all the work behind could be in vain.

        f"-------------------------\n"
        f"Winner: {winning_candidate}\n"
        f"Winning Vote Count: {winning_count:,}\n"
        f"Winning Percentage: {winning_percentage:.1f}%\n"
        f"-------------------------\n")
            print(winning_candidate_summary)


The results were evident and favored Diana DeGette and Denver being the stronghold for her party. It was straightforward to determine in which counties the other two candidates needed to work more to be able to reach Diana's party in the next elections; 

The calculation result showed that even adding the votes of the two candidates who lost, they would not reach half of what Diana did.
       
## Challenge Summary

The results of this development pleasantly surprised the committee; due to this, they intend to use it for future voting and extend it to more country states.

The following modifications are proposed to the script to extend its use if required.
* - Adding two variables and an input() function to add the ability to choose another file/file path without modifying the code.

https://user-images.githubusercontent.com/102424210/163659647-a49b26b1-759e-4e37-bcf5-bce14b503573.mp4



