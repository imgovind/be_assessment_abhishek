# be_assessment_abhishek

# 32Health - FastAPI assignment

Your task is to create a **_dockerized_** service, **claim_process**  to process claims. 

## Requirements
1. **claim_process** transforms a JSON payload representing a single claim input with multiple lines and stores it into a RDB.
   - An example input (in CSV format) - *claim_1234.csv* is provided. Note that the names are not consistent in capitalization.
2. **claim_process** generates a unique id per claim.
3. **claim_process** computes the *“net fee”* as a result per the formula below.
*“net fee” = “provider fees” + “member coinsurance” + “member copay” - “Allowed fees”* (note again that the names are not consistent in capitalization).
4. A downstream service, **payments**, will consume *“net fee”* computed by **claim_process**.


## Task Instructions
1. You have up to **180 min** to complete your solution. Mail govind@32health.care a copy/link to your solution.
2. Feel free to make and reasonable assumptions, state them and proceed if anything is unclear.
3. Please use FastApi as your API framework. As noted earlier the solution must be dockerized.
4. Use sqlite as a db and ORM of your choice. (Not necessary, but Extra points if you use postgres as your db and SQLModel as your ORM and have a docker-compose solution that brings up a db and the web service in one command)
5. Please add data validation for *“submitted procedure”* and *“Provider NPI”* columns. *“Submitted procedure”* always begins with the letter ‘D’ and *“Provider NPI”* is always a 10 digit number. The data validation should be flexible to allow for other validation rules as needed. All fields except *”quadrant”* are required.
6. Write pseudo code or comments in your code to indicate how **claim_process** will communicate with **payments**. There are multiple choices here but propose a reasonable solution based on:
   - What needs to be done if there is a failure in either service and steps need to be unwinded.
   - Multiple instances of either service are running concurrently to handle a large volume of claims.
   (Not necessary but extra points if you actually implement a rudimentary solution that create a payment record in a payments table, with error handling and other stuff built into it)

## Evaluation Criteria
1. Clean, documented code and avoidance of anti-patterns
2. Functioning code
3. Presence of Test cases
