# Advanced Web Identity Federation Demo

Welcome to the advanced demo series on Web Identity Federation. In this series, you will undertake the implementation of a sophisticated serverless application leveraging Web Identity Federation. The technologies employed in this application include:

- Amazon S3 for front-end application hosting
- Google API Project as the Identity Provider
- Amazon Cognito and IAM Roles to exchange Google Tokens for AWS credentials

## Stage 5A - Deleting the Google API Project & Credentials

To initiate the deletion process for the Google API Project and its associated credentials, follow these steps:

1. Navigate to the Google Cloud Console: [Google Cloud Console](https://console.developers.google.com/cloud-resource-manager)
2. Select `PetIDF` and click on `DELETE`.
	
	![Untitled](/images/Untitled13.png)
	
3. Enter the ID of the project (displayed above the text box), which may have a slightly different name, and click `ShutDown Anyway`.

## Stage 5B - Deleting the Cognito ID Pool

To remove the Cognito Identity Pool, proceed as follows:

1. Access the AWS Cognito Console: [Cognito Console](https://console.aws.amazon.com/cognito/home?region=us-east-1)
2. Click on `Identity Pool`.
3. Choose `PetIDFIDPool` and click on `Edit Identity Pool`.
4. Locate and expand `Delete identity pool`, then click `Delete Identity Pool`.
	
	![Untitled](/images/Untitled14.png)
	
5. Confirm by clicking `Delete Pool`.

## Stage 5C - Deleting the IAM Roles

To delete the IAM Roles associated with the project, follow these instructions:

1. Go to the AWS IAM Console: [IAM Console](https://console.aws.amazon.com/iam/home?region=us-east-1#/home)
2. Select `Roles`.
3. Choose both `Cognito_PetIDF*` roles and click `Delete Role`.
	
	![Untitled](/images/Untitled15.png)
	
4. Confirm by clicking `Yes, Delete`.

## Stage 5D - Deleting the CloudFormation Stack

To remove the CloudFormation Stack, execute the following steps:

1. Access the AWS CloudFormation Console: [CloudFormation Console](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks?filteringText=&filteringStatus=active&viewNested=true&hideStacks=false)
2. Select `WEBIDF`, click `Delete`, and then confirm by clicking `Delete Stack`.

	![Untitled](/images/Untitled16.jpg)

## Stage 5 - Finalization

Upon completion of Stage 5, your account will be cleaned up, and the following components will be removed:

- Front-end app bucket template
- Configured Google API Project
- Associated credentials
- Cognito Identity Pool
- IAM Roles linked to the Identity Pool

This advanced demo comprises five stages:

- **STAGE 1:** Provision the environment and review tasks
- **STAGE 2:** Create Google API Project & ClientID
- **STAGE 3:** Create Cognito Identity Pool
- **STAGE 4:** Update App Bucket & Test Application
- **STAGE 5:** Cleanup the account *(Current Stage)*