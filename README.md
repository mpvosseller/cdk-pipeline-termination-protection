# Repo demonstrating CDK Pipelines bug with terminationProtection

This repo demonstrates a bug with CDK Pipelines where the `terminationProtection` property of a `Stack` in a `Stage` of a `CodePipeline` is ignored.

## Instructions

1) Fork this repo
2) Create a plain text secret in `SecretsManager` with your github token 
3) Update `githubOwner`, `githubRepo`, and `githubAccessToken` in the file `myapp-pipeline-stack.ts`
4) Run `npm install`
5) Run `npm run cdk deploy`
6) Log into the CloudFormation console
7) Wait for the `MyappPipelineStack` stack to deploy
8) Wait for the CodePipeline to complete and the `Prod-MyappStack` stack to be deployed
9) Observe that the `MyappPipelineStack` stack correctly has termination protection enabled
10) Observe that the `Prod-MyappStack` stack does NOT have termination protection enabled. **This is the bug**

# Welcome to your CDK TypeScript project!

This is a blank project for TypeScript development with CDK.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

## Useful commands

 * `npm run clean`   remove all generated files
 * `npm run build`   compile typescript to js
 * `npm run watch`   watch for changes and compile
 * `npm run test`    perform the jest unit tests
 * `cdk deploy`      deploy this stack to your default AWS account/region
 * `cdk diff`        compare deployed stack with current state
 * `cdk synth`       emits the synthesized CloudFormation template
