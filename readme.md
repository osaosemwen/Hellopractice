# Tutorial on Jenkins Integration with GIT (SCM)
 
### Step 1

Create a simple program, in this case a simple interation for printing with Java. This can be written with eclipse or any scripting environment
Save it an ensure the program works, by running it on command line or in the eclipse environment .. note the location (/$PWD of the program/project)

### Step 2
Create a Jenkins job to first test the program from its current location using the execute shell option on the Jenkins configure job project. 
on the execute shell column under the build section or tab in the configure window, go to the directory of the project.
write shell commands to run the program, as you would on a regular shell window. if it is succesful, next


### Step 3
Add this program or project to Git.
- Go to the location or folder of the the project from the terminal window on your macbook/windows ```$ cd /Users/../../SampleJavaProject" ```
- Initialize the repository entering ``` $ git init ```
- Check the number of files in the repo, which has been initialized using ``` $ git status ``` , 
  if the files are not intialized it will be highlighted red. 
- To add the files which are not initialized, use ``` $ git add .``` ,
  The '.' indicates the present directory or folder, if you are not in your present directory enter the map to the repository you want initialized.
- Confirm again that the file are initialized, using ``` $ git status ```.
- Commit this files using ``` $ git commit ``` ("optionally you can add a message") using ``` $ git commit -m "Just added the file" ```
- To connect local repo to your github account, create a project, it is recommended it is similar to your project name on local repository, copy the location of the repository from your github account, you will need these git link for in other push your files/repo to github, using ``` $ git remote add origin $ https://github.com/osaosemwen/Hellopractice.git ``` 
- Next you will be prompted to enter your github account as well your password, if you have not already done so. 
- To push the repo enter ``` $ git push -u origin master ```, 
  if you refresh your repository on github you would see a copy of all your local files commited to your github repo


### Configure Jenkins Job to run the repository from github

- First confirm you have github plugin downloaded and available on your Jenkins (using manage plugins option available from the Manage Jenkins link)
- Next go the the project initially configured on your Jenkins, click on configure, this time on the source code management option chose Git, instead of the defualt (None), Then enter the link to your repository on github on the columns that opens after clicking 'git'
- I like to add build triggers, hence click on Poll SCM, and give the frequecy of the triggers you would like to use. (you can understand this by clicking on the question mark on the side. In my case I choose every 15 minutes. So, if there are any changes on the github this would trigger an automated build of the Job, from github account to jenkins. 

Thats it Enjoy!! :)

