# CTF Serverless Challenge

A CTF challenge to introduce beginners to APIs, HTTP request methods and cloud computing. The challenge is a serverless architecture that uses AWS. An S3 bucket contains a public text file to guide the user to the next stage. The user is then required to run a POST request to an API gateway that returns a message from the Lambda function. This final message contains the flag (encrypted or not). 

![Architecture](https://github.com/AsianJohnBoi/CTF-Serverless-Challenge/blob/master/Architecture.png)

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
4. Add a POST method by clicking on Actions >Create method. Select 'POST'.
5. Add the lambda function to the method.
6. Click on the Method request, set API key to true.
7. Click on 'Actions' > deploy API. This will give you a URL link to the API. Copy the link.
8. The API won't be accessible without a key. So you need to create an API key by clicking on API Keys > Actions > Create API key. Name and auto generate it.
9. Create a new Usage plan. You can set your throttling or quota to anything (Consider how many users will take on the challenge). Add the API stage and the key to the plan (don't forget to click on the checkmark!)
10. Navigate to your API key and make sure the usage plan has been added to it. If not go back to the previous step. Copy the API key.
11. Save the API URL and the API key in a text file.
12. Create a new S3 bucket. Leave the configuration and permissions by default.
13. Upload the file to the S3 bucket and make it public.
14. Enjoy the challenge!

