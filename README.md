# LabVIEW_Starter_Repo
This will act as a starter repository for LabVIEW projects.

# Quick links
1. [How to Use this repo](https://github.com/solitontech/LabVIEW_Starter_Repo/tree/feature/initial#how-to-use-this-repo)
2. [Creating YAML](https://github.com/solitontech/LabVIEW_Starter_Repo/tree/feature/initial#step1-creating-yaml-file)
3. [Basic YAML details](https://github.com/solitontech/LabVIEW_Starter_Repo/tree/feature/initial#step2-details-of-yaml-file)
4. [Creating a Self-hosted runner](https://github.com/solitontech/LabVIEW_Starter_Repo/tree/feature/initial#step3-adding-a-self-hosted-system)
5. [Deleting a Self-hosted runner](https://github.com/solitontech/LabVIEW_Starter_Repo/tree/feature/initial#step4-deleting-a-self-hosted-runner)
6. [Assignment file hierarchy](https://github.com/solitontech/LabVIEW_Starter_Repo/tree/feature/initial#step5-assignment-file-hierachy)
7. [Branch Protection Setting]()

# Steps

1. Create a public repo with README and add each assignments in separate branches
2. Create a YAML file (in detail below)
3. Add the Tests folder to corresponding assignments
4. Add your system as a self-hosted runner

# Prerequisites

1. Caraya Unit Test Framework
2. Drona
3. G- CLI

Install them from VIPM if not available.

*NOTE: Kindly follow the steps below in creating files*

# How to use this repo
![Use_template](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Use%20Template.png)

![create_repo](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/create_repo.png)

It is recommended to uncheck the INCLUDE ALL BRANCHES so that only the main branch is copied.


# STEP1: Creating YAML File

![image](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/image.png)

Click SETUP A WORKFLOW YOURSELF and paste the code from the YAML file of this repository.
(After commiting in GitHub pull the updates to your local)

# STEP2: Details of YAML File

![YAML_Image](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/YAML.png)

1. This will trigger the test to run (only if connected to GitHub through Windows Powershell) once there is a PR or push to the master/main branch. [Press ctrl+/ to uncomment it from the YAML template]
2. Follow this [link]() to set up a Self-hosted system. Refer this for detailed assistance [link](https://solitontech-my.sharepoint.com/:w:/p/sadhana_suresh/EUg5HBnxLrpCqPJ7OgUee3IBjahCa6hl3Jtg0OSPKQXD-Q?e=hvmr8B)

![Github_Workspace_Image](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/GH%20Workspace.png)

3. ${{ github.workspace }} --> To see the directory you can echo this and check. Call the Test vi in the run command.


# STEP3: Adding a self-hosted system
![Runner-1](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Runner-1.png)

![Runner-2](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Runner-2.png)

After selecting Settings> Runners> New self-hosted runner, a page will be opened (as shown in the image below) 
Copy and paste the commands in the WINDOWS POWERSHELL. 

![Runner-3](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Runner-3.png)

![Runner-4](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Runner-4.png)

If the build fails due to windows execution policy, then follow the link below to remove the restrictions. Useful Links: 
[About ExecutionPolicy](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.3) and 
[Set-ExecutionPolicy](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-7.3) --> Set this as UNRESTRICTED.
Set-ExecutionPolicy Unrestricted --> Type this by running PowerShell by giving Run as Administrator 

![Runner-5](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Runner-5.png)

After successfully connecting to GitHub, we can run the workflow manually by clicking RUN WORKFLOW or set a TRIGGER in the YAML (.yml) file when there is a PR or Push to the main/master branch.  

A mail will be sent to the mail id of the GitHub account when the build fails by default.

# STEP4: Deleting a self-hosted runner

![Remove_Runner-1](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Remove%20Runner.png)

![Remove_Runner-2](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Remove%20Runner2.png)

Don't click FORCE REMOVE THIS RUNNER
Instead copy the command and open Windows PowerShell.

![Remove_Runner-3](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Remove%20Runner3.png)

Move to actions-runner directory and paste the command
Change .sh to .cmd as shown in the image above.

# STEP5: Assignment File Hierachy

![Files_Image](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Files.png)

Have the Project files, Main.vi and Tests folder

![Tests_Image](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Tests.png)

The Tests Folder will contain the Test vi, Test library, Drona ini file and Test results folder.

![Test_Results](https://github.com/solitontech/LabVIEW_Starter_Repo/blob/feature/initial/README%20Images/Test_folder.png)

The Test Results folder will contain a blank xml document. This has to be created because a empty folder cannot be added to the GitHub Repository. 

To create a xml document copy the content from blank xml document > paste it in a text document and save it as .xml

When the YAML file runs the report generated gets saved in the actions_runner folder of the self hosted runner.
