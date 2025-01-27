# CI/CD for Lambda Functions

Creating CI/CD pipeline to automate the process of deploying Lambda Functions.

1. Deploying the Lambda Function code when it changes.
2. Updating the Lamda Layer when dependencies (package-lock.json) change.


Setting up automation with GitHub Actions, AWS SAM, and Lambda to make the deployment smooth and efficient.

## After Deployment

### 1. Check the Stack in AWS CloudFormation

* Go to CloudFormation Console in AWS.
* Look for the stack name (lambda-sam-stack)
* Check the status (CREATE_COMPLETE)


### 2. Verify Lambda Function

* Go to AWS Lambda Console.
* Look for the function defined in the teamplate.yaml (MyLambdaFunction)
* Check if the function exists and its settings match with the template.yaml

### 3. Verify Lambda Layer

* Go to AWS Lambda Console > Layers.
* Look for the layer you defined in template.yaml (MyLambdaLayer)


### 4. CloudWatch Logs

* Go to CloudWatch Console > Logs > Log Groups
* Look for the group named after your Lambda function (/aws/lambda/MyLambdaFunction)


### 5. API Gateway (If the SAM application involves API gateway)

* Go to API Gateway console
* Check for the deployed API

### 6. Verifying via AWS CLI

* To list the stack and check its status.
```bash
   aws cloudformation describe-stacks --stack-name lambda-sam-stack
   ```
* To list lambda functions.
```bash
   aws lambda list-functions
   ```
* To list lambda layers.
```bash
   aws lambda list-layers
   ```

### 7. Testing the Deployed Lambda
* Select the function.
* Use the "Test" button to invoke it with sample input.
* Review the executio resut and logs.
