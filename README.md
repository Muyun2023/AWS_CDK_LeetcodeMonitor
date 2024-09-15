# A cdk project with automated deployment pipeline

currently automatically deploying to 2 regions: us-east-1 and us-west-2

Must-Dos:

1. Create a Lambda Layer from the ZIP file in S3, which includes the requests library
. This is done manually by uploading the ZIP file to a S3 bucket
2. In deploy.yml, you will see ${{ secrets.AWS_ACCESS_KEY_ID_GAMMA }}, ${{ secrets.AWS_SECRET_ACCESS_KEY_GAMMA }}. these secrets need to be added to the GitHub repository. Go to repository settings -> secrets and variables (left panel) -> action -> new repository secret
![1](https://github.com/user-attachments/assets/5ea934ab-5752-4ccc-bb4e-0754e1d31bbe)
![2](https://github.com/user-attachments/assets/b8f552c5-9345-4597-ac54-aed412bbf8f8)

3. Replace with your SES-verified email and destination email. Go to AWS console, go to SES service, on the left panel,
   click on identities under Configuration, and create a new identity
## Useful commands

* `npm run build`   compile typescript to js
* `npm run watch`   watch for changes and compile
* `npm run test`    perform the jest unit tests
* `npx cdk deploy`  deploy this stack to your default AWS account/region
* `npx cdk diff`    compare deployed stack with current state
* `npx cdk synth`   emits the synthesized CloudFormation template
