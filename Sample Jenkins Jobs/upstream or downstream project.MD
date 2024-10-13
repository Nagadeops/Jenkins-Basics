# To create a Jenkins setup where a freestyle job is either an upstream or downstream project, you can configure job
  triggers that build dependent jobs. Here’s how you can create this setup:

# Scenario:
  Upstream Project: A job that triggers another job.

  Downstream Project: A job triggered by an upstream project.

Step 1: Create the Upstream Job
Create a new freestyle job:
On the Jenkins dashboard, click New Item.
Enter a name for your upstream project (e.g., UpstreamJob).
Select Freestyle project and click OK.
Configure the job:
Scroll down to the Build section.
Add any necessary build steps, such as executing a shell script (Ex: echo Hello, World!). 
Save the job by clicking Save.

Step 2: Create the Downstream Job
Create another freestyle job:
Go back to the dashboard and click New Item.
Enter a name for your downstream project (e.g., DownstreamJob).
Select Freestyle project and click OK.
Configure the job:
Scroll down to the Build section and add the necessary build steps same as Upstream Job.
Save the job by clicking Save.

Step 3: Configure the Upstream Job to Trigger the Downstream Job
Go to the Upstream Job Configuration:
Open the upstream job (e.g., UpstreamJob), click Configure.
Scroll down to the Post-build Actions:
Click Add post-build action.
Select Build other projects.
Add Downstream Job:
In the Projects to build field, enter the name of the downstream job (e.g., DownstreamJob).
Choose whether you want the downstream project to be triggered:
Only if build succeeds: Downstream job triggers only when the upstream job is successful.
Even if the build is unstable or fails: Downstream job triggers regardless of upstream build result.
Save the Upstream Job by clicking Save.

Step 4: Test the Setup
Build the Upstream Job:
Go to the upstream job's page and click Build Now.
Check the Downstream Trigger:
Once the upstream job completes, Jenkins will automatically trigger the downstream job.
You can monitor the build history of both jobs to ensure they are linked.

Step 5: Verify the Result
Go to the UpstreamJob's build history.
You will see a link to the triggered downstream job on the build page of the upstream job.
You can also go to the DownstreamJob and see that it was triggered by the upstream build.

Visualizing the Job Chain:
You can install the Build Pipeline Plugin to get a visual representation of upstream and downstream jobs.
