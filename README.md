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

### When the application sends information new posts :
1. The information is received by the RESTful web service exposed by Amazon API Gateway. This web service is invoked by a static webpage hosted on Amazon Simple Storage Service (Amazon S3).

2. Amzaon API Gateway triggers an AWS Lambda function, New Post, Which is responsible for initialozing the process of generating MP3 files.

3. The Lambda function inserts information about the post into an Amazon DyanmoDB table, where inforamation about all posts is stored.

4. To run the whole process asynchronously, you will use Amazon Simple Notification Service (Amazon SNS) to decouple the process of receving information about new posts and staring their audio conversion.

### When the application retrieves information about posts :
1. The RESTful web service is deployed using Amazon API Gateways. Amazon API Gateway expose the method for retrieving information about posts. These methods contain the text of the post and the link to the S3 bucket where the MP3 file is stored. The web service is invoked by a static webpage hosted on Amazon S3.

2. Amazon API Gateway invokes the Get Post Lambda function, whcich deploys the logic for retreving the post data.

3. The Get Post Lambda function retrieves infromation about the post (including the reference to Amazon S3) from the DyanoDB table and returns the information. 

## Task 1 : Create a DyanmoDB Table
This application will store infromation about blog posts, including the text and URL of the MP3 file in Amazon DyanmoDB.
1. Table name : posts
2. Primery key : id (String)
3. checkbox select : Use default settings
