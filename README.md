## Git Operations & Commands

### *Create Repositories*
  1. Create Central Repository on GitHub
  2. Create Local Repository
     * Install Git on your local machine
     * Create a folder on your local machine which will serve as the repo. Inside this folder, right click anywhere and select ‘Git Bash’ – this will open-up Git Emulator (Terminal).
     * New project (this will create a .git folder inside your local repository)--- **$ git init**	 
     * Joining an existing project --- **$ git clone** 
### *Sync Repositories*
  Add your central repository as your origin to your local repository ---**$ git remote add origin “[link]”**  
  (Click on the green “Clone or Download” button inside the central repository for the link.)
### *Fetch all files into your local*
  Updating your local repository --- **$ git pull origin master**
### *Making Changes*
  1. *Add to Index*
     * Adding a single file to your index:  --- **$ git add test_file.txt**
     * Adding multiple changes all at once: --- **$ git add -A**
  2. *Commit* - "snapshot of the repository"
     * Commit a single file --- **$ git commit -m "folder name changed"**
     * Commit multiple changes --- **$ git commit –a –m “adding 3 files”**
  3. *Lookup your commits/snapshots* 
     Git stores all commits --- **$ git log**

### *Branching*
  *Why branching* - Let’s say you want to add new features on to the main branch. You want to work on those new feature individually and you don’t want to interfere with the master branch - create a branch.
  Branches are pointers to a specific commit. There are two types of branches:
  - Remote-tracking branches – are branches that is  going to connect your local branches to your central repository.
  - Local branches – you create only in your workspace.
    * Lists all local branches in the current repository --- **$ git branch**
    * Creates a new branch        --- **$ git branch [branch-name]**
    * Switch/move around branches --- **$ git checkout [branch-name]**
### *Merging*
After you have create a new branch and developed a new feature in this branch, you need to merge to the project.
  - It is a way to combine the work of different branches together.
  - Allows to branch off, develop a new feature & combine it back in.
Now, merge the branches(folder) that you have created in the master branch. (Make sure you checkout in the destination branch(master))
    * Merge branches  ---  **$ git merge [branch]**
	* View the changes   ---  **$ cat [filename]**	
	
*Notes:*
- To view the changes in the terminal, make sure you are checkout in the same branch.
- You need to merge the branch to the master after any type modification/changes.
- After merging, you can ls the files when your are in the destination folder.
### *Git Push – ‘To Central Repository’*
  Once we have completed all changes we want to contribute the final draft to our central repository.
  * Push the changes to the central repository (from local master to central repo) ---**$ git push origin master**
  * Push the changes into different branch (not interfere with master branch). ---**$ git push origin firstbranch**
  
  Note: Make sure you checkout and work on the repository you just created (firstbranch).
  * Roll-back to previous version of a commit ---**$ git checkout [first 8 hexdig] [filename]**
  
  Note: First, check your log for the previous version *$ git log*, and copy the commit hash (the first 8 hexa digits).
