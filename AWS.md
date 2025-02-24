# AWS

Install `aws cli`

then configure aws cli using `aws configure` or `aws configure sso`

then we can create an aws lamba function as:

`aws lambda create-function --function-name "myAWSLambda" --runtime "python 3.7" --zip-file "fileb://zipFileName.zip" --handler "myAWSLambda.lambda_handler" --role "ARN ID for role"`

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=AWS.md&fileType=undefined&fileExtension=md