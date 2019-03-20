# alexa-via-ethos-example
An Amazon Alexa personal assistant example that leverages the Ellucian Ethos Integration component to deliver real-time data to this student-use skill. The skill provides Colleges and Universities a quick start example of how a voice-enable skill could be constructed to help their students and staff interact with the institution using only their voice and a personal assistant device.

## To get started
### Get necessary files
1. Download or clone the repository.
2. Open the 'AlexaOnEthosPlatform' folder in the source files using your favourite command line tool.
3. Execute 'npm install'. Note: 'npm' is a package solution that will download and update dependencies for this project so that you can package it for production. You can download the installation files from https://www.npmjs.com/get-npm .

### Create your Alexa skill
1. Open your Alexa Skills Developer Console (requires Amazon account) @ https://developer.amazon.com/alexa/console/ask?
2. Click 'Create Skill' and fill in the options. Make sure to select the 'Custom' model and 'Provision your Own' backend resource.
3. Use the 'Start from Scratch' template as we'll be uploading our own intents anyway.
4. At this point you are ready to start creating your intents. On the left hand menu you will see a menu item name 'JSON Editor'. Click on this option.
5. Open the 'AlexaOnEthosPlatform.json' file at the top level of your downloaded files in your favorite text editor. Copy all the text and replace the text in your JSON Editor window.
6. Click the 'Save Model' button at the top of the screen. Then click 'Build Model' at the top of the screen.
7. Your Alexa skill is now ready, but we need to create the back-end service to respond to requests.

### Create your Lambda back-end service
1. Log into your AWS console and follow the steps documented @ https://developer.amazon.com/docs/custom-skills/host-a-custom-skill-as-an-aws-lambda-function.html#create-a-lambda-function-for-an-alexa-skill to create a basic shell Lambda package. Note: you can use any 'blueprint' from AWS, or simple bypass this stage and create an empty function. Make sure to select Node.JS v8.10 as your backend language.
2. Open the index.js file inside the alexa-via-ethos-example folder of your downloaded files. This is the main working file of your backend service.
3. Update all of the content between the '<>' symbols. These are typically URLs and environment specific setting of your Ethos installation, as well as your ERP API. If you are not sure, you can proceed without these now and correct them at a later stage.
4. Create a ZIP file that contains ALL of the contents of the alexa-via-ethos-example folder. This will be our deployed package.
5. On the Lambda console, within your Lambda function, scroll down to the 'Function code' section. At the bottom of that section you will see a 'Code entry type' select list. Select 'ZIP file', with a runtime selection of 'Node JS 8.10' and a handler selection of 'index.handler'. Click 'Upload'.
6. Select your ZIP file and then click 'Save' on your Lambda console. 

### Configure your Alexa skill to use the backend service
1. In your Alexa Skills Developer Console window, click on the 'Endpoint' menu item.
2. In the 'Default region' textbox paste the ARN of your Lambda service. The ARN can be copied from the top of the Lambda console window (i.e. not the URL, search the page for ARN if you are unsure).
3. Save the Alexa skill, and click 'Build Model' one final time. You are now ready to start testing.

### Testing your skill
There are several ways to test the skill:
1. Use the Alexa Test console from the tab located in your Developer Console screen.
2. When you have the output generated by the Test console (i.e. the content that Alexa sends to the backend service, Lambda in this case) you can copy the output text and save this as a repeatable test in the Lambda console. This allows you to test directly from Lambda using recorded test scenarios, which can save time.
3. Add your developed skill to your Alexa device and test it with a real-life interaction. This last approach is a very useful final step to test the design and build of your skill.

Recommended reading on this subject: https://developer.amazon.com/docs/devconsole/test-your-skill.html
