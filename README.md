## Blue/Green deployment with AWS Developer tools on Amazon EC2 using Amazon EFS to host application source code

This Repo contains AWS Cloudformation template and required scripts to configure a fully automated CI/CD pipeline for performing a fully automated Blue/Green deployment on EC2 Instances using Amazon EFS to host source code.

This sample solution sets up a complete CI/CD pipeline for conducting a blue/green deployment on EC2 instances utilizing Amazon EFS file share as mount point to host application source code. The EFS share will be the central location hosting your application content, and it will help reduce your overall deployment time by eliminating the need for deploying a new revision on every EC2 instance local storage. It also helps to preserve any dynamically generated content when the life of an EC2 instance ends.

## Prerequisites

- An [AWS account](https://signin.aws.amazon.com/signin?redirect_uri=https%3A%2F%2Fportal.aws.amazon.com%2Fbilling%2Fsignup%2Fresume&client_id=signup)
- Access to an AWS account with administrator or PowerUser (or equivalent) [AWS Identity and Access Management(IAM)](http://aws.amazon.com/iam) role policies attached
- [Git Command Line](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) installed and configured in your local environment

## Deploy the solution

- Clone the GitHub repo and store the files on your local machine. Utilize the commands below to clone the repo:

    ```
      mkdir -p ~/blue-green-sample/
      cd ~/blue-green-sample/
      git clone https://github.com/aws-samples/blue-green-deployment-pipeline-for-efs
	``` 

Utilize the following steps to deploy the solution in your AWS account:

- Create a private Amazon Simple Storage Service (Amazon S3) bucket.
- Upload the cloned or downloaded GitHub repo files to the root of the S3 bucket. the S3 bucket objects structure.
- Go to the S3 bucket and select the template name solution-stack-template.yml, and then copy the object URL.
- Open the CloudFormation console. Choose the appropriate AWS Region, and then choose Create Stack.
- On the Specify stack details page, enter a name for the stack and provide the input parameter "ArtifactBucket".

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.