Requirements:
Git
AWS CLI
npm
yarn
cdk
github account

#To run this thing:

* Fork this project on github
* Create a codestar connection in your aws account: https://docs.aws.amazon.com/dtconsole/latest/userguide/connections-create-github.html
* Copy and paste the arn of this codestar connection in line 10 of the amplify-nextjs13.ts
* Create a secret in the secret manager of type other. Enter the key "GithubOauthToken" and value an Personal access token that you need to make on github (Developer Settings -> Personal access tokens)
* Give it a name (in my case "secret") and save it
* Copy the arn of this secret and paste it in line 29 of the web-stack.ts
* Browse to the deployment folder and run "npm install" and "npm run build"
* Type "cdk ls" and "cdk synth" to verify if there are no errors in your cdk code
* I also ran this command but I'm not sure if it was needed: cdk bootstrap aws://accountid/region
* cdk deploy
* Verify that the codepipeline runs once and creates the infra for the amplify app
* Go to the amplify app 
* The main branch should deploy succesfully and work
* PS: I turned on the basic auth feature in amplify, the username is "hello" and the password is "awssupport". You can disable it in web-stack.ts
