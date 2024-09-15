# A CDK project that notifies users about their LeetCode progress via email. Utilized Github Action to create an automated deployment pipeline

currently automatically deploying to one region: us-west-2. You can uncomment the deploy.yml to deploy to more prod stages/regions

Must-Dos before running the project:

1. Create a Lambda Layer from the ZIP file in S3, which includes the requests library
. This is done manually by uploading the ZIP file to a S3 bucket: [requests_layer.zip](https://github.com/user-attachments/files/17007644/requests_layer.zip)
![3](https://github.com/user-attachments/assets/8aacbf7d-caa0-43da-9202-963c0bd33cbe)
2. In deploy.yml, you will see ${{ secrets.AWS_ACCESS_KEY_ID_GAMMA }}, ${{ secrets.AWS_SECRET_ACCESS_KEY_GAMMA }}. these secrets need to be added to the GitHub repository. Go to repository settings -> secrets and variables (left panel) -> action -> new repository secret
![1](https://github.com/user-attachments/assets/5ea934ab-5752-4ccc-bb4e-0754e1d31bbe)
![2](https://github.com/user-attachments/assets/b8f552c5-9345-4597-ac54-aed412bbf8f8)
3. Replace with your SES-verified email and destination email. Go to AWS console, go to SES service, on the left panel,
   click on identities under Configuration, and create a new identity
![4](https://github.com/user-attachments/assets/edc70d67-4ad2-4c25-bdf0-1fa2538fb481)

## How to get started:
* `aws configure`   set up aws account connection -> in ChatGPT, search "how to set up aws configure" . if you don't have the AWS Access Key ID and Secret Access Key, search "AWS Access Key ID and Secret Access Key"
```
$ aws configure
AWS Access Key ID [None]: yourID
AWS Secret Access Key [None]: yourKey
Default region name [None]: us-west-2
Default output format [None]: json
```
* `npm run build`   compile typescript to js
* `cdk bootstrap`   If this is your first time using AWS resources, you need to run cdk bootstrap once before running cdk deploy,
* `cdk deploy`      This is an optional step as you can run below git commands. deploy this stack to your default AWS account/region
* `git add .`
* `git commit -m "new code"`
* `git push`

## Useful commands
* `aws configure`   set up aws account connection
* `npm run build`   compile typescript to js
* `npm run watch`   watch for changes and compile
* `npm run test`    perform the jest unit tests
* `cdk bootstrap`   before running cdk deploy, you need to run cdk bootstrap once when deploying to a new region
* `npx cdk deploy`  deploy this stack to your default AWS account/region
* `npx cdk diff`    compare deployed stack with current state
* `npx cdk synth`   emits the synthesized CloudFormation template

