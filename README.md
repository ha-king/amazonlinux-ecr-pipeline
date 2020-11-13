# AmazonLinux ECR Pipeline

## Deployment instructions

#### Note: Create a Personal Access Token for your Github account for the AWS webhook.
##### Link: https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/creating-a-personal-access-token

This application is deployed using AWS CloudFormation.

#### CloudFormation Parameters: (required)
* GitHubRepo
* GitHubBranch
* GitHubToken (do not commit this value)
* GitHubUser
* RepositoryName (ECR repository name to be created)

#### CloudFormation deployment options:
* Local bash terminal
* <a href="https://us-west-2.console.aws.amazon.com/cloud9/home?region=us-west-2">Cloud9</a> (Oregon)
* <a href="https://us-west-2.console.aws.amazon.com/cloud9/home?region=us-west-2">Cloud9</a> (Oregon)
* <a href="https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1">CloudFormation</a> (N.Virginia)
* <a href="https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1">CloudFormation</a> (N.Virginia)

Create ECR pipeline resources: (add parameters)
```
aws cloudformation deploy --stack-name amazonlinux-ecr-pipeline --template-file cfn/ecr-pipeline-stack.yml --capabilities CAPABILITY_NAMED_IAM
```

Cleanup:
```
Delete S3 objects for CodeSuite before deleting CloudFormation stacks

Delete Stacks:

aws cloudformation delete-stack --stack-name amazonlinux-ecr-pipeline

```

## Credits


## License

This library is licensed under the MIT License.
