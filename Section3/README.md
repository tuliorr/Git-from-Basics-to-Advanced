## Section 3 - Basic Commands

**3.1 User Configuration**

* Right click and select ```Git Bash Here```
  * With Git Terminal open, type:
    * git config --global user.name "your name"
    * git config --global user.email "your email"

Note: No need to config this every time you use git

**3.2 Create a local repositorie**

* ```Git Bash Here``` on folder that you want create a repositorie

* Use the command ```git init``` to initialize a repositorie

* This repositorie created will be on master branch

**3.3 Add changes**

* The ```git status`` command shows current information about the repository, such as:
  * Which branch being used
  * Untracked files
  * Files to be committed

* Whenever a file is added to the repository it will be as an untracked file, that is, git will not track your changes

* You need to add this file with the command ```git add <file name>``` for git to track your changes

Note: to add all existing files in the folder you can use one of the commands:
```git add .```
```git add -A```
```git add -all```
```git add *```

* With the file tracked, every change will be identified and shown in ```git status```

![3.1](/images/add.png)

* To untrack the file use ```git rm --cached <file name>```

**3.4 File Life cycle**

* The file has 4 phases in Git
  * Untracked
  * Staged
  * Committed
  * Modified

![3.2](/images/life_cycle.png)

New file ```Untracked``` -> add file ```Staged``` -> commit ```Committed```

![3.3](/images/cycle1.png)

file modified -> stage file with git add ```Staged``` > commit ```Committed```

![3.4](/images/cycle2.png)

**3.5 Viewing Changes**

* To to see the difference between a committed file and a modified file use ```git diff``

![3.5](/images/diff.png)

* If you already staged the file, you need use ```git diff --cached``` or ``` git diff --staged```

![3.6](/images/diff_cached.png)

**3.6 Commits History**

* To see the history of commits use ```git log```

* For each commit that was made will appear: Hash; Author; Date; and Comment about the commit 

* If you need to view a summary information use ```git log --oneline```

![3.7](/images/log.png)

* If you need see only N commits use ```git log -N```

* It's possible to combine the ```git log --oneline``` + ```git log -N```

* To see the difference of the files changed in the commit use ```git log -p``` or ```git log --patch```. Show git log + git diff

![3.8](/images/patch.png)

* To see the files that were modified in each commit use ```git log --stat``` or ```git log --shortstat``` to view a summary information

**3.7 Changing a Commit**

* To change the commit (last one) message use ```git commit --amend -m <"correct message">```

* To add a forgot file in a commit (last one) use ```git commit --amend --no-edit``` (staged file)

Note: This commands will create another commit with the correct message/forgot file and will discard the old one (the commit hash will change)

**3.8 Using previous commits** 

* To access files referring to previous commits use ```git checkout <commit hash>```

* This command will update the files in the repository folder according to the files of the accessed commit, that is, as if the folder went back in time exactly as it was in the accessed commit

* For example, if a file was created after the commit was accessed, that file will "disappear" from the folder

* To return to the current commit (HEAD) use ```git checkout master```

* When returning to the master, the files will appear again in the folder

**3.9 Undoing changes**

* To revert the file to the latest version use ```git checkout <file name>```

Note 1: It does not partially revert the changes, all changes made are removed and the file reverts to the last version

Note 2: Reverts to the last version of the commit, if the file is untracked it will give an error

* To remove untracked files use ```git clean -f```

* To remove a staged file use:
  * ```git rm --cached <file name>``` se nao existir nenhum commit no repositorio
  * ```git restore --staged <file name>``` se ja existir pelo menos um commit no repositorio

* During development, there may be a situation where several changes are made and files are created, which will be distributed as staged, not staged and untracked. In this situation, you may find yourself needing to go back to the last commit because it didn't work out. In this situation use ```git reset --hard```

** Warning: ** This command will delete all files (if they are new files) or revert all changes (if they are previously committed files) that are staged, not staged and untracked

**3.10 Bypassing files**

In application development, there are files/folders that are automatically generated during runs, that is, they are files that change constantly and do not need to be versioned.

* As these files are present in the repository, they will appear as untracked files, but can be ignored through .gitignore

* Create a .gitignore file with ```touch .gitignore```

* Open this created file and write the name of the files or the extension to be ignored

* For example:
   * I created the config.bmp file that will not be versioned
   * This file will appear as untracked, but i want git to ignore it
   * So I created a .gitignore using ```touch .gitignore```
   * In .gitignore I wrote ```*.bmp```, that is, git will ignore all files with that extension

![3.9](/images/gitignore.png)

* Github provides several templates for different languages with files that should be ignored 
  * https://github.com/github/gitignore

* If the file that you want ignore are already added (or tracked) use ```git update-index --skip-worktree <file name>```

* To reverse this command use ```git update-index --no-skip-worktree <file name>```

**3.11 Cloning Repository**

* Use ```git clone <origin folder name> <destination folder name>``` or ```git clone <https link from github>``` to clone from Github

* This command will clone the entire contents of the folder, including the commits history
