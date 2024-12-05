# NBADataLake
This repository contains the setup_nba_data_lake.py script, which automates the creation of a data lake for NBA analytics using AWS services. The script integrates Amazon S3, AWS Glue, and Amazon Athena, and sets up the infrastructure needed to store and query NBA-related data.

# Overview
The setup_nba_data_lake.py script performs the following actions:

Creates an Amazon S3 bucket to store raw and processed data.
Uploads sample NBA data (JSON format) to the S3 bucket.
Creates an AWS Glue database and an external table for querying the data.
Configures Amazon Athena for querying data stored in the S3 bucket.

# Prerequisites
Before running the script, ensure you have the following:

AWS Account:

An active AWS account with permissions to create and manage resources in S3, Glue, and Athena.
Python:

Python 3.7 or higher installed on your local machine or environment (e.g., AWS CloudShell, EC2).
Python Libraries:

Install the following libraries:
pip install boto3

AWS CLI
aws configure
Provide your AWS Access Key, Secret Key, Default Region, and Output Format

IAM Role/Permissions: Ensure the user or role running the script has the following permissions:

S3: s3:CreateBucket, s3:PutObject, s3:DeleteBucket, s3:ListBucket
Glue: glue:CreateDatabase, glue:CreateTable, glue:DeleteDatabase, glue:DeleteTable
Athena: athena:StartQueryExecution, athena:GetQueryResults

#START HERE 
#Step 1: Open CloudShell Console

Go to aws.amazon.com & sign into your account

In the top, next to the search bar you will see a square with a >_ inside, click this to open the CloudShell

#Step 2: Create the setup_nba_data_lake.py file
In the CLI (Command Line Interface), type nano setup_nba_data_lake.py

In another window, go to https://github.com/alahl1/NBADataLake
Copy the contents inside the setup_nba_data_lake.py file

Go back to the Cloudshell window and paste the contents inside the file.

Press ^X to exit, press Y to save the file, press enter to confirm the file name 


#Step 3: Run the script
In the CLI type
python3 setup_nba_data_lake.py

You should see the resources were successfully created, the sample data was uploaded successfully and the Data Lake Setup Completed

#Step 4: Manually Check For The Resources
In the Search Bar, type S3 and click blue hyper link name
You should see 2 General purpose bucket named "Sports-analytics-data-lake"
When you click the bucket name you will see 3 objects are in the bucket
Click on raw-data and you will see it contains "nba_sample_data.json"
Click the file name and at the top you will see the option to Open the file
The contents should look like this:
[
    {"player": "LeBron James", "team": "Lakers", "points": 30},
    {"player": "Stephen Curry", "team": "Warriors", "points": 40}
]
