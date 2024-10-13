# To create a freestyle job in Jenkins that uses a shell script file, follow these steps:
  # Open Jenkins Dashboard:
    
    Log into your Jenkins instance.
    Create a New Freestyle Job:
    On the Jenkins dashboard, click on New Item.
    In the "Enter an item name" field, give your job a name (e.g., ShellScriptJob).
    Select Freestyle project.
    Click OK.
    
    Configure the Job:
    In the configuration screen, scroll down to the Build section.
    Click Add build step and select Execute shell.
    
    Enter Execute Shell Commands:
    In the shell command text box, add the shell command you want to execute. For example:
    Shell script
    echo Hello, World!
    
    Save and Build:
    Once the command is added, click Save.
    
    To run the job, click Build Now in the left sidebar.
    You can check the console output of the job by clicking on the build number under the "Build History" section,
    and then selecting Console Output.
