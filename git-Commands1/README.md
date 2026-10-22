# MOST COMMEN git COMMANDS


push empty commit:  
run : 
```bash
git commit --allow-empty -m "Trigger Build"
```

rename branch 
run : 
```bash
git switch branch name
git branch -m new name
``` 

clean working tree :  
run : 

```bash
git fetch origin
git rebase origin/main
```  

clone single branch :     
```bash
git clone --branch name --single-branch < URL>  
```  



if create nested repos in local and refused to add content remove the folder remotly byt keep it localy :   
run :  
```bash
git rm -f --cached  file
git rm -rf -f --cached folder

```

Current local branch name : 

```bash
git branch --show-current  
```   
Remote branches :   
```bash
git branch -r  

```   
all Branches :   
```bash
git branch -a  

```   


MERGE :  
first fetch if it does not showing branches  
```bash
git switch main  
git pull origin main  
git merge dev  
git push origin main  

```   

if you want to merge and sais fatal: refusing to merge unrelated histories  
run   : 
```bash

git merge origin/branch --allow-unrelated-histories  
```   
  
If you want to stop the merge and return to the state before it started:   
```bash

git merge --abort    
```   



resolve branch conflicts :  

Step 1 Clone the repository or update your local repository with the latest changes.  

```bash
git pull origin main   

```   

Step 2 Switch to the < branch name  > of the pull request.    
```bash

git checkout < branch name  >  
```   

Step 3 Merge the main branch into the < branch name  >  
```bash

git merge main  
```   

Step 4 Fix the conflicts and commit the result.


Step 5 Push the changes.
```bash

git push -u origin < branch name  >  
```   



The arrow on a folder icon in **GITHUB** often means the folder is a Git submodule or a symbolic link,  

1. Check git tracking 
```bash

git status  
git ls-files --stage  
```   


If the folder appears with mode 160000, Git is tracking it as a submodule.  
2. Check if the folder is a separate Git repository  
Run:
```bash

ls -la  
```   




ARROW IN GITHUB FOLDER MEANS A SUBMODEL

1. Remove the submodule reference from Git
```bash

git rm --cached feat
```   


This removes the tracked reference, not the folder's files.
2. Remove the nested Git metadata  

Check whether directory/.git is a file or directory:
```bash

ls -la directory
```   


Remove its .git metadata. On Windows Git Bash, use the appropriate command:
- If .git is a file: 
```bash

rm feat/.git  
```    
- If .git is a directory:  
```bash
 rm -rf feat/.git  

```   

3. Add the folder as normal files
```bash
git add directory
git commit -m "message"
git push origin main

```   



1. Remove the Git username and email from the current repository :   
```bash

git config --local --unset user.name
git config --local --unset user.email
```   



2. Remove the Git username and email from all Repos : 
```bash
git config --global --unset user.name
git config --global --unset user.email

```    


3. Add the Git username and email to current Repo :  
```bash

git config --local --unset user.name
git config --local --unset user.email
```   


4. Add the Git username and email to all Repos  :
```bash

git config --global user.name
git config --global user.email
```   


5. Check your current Git identity  :
```bash

git config user.name
git config user.email
```   
