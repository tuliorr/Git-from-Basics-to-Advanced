## Section 5 - Branches

**5.1 Branch Concepts**

* A Branch in the project flow allows features or changes to be developed separately from the ```main``` project branch, which has stable project features

[branches](/images/branches.png)

* After new features are tested in separate branch, they can be merged to main branch

**5.2 Create a Local Branch**

* To list existing branches in the repository use ```git branch``` or ```git branch --list```

Note: The repository will always have its main (or master) branch

* To create a new branch use ```git branch <branch_name>``` or ```git switch -c <branch_name>```

* To change from the current branch to another branch use ```git checkout <target branch_name>``` or ```git switch <branch_name>```

* To switch to the last accessed branch use ```git switch -```

* To create a new branch and access it use ```git checkout -b <branch_name>```

Note: The branch name cannot have spaces

Note: The branches are independent, this is changes made to the branches are contained only in the changed branch, to add to the main branch it is necessary to merge

[5.2](/images/create_branch.png)

**5.3 Unsaved Changes**

* In the example below, I made a change to the index.html file and then switched branches without committing. This change will continue to be identified in the different branch, that is, if I commit it, it will include this change that was supposed to be from the other branch

* Note that when switching branches git identified the uncommitted file as "M      index.html"

Note: this situation only applies to **TRACKED** files

[5.3](/images/change_branch.png)

* To do a "clean" branch switch use ```git checkout(or switch) -f <branch_name>```

**5.4 Detached Head**

* When a specific commit is accessed, you are in 'detached HEAD'

* According to Git itself: 

*You are in 'detached HEAD' state. You can look around, make experimental changes and commit them, and you can discard any commits you make in this state without impacting any branches by switching back to a branch*

[5.4](/images/checkout_commit.png)

* So, viewing the flowchart of commits, the most recent commit always points to the previous one and so on. The main branch points to the last commit made

* The head goes along with main, that is, the most recent commit. When a commit is accessed or ```git checkout <commit_hash>```, the head is detached for that accessed commit, that is, you enter in 'detached HEAD' mode, the head is detached from main branch

[5.5](/images/head1.png)

* If a branch is created in this accessed commit (b84f1da), this new branch (zzyyxx) does not interfere with main

* When a commit is done, the HEAD pointer will go to the new branch created (zzyyxx) in the accessed commit (b84f1da), creating a new ramification

[5.6](/images/head2.png)

**5.5 Push a branch to a remote repositorie**

* To link the branch from the local to the remote repository use ```git push --set-upstream origin <branch_name>``` or ```git push -u origin <branch_name>```

**5.6 Remove branch**

* To remove a local branch use ```git branch -d <branch_name>``` or ```git branch -D <branch_name>``` (force)

Note: When a branch is deleted, all its history is also deleted

* To remove a remote branch use ```git push --delete origin <branch_name>```

Note: When a remote branch is removed, it continues to exist locally. For example, if someone made a **git clone** before the branch was deleted, it will continue to exist locally on that person's machine, if they do a **git push** the branch will be created again in the remote repository. It's necessary to inform the team that the branch was deleted

**5.7 Rename branch**

* To rename a branch use:
    * If you're check out the branch use ```git branch -m <new_name>```
    * If you aren't use ```git branch -m <old_name> <new_name>```

Note: Once a branch is uploaded to the server, it is not possible to change its name. However, it is possible to work around this situation

* If you have the branch locally, you can delete the remote branch, reconnect the branch with the changed name, and do the git push:

```git push --delete origin <branch_name>```  => ```git branch -m <new_name>``` => ```git push -u origin <branch_with_new_name>```

* This sequence of commands creates a new branch with the same content, but with a changed name. That way, it is necessary to inform the team, because someone may be working on the removed branch and if they do a git push, the old branch will be created again

**5.8 Branch history**

* To see the branch history without switch use ```git log <branch_name> --oneline``` or variations of this command
