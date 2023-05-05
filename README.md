# web app AWS
 html app hosted on amplify, takes user input as 'base' & 'exponent', and send it to lambda, which calls python script to calculate the total and sends output to dynamodb. We use IAM to giv lambda permission to right into dynamoDB

1.Amplify, build & host websites, (were gonna create index.html page using an editor, then just deploy w amplify)

2. A way to invoke the lambda function, cuz our user isnt goin into aws console and deploy it. We need a public url or endpoint. For that were gonna use api gateway(core service) that u can use to build ur own apis, (http, rest, webstock apis) we use REST API

-Enable cors, allows an application running in one origin or domain to access recuourses in a different origin or domain, so since our web app is running on one domain in amplify, and our other on lambda, were gonna need to work thru both


3. A way to do math, gonna use a lambda function, a lambda function is just a bit of code that responds to some trigger, for example when you upload a picture to an s3 bucket, it can trigger a lambda function to go process that picture. By the fricking way did i mention these are serverless… you dont have to set up servers to run the code, happens behind the scenes for u, so we will use python code and math lib.

Tested api works with function. Works

Request: /
Status: 200
Latency: 204 ms
Response Body
{"statusCode": 200, "body": "\"Your result is 16.0\""}


4. How do we incorporate a database into this. ?
5. As we do this we need to handle permissions between the different parts of the application.

4. Starting with our database for our purposes we will use dynamodb, its a key value/nosql database, lighter weight than a relational database were u have to set up other stuff ahead of time 
5. Now we need lambda func permissions to right to databsase

Put the DB URI in ur lambdas controls to link them

After allowin permission our stuff is stored in the database

Add permission for api gateway so that websites output will send to database.
