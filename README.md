A project to demonstrate using AWS STS assume role functionality to access AWS resources in another account.

## Running

`./gradlew listS3Buckets -ProleArn=<role-arn>`

Your local credentials should have the `sts:AssumeRole` permission to assume the provided role.

## Explanation

The code in *[build.gradle](build.gradle)* uses the AWS Java SDK to generate temporary credentials for the provided role
using the `AWSSecurityTokenService`. 

It then uses those temporary credentials to list S3 buckets using the `AmazonS3Client`. 