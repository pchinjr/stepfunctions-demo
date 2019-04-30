# Example Step Function using Serverless Framework 

Example made from [Serverless Blog Post](https://serverless.com/blog/how-to-manage-your-aws-step-functions-with-serverless/)

Step Functions are a service from AWS to create state machines to orchestrate other aws services like Lambas. The goal is to create workflows that are observable and can do things like retries and error handling. It leaves the individual components stateless.

## How to Use:

### Install Serverless Framework

`$ npm i -g serverless` 

### Configure AWS Profile and Credentials using the AWS Console
 - create a user and give that user IAM permissions to execute lambdas, cloudformation, api gateway, and step functions
 - save the information to `~/.aws/credentials`

### Install serverless framework plugins for step functions and pseudo parameters 

`$ serverless plugin install --name serverless-step-functions`

`$ serverless plugin install --name serverless-pseudo-parameters`

### Deploy functions 

`severless deploy` 

In the AWS Console create an EC2 Instance and note the instance id. Also create an S3 bucket and update the bucket name in the handler.js file 

To execute the step function use curl command 

`curl -XPOST https://xxxxx.execute-api.us-east-1.amazonaws.com/dev/startEC2 -d '{"instanceId":"<instanceId>"}'`
