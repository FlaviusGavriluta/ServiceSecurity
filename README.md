# Service Security

## Story

As a security engineer you are asked to guard protect and secure your premises. Security has been seen as technology burden that puts a lot of strain on developers and their applications. You as a DevSecOps engineer should not just give the choice of `Move fast` or `Stay secure` and choose one or the other. Instead, have both - _move fast, innovate, be agile and at the same time _be secure_.

## What are you going to learn?

- How to secure S3 buckets in AWS
- How to secure EC2 instance in AWS
- What are various types of KMS keys
- How to create KMS keys
- General advice for cloud security best practices
- How to move fast and stay secure

## Tasks

1. Create an S3 bucket in AWS to store private information, protect it by restricting public access
    - Ensure that public access to this bucket and its objects is blocked
    - Enable automatic encryption of new objects stored in this bucket
    - Enable versioning to preserve, retrieve, and restore every version of every object stored in your bucket

2. Create and protect an EC2 instance in AWS
    - Choose Ubuntu Server 20.04 LTS (free tier eligible)
    - Create a new security group for testing purposes called `restrict-ssh`
    - Add a rule to `restrict-ssh` allowing SSH access from your own IP only

3. Create and configure keys
    - A single encryption key
    - A public and private key pair

4. [OPTIONAL] Here is a list of AWS Cloud security best practices
    - - Stop using `root` account
- Using IAM, create yourself a new account for administrative purposes.
- (Extra) Create unique IAM users for all aws users inside your environment.
- Enable multi-factor authentication, MFA on all of your interactive web console logins.
- Make use of access tokens for authentication to sign API calls. See temporary security credentials.
    - - Log and retain account activity (who did what) using CloudTrail. By default CloudTrail is enabled for 7 days, explicitly create a trail if you want to go further than that. - GuardDuty - managed threat detection service continuously monitors for malicious or unauthorized behavior. 30-day free trial available to every new account.
    - - AWS systems manager helps by maintaining security compliance by scanning EC2 instances against your patch configuration and custom policies.
- Use private VPC and subnets whenever possible and let LoadBalancers or CloudFront face off to the internet.
- Ensure that your security groups for both public and private subnets are appropriate.
    - - Protect your S3 buckets and objecs through ACLs, bucket, and access point policies.
- Do not ever use clear-text credentials such as keys, tokens, usernames, and passwords in source code or config files.
- Use AWS Secrets Manager to protect your secrets. Easily rotate, manage, and retrieve credentials, api keys and other secrets.

## General requirements

None

## Hints

- By not using `root` account you reduce the attack surface and opportunities for attackers.
- It might be tempting to share accounts and passwords among users, this is __bad__ security practice as it does not provide traceability into actions within your account.
- AWS supports __software__ and __hardware__ MFA tokens. _Software_ -  applications that support `open TOTP` standard such as google authenticator and tamper evident _hardware_-based tokens like Gemalto.
- With MFA enabled, when a user signs in to AWS they will be prompted for their username and password, first factor, as well as an authentication code from their MFA device, or the second factor.

## Background materials

- <i class="far fa-exclamation"></i> [Encrypting Data](project/curriculum/materials/pages/web-security/aws-encryption.md)
- <i class="far fa-exclamation"></i> [AWS S3 access best practice](project/curriculum/materials/pages/web-security/security-in-s3.md)
- <i class="far fa-book-open"></i> [AWS Key Management Service](https://medium.com/better-programming/aws-key-management-service-all-you-need-to-know-8c6b0e17a2d0)
- <i class="far fa-video"></i> [Using AWS KMS for data protection](https://www.youtube.com/watch?v=hxWvbNvj2lg)
- <i class="far fa-video"></i> [How encryption works in AWS](https://www.youtube.com/watch?v=plv7PQZICCM)
- <i class="far fa-video"></i> [S3 Security](https://www.youtube.com/watch?v=7M3s_ix9ljE)
