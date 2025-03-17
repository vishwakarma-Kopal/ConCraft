# ConCraft Project

Welcome to the ConCraft project! This README will guide you through the steps required to set up and configure the various AWS services used in this project.

Table of Contents
   1.	Prerequisites
   2.	S3 Bucket Setup
   3.	IAM Roles and Policies
   4.	Lambda Function Setup
   5.	Lex Chatbot Setup
   6.	CloudWatch Integration

Prerequisites

Before starting, ensure you have the following:
    •	AWS account with necessary permissions
    •	AWS CLI installed and configured
    •	Access to the AWS Management Console

S3 Bucket Setup

Step 1: Create an S3 Bucket
   •	Open the S3 Management Console.
   •	Click on "Create bucket".
   •	Enter a unique bucket name (e.g., concraft-meeting-datasheets).
   •	Choose the appropriate region.
   •	Click "Create bucket".

Step 2: Upload a File to the S3 Bucket
   •	Go to the S3 bucket you just created.
   •	Click "Upload".
   •	Select the file you want to upload.
   •	Click "Upload" again.
   •	IAM Roles and Policies

Step 3: Create IAM Role for Lambda
   •	Open the IAM Management Console.
   •	Click on "Roles" and then "Create role".
   •	Choose "AWS service" and then "Lambda".
   •	Click "Next: Permissions".
   •	Attach the following policies:
   •	AmazonS3ReadOnlyAccess
   •	AWSLambdaBasicExecutionRole
   •	Click "Next: Tags" and then "Next: Review".
   •	Enter a role name (e.g., ConCraftLambdaRole).
   •	Click "Create role".

Step 4: Create IAM Role for Lex
   •	Go to the "Roles" section in the IAM Management Console.
   •	Click on "Create role".
   •	Choose "AWS service" and then "Lex".
   •	Click "Next: Permissions".
   •	Attach the AmazonLexFullAccess policy.
   •	Click "Next: Tags" and then "Next: Review".
   •	Enter a role name (e.g., ConCraftLexRole).
   •	Click "Create role".
   •	Lambda Function Setup

Step 5: Create a Lambda Function
   •	Open the Lambda Management Console.
   •	Click "Create function".
   •	Choose "Author from scratch".
   •	Enter a function name (e.g., ConCraftMeetingSummaryFunction).
   •	Choose the runtime (e.g., Python 3.8).
   •	Under "Permissions", choose "Use an existing role" and select ConCraftLambdaRole.
   •	Click "Create function".

Step 6: Add Code to Lambda Function
   •	In the Lambda Management Console, go to the function you just created.
   •	In the "Code" section, write your code directly.
   •	Click "Deploy".
   •	Lex Chatbot Setup

Step 7: Create a Lex Chatbot
   •	Open the Lex Management Console.
   •	Click "Create bot".
   •	Choose "Create a custom bot".
   •	Enter a bot name (e.g., ConCraftBot).
   •	Set up the bot with the necessary configurations and intents.
   •	Click "Create".

Step 8: Import a Lex Bot
   •	In the Lex Management Console, go to your bot.
   •	Click "Actions" and select "Import bot".
   •	Upload the zip file containing the bot definition (e.g., concraft.zip).
   •	Follow the prompts to import the bot.

Step 9: Connect Lex to Lambda
   •	In the Lex Management Console, select your bot.
   •	Go to the "Settings" tab and then "Fulfillment".
   •	Choose "AWS Lambda function" and select the Lambda function you created (e.g.,ConCraftMeetingSummaryFunction).
   •	Click "Save".
   •	CloudWatch Integration

Step 10: Enable CloudWatch Logs for Lambda
   •	In the Lambda Management Console, select your function.
   •	Go to the "Monitoring and operations tools" section.
   •	Enable "Enable active tracing".
   •	Click "Save".

Step 11: Verify CloudWatch Logs
   •	Open the CloudWatch Management Console.
   •	Go to "Logs" and find the log group for your Lambda function.
   •	Verify that logs are being recorded for function invocations.

Conclusion
You have successfully set up the ConCraft project, including S3 bucket creation, IAM roles and policies, Lambda function setup, Lex chatbot integration, and CloudWatch logging. Your ConCraft chatbot is now ready to handle meeting-related requests and provide summaries and action items efficiently.

For any issues or further assistance, please refer to the AWS documentation or reach out to the project maintainers.

