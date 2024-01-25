# Advanced Web Identity Federation Demo

Welcome to the advanced demo series where you'll be implementing a sophisticated serverless application leveraging Web Identity Federation. This application utilizes various technologies:

- **S3:** Front-end application hosting
- **Google API Project:** Identity Provider
- **Cognito and IAM Roles:** Facilitating the exchange of Google Token for AWS credentials

## Stage 3: Create Cognito Identity Pool

Follow these steps to create a Cognito Identity Pool for your application:

1. Access the [Cognito Console](https://console.aws.amazon.com/cognito/home?region=us-east-1#).
2. In the left menu, select `Identity Pool`, and click on 'Create Identity Pool'.
3. Under 'User Access', choose 'Authenticated Access'
4. Under the `Authentication Identity Sources` and select `Google` and click 'Next'.
5. Under the 'Authenticated Identity Role', click on 'Create A New IAM Role'
6. Enter 'Cognito_PetIDFIDPoolAuth_Role' as the 'IAM Role Name', and click 'Next'.
7. Enter the previously noted Google Client ID in the `Google Client ID` box, and click 'Next'.
8. In the `Identity pool name`, enter `PetIDFIDPool` and then 'Next'.
9. Click on `Create Identity Pool`.
	
	![Untitled](/images/Untitled7.png)

## Stage 3B: Adjust Permissions

1. Move to the [IAM Console](https://console.aws.amazon.com/iam/home?region=us-east-1#/home).
2. Click on `Roles`.
3. Locate and click on `Cognito_PetIDFIDPoolAuth_Role`.
4. Click on `Trust Relationships`.
5. Verify the role is assumable by `cognito-identity.amazonaws.com` with specific conditions:
	- `StringEquals` `cognito-identity.amazonaws.com:aud` `your congnito ID pool`  
	- `ForAnyValue:StringLike` `cognito-identity.amazonaws.com:amr` `authenticated` 
	
	![Untitled](/images/Untitled8.png)
	
6. Click `Permissions` to define what the credentials can do.
7. The CloudFormation template created a managed policy named `PrivatePatchesPermissions` for accessing the `privatepatches` bucket.
8. Click `Add permissions`, then `Attach policies`.
9. Type `PrivatePatches` in the search box and press `Enter`.
10. Check the box next to `PrivatePatchesPermissions` and click `Attach Policies`.
	
	![Untitled](/images/Untitled9.png)

## Stage 3 - Finish

- Front-end app bucket templated
- Google API Project configured
- Credentials for accessing it
- Cognito Identity Pool established
- IAM Roles for the Identity Pool

In Stage 4, you will proceed to create App Bucket Update and Application Testing.

- [**STAGE 1: Environment Provisioning and Task Review**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage1%20-%20Environment%20Provisioning%20and%20Task%20Review.md)
- [**STAGE 2: Google API Project and Client ID Creation**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage2%20-%20Create%20Google%20API%20Project%20%26%20Client%20ID.md)
- [**STAGE 3: Cognito Identity Pool Establishment**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage3%20-%20Create%20Cognito%20Identity%20Pool.md) (Current Stage)
- [**STAGE 4: App Bucket Update and Application Testing**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage4%20-%20Update%20App%20Bucket%20%26%20Test%20Application.md)
- [**STAGE 5: Account Cleanup**](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage5%20-%20Cleanup%20the%20account.md)
