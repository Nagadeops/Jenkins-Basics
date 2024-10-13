# Create a freestyle job in Jenkins that can be triggered remotely via an HTTP request (using the "Trigger builds remotely" feature), follow these steps:

Step 1: Create a Freestyle Job

Open Jenkins Dashboard:

Log into your Jenkins instance.

Create a New Job:

Click on New Item.

Enter a job name (e.g., RemoteTriggerJob), select Freestyle project, and click OK.

Step 2: Configure the Job

Add Build Steps:

Scroll down to the Build section.

Add any build steps you want, such as executing a shell script.

Example (shell script):

echo Job triggered remotely!

Step 3: Enable "Trigger builds remotely"

Go to the "Build Triggers" section:

Scroll down to the Build Triggers section.

Enable Remote Build Trigger:

Check the box labeled Trigger builds remotely (e.g., from scripts).

In the "Authentication Token" field, enter a token (e.g., myToken). This token will be used as a security measure to authorize the remote build request.

Example:

Token: myToken

Step 4: Save the Job

Scroll to the bottom and click Save.

Step 5: Trigger the Job Remotely

Now that the job is configured, you can trigger it remotely using an HTTP request.

Construct the Remote Trigger URL:

The URL format to trigger the job remotely is:

http://<JENKINS_URL>/job/<JOB_NAME>/build?token=<TOKEN>

Replace:

<JENKINS_URL> with your Jenkins server URL.

<JOB_NAME> with the name of the job (RemoteTriggerJob).

<TOKEN> with the authentication token you set (myRemoteToken).

Example URL:

http://localhost:8080/job/RemoteTriggerJob/build?token=myRemoteToken

Send the Request:

Open a browser or use a tool like curl to send an HTTP GET request to the URL.

Example using curl:

curl -X POST http://localhost:8080/job/RemoteTriggerJob/build?token=myRemoteToken


Step 6: Verify the Job

Go to your Jenkins job page and check the Build History to ensure the job was triggered successfully.

You can view the console output to see the details of the execution.

# Additional Inputs:

Security Consideration: Ensure your Jenkins instance is protected and has appropriate authentication enabled (e.g., Jenkins user login) if exposing this trigger to external networks.

You may also need to configure Jenkins’ security settings (via Manage Jenkins > Configure Global Security) to allow remote builds.
