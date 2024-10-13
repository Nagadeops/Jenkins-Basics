# To create a freestyle job in Jenkins using parameters, follow these steps:
  
  Step 1: Create a New Freestyle Job
  
  Go to your Jenkins dashboard.
  
  Click New Item.

  Enter a job name (e.g., ParametrizedJob), select Freestyle project, and click OK.

  Step 2: Enable "This project is parameterized"

  In the job configuration page, scroll down to the General section.

  Check the box labeled This project is parameterized.

  Click Add Parameter and choose the type of parameter you want. Some common options are:

  String Parameter: For text input.

  Boolean Parameter: For true/false options (checkbox).

  Choice Parameter: For predefined choices (dropdown).

  File Parameter: For file upload.

  Password Parameter: For sensitive data.

  In this Example, we are going to see : String Parameter
  
  Choose String Parameter.

  Set the Name (e.g., GREETING).

  Optionally, set a Default Value (e.g., Hello).

  Provide a Description for users who trigger the build (optional).

  Step 3: Use Parameters in Build Steps

  Now, you can use the parameter in your build step.

  Scroll down to the Build section.

  Click Add build step and select Execute Shell command.

  Use the parameter by referencing it with ${PARAMETER_NAME}. For example, if you defined a GREETING parameter:

  echo ${GREETING}, World!

  Step 4: Save and Build

  Click Save to store the job configuration.

  To run the job, click Build with Parameters in the left sidebar.

  Enter the value for the parameter(s) and click Build.

  Step 5: View Output

. Once the job starts, click on the build number under the "Build History" section.
  
  Check the Console Output to see the result of your parameterized job.
