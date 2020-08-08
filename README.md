# Text-to-Speech Application
 Text-to-Speech Application With Amazon Polly
## Topics covered
* Create an Amazon DyanmoDB to store data
* Create an Amazon API Gateway RESTful API
* Creeate AWS Lambda function triggered by API Gateway
* Connect AWS Lambda functions with Amazon Simple Notification Service (SNS)
* Use Amazon Polly to synthesize speech in a variety of language and voices

## Application Architecture
![Application Architecture](Images/architecture.jpg)

## Task 1 : Create a DyanmoDB Table
This application will store infromation about blog posts, including the text and URL of the MP3 file in Amazon DyanmoDB.
1. Table name : posts
2. Primery key : id (String)
3. checkbox select : Use default settings
