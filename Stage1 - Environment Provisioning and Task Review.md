# Advanced Web Identity Federation Demo

Welcome to the Advanced Web Identity Federation Demo series, where you will be guided through the implementation of a sophisticated serverless application leveraging Web Identity Federation. This application seamlessly integrates various technologies to deliver a powerful user experience:

- **S3 for Front-end Application Hosting**
- **Google API Project as an Identity Provider**
- **Cognito and IAM Roles for Exchanging Google Token for AWS Credentials**

## Overview

The application, operating within a browser, facilitates user authentication using a Google ID and dynamically loads images from a private S3 bucket into the browser using presigned URLs. The demo comprises five stages:

1. **STAGE 1A - Login to an AWS Account** 
2. **STAGE 1B - Verify S3 Bucket**
3. **STAGE 1C - Verify Private Bucket**
4. **STAGE 1D - Verify CloudFormation Distribution**
5. **STAGE 1E - FINISH**

### STAGE 1A - Login to an AWS Account

1. Log in to your AWS account with administrative privileges.
2. Ensure your region is set to `us-east-1` (N. Virginia).
3. Click [HERE](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/quickcreate?templateURL=https://techidence.s3.amazonaws.com/aws_projects/WEBIDF.yaml&stackName=WEBIDF) to automatically configure the required infrastructure.
4. Check the `The following resource(s) require capabilities: [AWS::IAM::ManagedPolicy, AWS::IAM::Role]` box.
5. Click `Create Stack`.
6. Wait for the stack to transition to the `CREATE_COMPLETE` state.

	![Untitled](/images/Untitled.png)

### STAGE 1B - Verify S3 Bucket

1. Open the [S3 console](https://s3.console.aws.amazon.com/s3/home?region=us-east-1).
2. Access the bucket starting with `webidf-appbucket`.
3. Confirm the presence of objects, including `index.html` and `scripts.js`.
4. Navigate to the `Permissions` tab and verify that `Block all public access` is set to `Off`.
5. Click `Bucket Policy` and ensure there is a valid bucket policy.

### STAGE 1C - Verify Private Bucket

1. Open the bucket starting with `webidf-patchesprivatebucket-`.
2. Review the contents of the bucket.
3. Confirm the absence of a bucket policy, ensuring the bucket remains entirely private.

	![Untitled](/images/Untitled1.png)
	
### STAGE 1D - Verify CloudFormation Distribution

1. Visit the [CloudFront console](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=us-east-1#/distributions).
2. Locate the distribution pointing to the origin `webidf-appbucket-....` and click on it.
3. Identify the `distribution domain name`.
4. Note this domain name as the `WebApp URL`, prefixed with https (e.g., `https://dgqelplzo3o3b.cloudfront.net`).

	![Untitled](/images/Untitled2.png)

### STAGE 1 - FINISH

At this stage, you have established the foundational infrastructure, including:

- Front-end app bucket
- Private patches bucket
- CloudFront distribution providing caching and HTTPS capabilities

In Stage 2, you will proceed to create a Google API project, which will serve as the `ID Provider` for this serverless application.

- [**STAGE 1: Environment Provisioning and Task Review**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage1%20-%20Environment%20Provisioning%20and%20Task%20Review.md) (Current Stage)
- [**STAGE 2: Google API Project and Client ID Creation**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage2%20-%20Create%20Google%20API%20Project%20%26%20Client%20ID.md)
- [**STAGE 3: Cognito Identity Pool Establishment**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage3%20-%20Create%20Cognito%20Identity%20Pool.md)
- [**STAGE 4: App Bucket Update and Application Testing**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage4%20-%20Update%20App%20Bucket%20%26%20Test%20Application.md)
- [**STAGE 5: Account Cleanup**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage5%20-%20Cleanup%20the%20account.md)
