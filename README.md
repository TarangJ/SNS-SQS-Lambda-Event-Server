# Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda

This application demonstrates a simple architecture for handling events asynchronously in a scalable and cost-effective manner.

Technologies Used:

 Amazon SNS: A fully managed pub/sub messaging service.
 Amazon SQS: A fully managed message queuing service.
 AWS Lambda: A serverless compute service for running code in response to events.
 AWS IAM: Identity and Access Management for managing permissions.

Setup and Deployment

To set up and deploy this application, follow these steps:

1. Create AWS Resources: Create an Amazon SNS topic, an Amazon SQS queue, and an AWS Lambda function.
    
![Screenshot from 2024-03-23 18-44-45](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/2322310f-e2ec-41c8-a7aa-f0915b9d373c)
    
![Screenshot from 2024-03-23 18-44-58](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/2ebcd3e9-76e7-4fda-9043-68c913e5a551)

![Screenshot from 2024-03-23 18-45-19](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/8bc85c75-1ae9-400a-86e5-7d6d22217c41)

![Screenshot from 2024-03-23 18-45-55](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/1d23970e-15af-4af1-a390-63b3ebd70555)

![Screenshot from 2024-03-23 18-51-08](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/14530b05-f98d-4ab3-bdb8-e4d4ae887e25)

2. Configure Permissions: Attach the provided IAM policy to allow SNS to send messages to the SQS queue.
   - Replace default policy with "Policy_re" in this repo.
   - Click "save" to attach the policy.

![Screenshot from 2024-03-23 18-55-42](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/f1d9bc0a-d697-4b25-8cd2-ac87d9879ee8)

![Screenshot from 2024-03-23 18-56-01](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/317f3d95-4f5e-4da7-a2fc-a484742d114e)

3. Deploy Lambda Function: Upload the Lambda function code and configure the trigger to listen to messages from the SQS queue.
   
   - Lambda Function Logic: The Lambda function processMessages listens to messages from the SQS queue and logs the message body to the console.
   - Then hit "deploy"

![Screenshot from 2024-03-23 19-00-41](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/aa224896-fac9-4913-b333-92a8364b0ab2)

  - Go to "Congfiguration" -> "Permission" -> click on "Role name"
  
![Screenshot from 2024-03-23 19-05-20](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/3e3c7787-2977-4245-8c73-5fe64286ff2e)

  -  Click "Attach Policy"
  -  add "AWSLamdaSQSQueueExecutionRole": It grants minimal permissions for sending and receiving messages, ensuring secure integration between Lambda and SQS.
![Screenshot from 2024-03-23 19-05-57](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/6878fb99-7089-4603-815d-fcd761943450)

  - Configure Amazon SQS-> MyQueue -> Lamda trigger
    
![Screenshot from 2024-03-23 19-07-17](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/444ebdf0-01cb-4c6b-b4a3-04d8979795c1)

  - Wait for status "enable"

![Screenshot from 2024-03-23 19-07-31](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/070805c6-0d93-465e-bfba-6306cd0c7eed)

  - Go to SNS -> and click "Publish message"
  - Give your subject name (Optional)
  - Add you example in message body
  - Hit "Publish Message"

![Screenshot from 2024-03-23 19-09-37](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/1e0268bb-0b35-40d3-ac59-51db09efae48)

4. Testing: Send messages to the SNS topic and verify that they are processed by the Lambda function.

  - Go to CloudWatch -> Log groups -> /aws/lamda/MyTest
  - Look for recent Log events
  - You will get your subject and message !
    
![Screenshot from 2024-03-23 19-12-51](https://github.com/TarangJ/Event-Driven-Serverless-Application-with-AWS-SNS-SQS-and-Lambda/assets/65700353/a5472ee4-038b-4071-b482-1d79224803ac)

    
   
