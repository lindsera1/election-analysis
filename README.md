# Election Analysis

## Audit Overview

A Colorado Board of Elections employee, Seth, has asked me to analyze the votes in three Colorado counties to determine several outcomes.
1. The total votes cast in the election
2. The counties voter turnouts
3. The county with the largest turnout
4. List out the candidates in the election that received votes
5. Calculate each candidates total votes and the percentage out of the election total
6. See who the winner was by popular vote

I used the Python programming language to collect and filter all the necessary data to get these results.

## Resources

Include:

- Software: Python 3.8.5, Visual Studio Code 1.49.0
- Data Resource: election_results.csv

## Election Results 

After our analysis, the results were as follows:

- There were 369,711 total votes cast in the election

The individual counties had the following votes:

- Jefferson: 10.5% (38,855)
- Denver: 82.8% (306,055)
- Arapahoe: 6.7% (24,801)

As we can see:

-Denver

Had the largest voter turnout, with 306,055 votes

The candidates names and results:

- Charles Casper Stockham, who received 23.0% of the total votes at 85,213 votes
- Diana DeGett, who received 73.8% of the total votes at 272,892 votes
- Raymon Anthony Doane, who received 3.1% of the total votes at 11,606 votes

The winner of the election with the highest share of the votes:

- Diana DeGette, at 73.8% and 272,892 votes

## Audit Summary

Theoretically, this code could be used for any election, save that the formatting of the results remained the same "Ballot ID, County, Candidate."

```
for county in counties:
        # 6b: Retrieve the county vote count.
        county_count = county_votes[county]
        # 6c: Calculate the percent of total votes for the county.
        county_percentage = float(county_count)/float(total_votes) * 100

         # 6d: Print the county results to the terminal.
        print(f'{county}: {county_percentage:.1f}% ({county_count:,})')
         # 6e: Save the county votes to a text file.
        txt_file.write(f'{county}: {county_percentage:.1f}% ({county_count:,})\n')
         # 6f: Write a decision statement to determine the winning county and get its vote count.
        if county_count > largest_votes:
            largest_votes = county_count
            largest_turnout = county
```

This is the code that was used to get county votes and turnout, and this same format was used for candidate votes. Absolutely nothing has to be changed, unless
we were to begin looking at state votes, or country votes. In these cases, only the keywords would change, and the structure would remain the same. 

```
 # For each row in the CSV file.
    for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1

        # Get the candidate name from each row.
        candidate_name = row[2]

        # 3: Extract the county name from each row.
        county_name = row [1]

        # If the candidate does not match any existing candidate add it to
        # the candidate list
 ```
 
 Here we see the assignment of variables to values within the rows. If these row formats were to change, say instead we added state names, or added electoral votes, then we could just change the row position or variable name that was referenced.
