# Clouds and API

A CTF challenge to introduce beginners to APIs, HTTP request methods and cloud computing. The challenge is a serverless architecture that uses AWS. An S3 bucket contains a public text file to guide the user to the next stage. The user is then required to run a POST request to an API gateway that returns a message from the Lambda function. This final message contains the flag (encrypted or not). 

![data:image/png;base64,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](data:image/png;base64,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)

The first stage of this challenge may too easy. You could provide the link to the S3 bucket folder without any  read permissions and make people find the text file. E.g.

"There's a 'firstmessage.txt' file inside my S3 bucket https://s3-ap-northeast-2.amazon.com/challenge"



### Requirements

```
AWS account
1x S3 Bucket
1x Lambda function
1x API Gateway
1x Text file
```



### Deployment

1. Create a new Lambda function, author from scratch and set the language to Python 3.6 or above. You do not need to set any permissions. Can create with defaults. 
2. Change the json dump to any message with the flag inside. See `lambda_function.py` for an example. You may test your function by clicking the 'Test' button.
3. Create a new Rest API Gateway.
4. Add a POST method by clicking on Actions > select 'POST' and click the checkmark.
5. Add the lambda function to the method.
6. Click on the POST method > Method request, set API key to true.
7. Click on 'Actions' > deploy API. This will give you a URL link to the API. Copy the link.
8. The API is accessible but not when you don't have a key. You will get a forbidden message. So we need to create an API key. Click on API Keys > Actions > Create API key. Name and auto generate it.
9. Add a new usage plan and include the API gateway you created. Your API and Lambda function is good to go! Copy the API key.
10. Create a new S3 bucket. You can leave the configuration and permissions by default.
11. Create a text file containing the API URL and key.
12. Upload the file to the S3 bucket and make it public.
13. Enjoy the challenge!
