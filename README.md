# CTF Serverless Challenge

A CTF challenge to introduce beginners to APIs, HTTP request methods and cloud computing. The challenge is a serverless architecture that uses AWS. An S3 bucket contains a public text file to guide the user to the next stage. The user is then required to run a POST request to an API gateway that returns a message from the Lambda function. This final message contains the flag (encrypted or not). 

![Architecture](raw.githubusercontent.com/AsianJohnBoi/CTF-Serverless-Challenge/Architecture.png)

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

