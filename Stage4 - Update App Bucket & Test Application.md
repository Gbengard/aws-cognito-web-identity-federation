# Advanced Web Identity Federation Demo

Welcome to the advanced demo series, where you will implement a sophisticated serverless application employing Web Identity Federation. The application leverages the following technologies:

- **S3** for hosting the front-end application
- **Google API Project** as the Identity Provider (IDP)
- **Cognito** and **IAM Roles** to exchange Google Tokens for AWS credentials

## STAGE 4A - Downloading Files from S3

1. Navigate to the [S3 Console](https://s3.console.aws.amazon.com/s3/home?region=us-east-1).
2. Open the `webidf-appbucket-` bucket.
3. Select `index.html` and click `Download` to save the file locally.
4. Similarly, select `scripts.js` and click `Download` to save the file locally.

## STAGE 4B - Updating Connection Information

1. Open the local copy of `index.html` in a code editor.
2. Locate the `REPLACE_ME_GOOGLE_APP_CLIENT_ID` placeholder and replace it with YOUR CLIENT ID.
3. Save the changes to `index.html`.
4. Open the local copy of `scripts.js` in a code editor.
5. Locate the `REPLACE_ME_COGNITO_IDENTITY_POOL_ID` placeholder and replace it with your Cognito Identity Pool ID.
	
	![Untitled](/images/Untitled10.png)
	
6. Also, replace the `REPLACE_ME_NAME_OF_PATCHES_PRIVATE_BUCKET` placeholder with the actual name of the `webidf-patchesprivatebucket-` bucket.
7. Save the changes to `scripts.js`.
	
	![Untitled](/images/Untitled11.png)

## STAGE 4C - Uploading Files

1. Return to the S3 console and navigate inside the `webidf-appbucket-` bucket.
2. Click `Upload`.
3. Add the `index.html` and `scripts.js` files and click `Upload`.

## STAGE 4D - Testing the Application

1. Open the `WebApp URL` noted earlier (the distribution domain name of the CloudFront distribution).
2. This web app currently has no access to AWS resources.
3. Open your browser's web developer tools (e.g., Firefox: `Tool` -> `Browser Tools` -> `Web Developer Tools`).
4. Click `Sign In` and authenticate with your Google account.
5. Monitor the browser console for the following sequence of events:
   - Google IDP authentication
   - Receipt of a Google Access token
   - Exchange of the token for Temporary AWS credentials through Cognito
   - Use of these credentials to list objects in the private bucket and generate presigned URLs
   - Loading of images in the browser using the presigned URLs

After signing in, you should see three cat pictures loaded from a private S3 bucket. Observe the presigned URLs used for each image.
	
![Untitled](/images/Untitled12.png)

## Caching Issue

If you encounter sign-in issues:

- Ensure correct credentials in the uploaded `index.html` and `scripts.js`.
- Confirm the completion of CloudFront distribution deployment.

If issues persist, CloudFront may be caching old files. To resolve this:

1. Go to the CloudFront console.
2. Select your CloudFront distribution.
3. Navigate to the `Invalidations` tab.
4. Click `Create Invalidation`.
5. Enter `/index.html` and `/scripts.js` in the `Object Paths` field.
6. Click `Create Invalidation`.

# STAGE 4 - Completion

Congratulations! You now have a fully functional, simple serverless application, featuring:

- A templated front-end app bucket
- Configured Google API Project with access credentials
- Cognito Identity Pool
- IAM Roles for the Identity Pool
- HTML and JS configured to interact with Google IDP and Cognito

In Stage 5, you will proceed to cleanup the resources created.

- [**STAGE 1: Environment Provisioning and Task Review**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage1%20-%20Environment%20Provisioning%20and%20Task%20Review.md)
- [**STAGE 2: Google API Project and Client ID Creation**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage2%20-%20Create%20Google%20API%20Project%20%26%20Client%20ID.md)
- [**STAGE 3: Cognito Identity Pool Establishment**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage3%20-%20Create%20Cognito%20Identity%20Pool.md)
- [**STAGE 4: App Bucket Update and Application Testing**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage4%20-%20Update%20App%20Bucket%20%26%20Test%20Application.md) (Current Stage)
- [**STAGE 5: Account Cleanup**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage5%20-%20Cleanup%20the%20account.md)
