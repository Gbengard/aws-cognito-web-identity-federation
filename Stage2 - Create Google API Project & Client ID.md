# Advanced Web Identity Federation Demo

Welcome to the Advanced Web Identity Federation Demo series, where you'll be guided through the implementation of a sophisticated serverless application utilizing Web Identity Federation. This application leverages the following technologies:

- S3 for hosting the front-end application
- Google API Project as the Identity Provider
- Cognito and IAM Roles for exchanging Google Tokens for AWS credentials

## Stage 2A: Create Google API Project

To kick off this stage, we need to establish authorization credentials for any application utilizing OAuth 2.0 to access Google APIs. Follow these steps:

1. Ensure you have a valid Google login (GMAIL is acceptable).
2. If you don't have a Google account, create one as part of this process.
3. Visit the Google Credentials page at [https://console.developers.google.com/apis/credentials](https://console.developers.google.com/apis/credentials).
4. Sign in or create a Google account.
5. In the Google API Console, set your country and agree to terms and conditions.
6. Click the "Select a project" dropdown, then select "NEW PROJECT."
	
	![Untitled](/images/Untitled3.png)
	
7. Enter "PetIDF" as the project name and click "Create."

## Stage 2B: Configure Consent Screen

1. Navigate to "Credentials" and click "CONFIGURE CONSENT SCREEN."

	![Untitled](/images/Untitled4.png)

2. Select "External" for usability by any Google user and click "CREATE."
3. Provide the application name as "PetIDF"
4. Enter your email in "User support email" and "Developer contact information."
5. Click "SAVE AND CONTINUE" three times.
6. Finally, click "BACK TO DASHBOARD."

## Stage 2C: Create Google API Project Credentials

1. In the left menu, click "Credentials."
2. Click "CREATE CREDENTIALS" and select "OAuth client ID."

	![Untitled](/images/Untitled5.png)

3. Choose "Web Application" as the application type.
4. Enter "PetIDFServerlessApp" as the name.
5. Add the distribution domain name of the CloudFront distribution under "Authorized JavaScript origins."

	![Untitled](/images/Untitled6.png)

6. Click "CREATE."

Upon completion, note down the provided "Client ID"; the "Client Secret" won't be needed again. Click "OK" once done.

## Stage 2 - Finish

Congratulations on completing Stage 2! You have successfully:

- Set up the front-end app bucket template
- Configured the Google API Project
- Acquired the necessary credentials for accessing it

Stay tuned for the next stages in this advanced demo series:

- [**STAGE 1: Environment Provisioning and Task Review**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage1%20-%20Environment%20Provisioning%20and%20Task%20Review.md)
- [**STAGE 2: Google API Project and Client ID Creation**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage2%20-%20Create%20Google%20API%20Project%20%26%20Client%20ID.md) (Current Stage)
- [**STAGE 3: Cognito Identity Pool Establishment**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage3%20-%20Create%20Cognito%20Identity%20Pool.md)
- [**STAGE 4: App Bucket Update and Application Testing**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage4%20-%20Update%20App%20Bucket%20%26%20Test%20Application.md)
- [**STAGE 5: Account Cleanup**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage5%20-%20Cleanup%20the%20account.md)
