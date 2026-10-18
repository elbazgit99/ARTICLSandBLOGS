# MOST COMMEN git COMMANDS
clone single branch : git clone --branch name --single-branch < URL>  

Current local branch name : git branch --show-current   
Remote branches : git branch -r
all Branches : git branch -a

MERGE :  
first fetch if is does not showing branches  
git switch main  
git pull origin main  
git merge dev  
git push origin main  


if you want to merge and sais fatal: refusing to merge unrelated histories  
run   : git merge origin/branch --allow-unrelated-histories  
  
If you want to stop the merge and return to the state before it started:  
git merge --abort    



resolve branch conflicts :  

Step 1 Clone the repository or update your local repository with the latest changes.  

git pull origin main   

Step 2 Switch to the < branch name  > of the pull request.    

git checkout < branch name  >  

Step 3 Merge the main branch into the < branch name  >  

git merge main  

Step 4 Fix the conflicts and commit the result.


Step 5 Push the changes.

git push -u origin < branch name  >  



The arrow on a folder icon in **GITHUB** often means the folder is a Git submodule or a symbolic link,  

1. Check what Git sees  

git status  
git ls-files --stage  


If the folder appears with mode 160000, Git is tracking it as a submodule.  
2. Check if the folder is a separate Git repository  
Run:
ls -la  




ARROW IN GITHUB FOLDER MEANS A SUBMODEL

1. Remove the submodule reference from Git
git rm --cached feat


This removes the tracked reference, not the folder's files.
2. Remove the nested Git metadata
Check whether directory/.git is a file or directory:
ls -la directory


Remove its .git metadata. On Windows Git Bash, use the appropriate command:
- If .git is a file: rm feat/.git  
- If .git is a directory: rm -rf feat/.git  


3. Add the folder as normal files
git add directory
git commit -m "message"
git push origin main



1. Remove the Git username and email from the current repository :   
git config --local --unset user.name
git config --local --unset user.email



2. Remove the Git username and email from all Repos :  
git config --global --unset user.name
git config --global --unset user.email


3. Add the Git username and email to current Repo :  
git config --local --unset user.name
git config --local --unset user.email


4. Add the Git username and email to all Repos
git config --global user.name
git config --global user.email


5. Check your current Git identity
git config user.name
git config user.email
