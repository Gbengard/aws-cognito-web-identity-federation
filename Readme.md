# Advanced Demo - Web Identity Federation

Explore the intricacies of Web Identity Federation through this comprehensive demo series, where you will construct a sophisticated serverless application. This application leverages various technologies to deliver a seamless user experience:

- **S3** for front-end application hosting
- **Google API Project** as an Identity Provider
- **Cognito and IAM Roles** for swapping Google Tokens for AWS credentials

The application operates directly from a web browser, prompting users to log in using their Google credentials. Subsequently, it fetches and displays all images from a private S3 bucket within the browser using pre-signed URLs.

This advanced demo is structured into six stages:

- **STAGE 1:** Provision the environment and review tasks
- **STAGE 2:** Create Google API Project & Client ID
- **STAGE 3:** Create Cognito Identity Pool
- **STAGE 4:** Update App Bucket & Test Application
- **STAGE 5:** Cleanup the account

## Instructions

- [Stage 1](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage1%20-%20Environment%20Provisioning%20and%20Task%20Review.md)
- [Stage 2](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage2%20-%20Create%20Google%20API%20Project%20%26%20Client%20ID.md)
- [Stage 3](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage3%20-%20Create%20Cognito%20Identity%20Pool.md)
- [Stage 4](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage4%20-%20Update%20App%20Bucket%20%26%20Test%20Application.md)
- [Stage 5](https://github.com/Gbengard/aws-cognito-web-identity-federation/blob/main/Stage5%20-%20Cleanup%20the%20account.md)

## 1-Click Installs

Ensure you are logged into AWS and located in `us-east-1`.

- [WEBIDF](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/quickcreate?templateURL=https://techidence.s3.amazonaws.com/aws_projects/WEBIDF.yaml&stackName=WEBIDF)
