# sam-lambda-param-store

## Overview
This is a simple example of integration between AWS Lambda and AWS SSM Parameter Store.
Developers commonly want to store application configuration centrally, separate from 
the application code, and with limited access permission. 

This sample shows how to create a plaintext parameter in 
Amazon EC2 Systems Manager Parameter Store and access it from your Lambda function.
It also shows how to create a KMS encryption key that only the function can use for decryption.


## Useful commands
* Install pip requirements to a lib directory under the code folder
  * pip install --upgrade -t './code/lib' -r requirements.txt
* Package and deploy the example.
  * aws cloudformation package --template-file lambda-parameter-store-sam-template.yaml --s3-bucket <YOUR_S3_BUCKET> --output-template-file packaged-template.yaml
  * aws cloudformation deploy --template-file packaged-template.yaml --stack-name "ParameterStoreExampleStack" --capabilities CAPABILITY_IAM
  
