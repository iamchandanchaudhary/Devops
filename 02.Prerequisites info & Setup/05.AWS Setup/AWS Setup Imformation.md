# AWS Setup

## Introduction to AWS Setup

 In this lecture, we will create a free tier account on AWS and perform essential configurations. These include creating an IAM user with multi-factor authentication (MFA), setting up billing alarms to monitor expenses, and creating a certificate using AWS Certificate Manager (ACM) for HTTPS secure connections. This lecture is longer than usual, so take your time and feel free to take breaks if you feel overwhelmed. These steps are crucial for securely managing your AWS account.

## Creating an AWS Free Tier Account
 Start by searching for "AWS free tier" and select the link for free cloud computing services. AWS provides informative videos explaining the free tier and how to monitor usage to avoid exceeding limits. We are creating a free tier account to use AWS cloud computing with minimal or no cost. Some projects may exceed the free tier, but we will set up alerts to notify us in such cases.

 Click on "Create a Free Account" and provide a valid email address, as   verification is required. Enter an account name and verify your email address with the code sent to your inbox. Set a strong root user password containing alphanumeric characters and symbols. Use a password manager if needed to securely store your password. Fill in your personal details and proceed to the next steps.

 Provide your credit or debit card details for identity verification. Note that a small amount may be temporarily deducted for verification purposes but will not be charged if you stay within the free tier and clean up unused resources. Verify your phone number by receiving an SMS code and entering it. Choose the basic support plan, which is free. After completing signup, you will see a "Congratulations" message and can proceed to the AWS Management Console.

## Logging into AWS Management Console
 Sign in to the AWS console using your root user credentials. The root user is the account used during signup and has full access. AWS frequently updates the console UI, so the interface you see may differ slightly from this lecture. However, the features and services remain the same. We will keep updating the course to minimize confusion.

 Once logged in, verify your account is active by navigating to the EC2 service. If you see your instances and no errors, your account is active. Otherwise, verify your phone and card details or contact AWS support via the support center to resolve activation issues.

## Creating an IAM User and Enabling MFA
 It is not recommended to use the root user for daily AWS operations. Instead, create an IAM user with controlled permissions.

 Navigate to the IAM service and note the security recommendation to add MFA for the root user. MFA adds an extra layer of security by requiring a six-digit code from an authenticator app, such as Google Authenticator, in addition to your password.

 Assign an MFA device to the root user by installing Google Authenticator on your phone, scanning the QR code provided, and entering the generated codes to complete setup.

 Next, create a new IAM user named "itadmin" with AWS Management Console access. Generate an auto-generated password and require the user to create a new password upon first login. Attach the "AdministratorAccess" policy to grant full permissions. Download the CSV file containing the username, password, and login URL.

 Assign MFA to this IAM user following the same process as for the root user, using Google Authenticator to scan the QR code and enter the generated codes.

 Explore the IAM user settings, including permissions, security credentials, password reset options, and access keys. Do not modify access keys at this time; they will be covered later. Familiarize yourself with these options as they will be useful in future sections.

## Setting Billing Alarms with CloudWatch
 To monitor your AWS expenses, set up billing alarms using the CloudWatch service. First, enable billing preferences by navigating to the billing dashboard and enabling invoice delivery, free tier alerts, and CloudWatch billing alerts with your email address.

 Then, go to CloudWatch in the North Virginia region (us-east-1), as billing metrics are only available there. Create a new alarm for the "Total Estimated Charge" metric in USD. Set the threshold to a desired amount, for example, 5 USD, to receive notifications when your bill exceeds this value.

 Configure the alarm to send notifications via the Simple Notification Service (SNS). Create a new SNS topic, such as "Monitoring Team," and add your email address as a subscriber. Confirm the subscription by clicking the link sent to your email. After confirmation, the alarm status will show as OK if your bill is below the threshold. You will receive an email notification if the bill exceeds the set amount.

## Requesting a Public SSL Certificate with AWS Certificate Manager
 To enable HTTPS secure connections for your domain, request a public SSL certificate using AWS Certificate Manager (ACM). This certificate validates your domain ownership and secures communication.

 Navigate to ACM and request a public certificate. Enter your domain name in the format *.yourdomain.com to cover all subdomains. Choose DNS validation as the validation method.

 After requesting, you will see the certificate status as "Pending validation." To validate, add the provided CNAME record to your domain registrar's DNS settings.

 For example, if your domain is registered with GoDaddy, log in to your GoDaddy account, navigate to your domain's DNS management, and add a new CNAME record. Use the CNAME name and value provided by ACM, removing the domain suffix and trailing dots as instructed. Save the record.

 AWS ACM will periodically check the DNS records to verify domain ownership. This process may take from a few minutes up to 48 hours depending on your domain's age and DNS propagation. Once validated, the certificate status will change to "Issued."

## Using the IAM User to Access AWS Console
 Finally, log in to the AWS console using the IAM user credentials. The IAM user login URL can be customized by creating an account alias in the IAM dashboard. This alias replaces the default account ID in the login URL, making it easier to remember.

 Use the username and password from the CSV file downloaded earlier. Upon first login, you will be prompted to change the password and enter the MFA code from Google Authenticator. It is recommended to use the IAM user for daily operations and reserve the root user for account management and billing.

## Summary
In this lecture, we have completed several important steps to set up a secure and manageable AWS environment:

- Created an AWS free tier account with verified contact and payment information.
- Enabled multi-factor authentication for both root and IAM users.
- Created an IAM user with administrator access for daily use.
- Set up billing alarms using CloudWatch and SNS to monitor expenses.
- Requested and validated a public SSL certificate using AWS Certificate Manager.

These configurations are essential for professional and secure AWS usage. We will use these setups throughout our projects.

## Key Takeaways
- Created an AWS free tier account and configured it securely.
- Set up IAM users with multi-factor authentication (MFA) for enhanced security.
- Established billing alarms using CloudWatch to monitor and control costs.
- Requested and validated a public SSL certificate through AWS Certificate Manager for HTTPS secure connections.