# AWS Upload Image to S3 via ApiGateway & Lambda

A sample repository which demonstrates uploading images to S3 via Api Gateway - Lambda integration.

# Instructions

1. Make sure you have serverless installed and AWS CLI as well installed and configured.
https://serverless.com/framework/docs/providers/aws/guide/installation/

2. Update handler.js(lines - 12 & 16) & serverless.yml(line - 14) to your S3 bucket name where images will be kept and permissions for your lambda.
"Bucket": "bucketName"

3. Save all files and run "serverless package" for any validation errors.

4. Now run "serverless deploy" which does actual infrastructure deployment. Note - Based on your CLI settings, resources will be created in that region. Also, handler.js has region hard coded to "us-east-1" which you can modify based on your need.

5. Output should give API Gateway Endpoint which is created - something like https://xxxxxx.execute-api.us-east-1.amazonaws.com/dev/handler

6. Run API call to upload the image with base64 encoded string in JSON. (Visit https://www.browserling.com/tools/image-to-base64 for converting image to base64 online)

Example -     
https://xxxxxx.execute-api.us-east-1.amazonaws.com/dev/handler?username=sampleavatar     
Content-Type: application/json     
Take the JSON payload from - request.json file    
