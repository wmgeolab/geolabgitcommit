# geoLab Git Commit Script
### The purpose of this repository is to provide the tools to automatically sync code to github on CDSW.
### NOTE: This only has to be done once per project.
***
## Instructions for use
### Step 1
Copy the file "geoLabGitCommit.py" into the CDSW project you want to backup to Github automatically.

### Step 2
On github, create a new repository on the "wmgeolab" organization.  If you aren't a member of the organization, tell Olivia and she will add you.

### Step 3
Go into your project on CDSW, and click "Jobs" on the left.
Click "New Job"

### Step 4
Choose the following:

**Name** your job something you can recognize - i.e., "Git Autocommit".
**Script**: Choose "geoLabGitCommit.py", which you copied into this project in step 1.
**Engine Kernel**: Python 3
**Schedule**: Set this to recurring
**Every**: Set this to at least one hour; this is how often your code will sync to github.
**Engine Profile**: Set this to 1 vCPU, 2 GiB Memory
**GPUs**: Set this to 0

**Click on "Set Environmental Variables"**
In the first row, under "Name" type in "access_token" (no quotes), and under value you will type in the access code you retrieve at https://forms.gle/8enxPd3jU2SoWUaTA .
Note at that website, if you type in the wrong answer it will bring you to a "Response Recorded" page.  You must go back and try again.

Once you've copied the access_token, click "Add".

Now, add a second variable.  Name this one "repository_name" (no quotes), and under value type the name of the repository you created in step 2.  Click "Add".

Double check both environmental variables look correct.

### Step 5
Under job report recepients, check failure, stopped, and timeout.  You will receive an email after each sync in case something goes wrong.

### Step 6 
Click "Create Job".  On the next screen at the far right, click the word "Run".  After a minute, under status it should show "Success", and your new files should be on github in the repository you created.  You're all done, auto-syncing is activated!
If status shows up as "Failed", you can click on the blue text under "Latest Run" to see what happened.






