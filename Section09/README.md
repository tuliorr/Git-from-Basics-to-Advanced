## Section 9 - Stash

**9.1 What is it used for?**

* Git stash archives changes made to the working copy to allow the user to work on something else or switch branches and then come back to finalize the change

* This command is useful when you need to switch context quickly and work on something else, but have not yet finished changing the code and are not ready to commit

* For example: if the user makes a change to a file, which is not yet ready to be committed, and wants to switch branches to perform another activity, this change will go together to the other branch. The git stash serves exactly to avoid this situation, the command will archive the changes and clean the branch

**9.2 Basic**

* To archive changes use ```git stash```

**Note: The default of the command is to stash changes in the staging area and on tracked files. The stash will not be performed on untracked files**

* To include non-tracked files in the stash use ```git stash -u``` or ```git stash --include-untracked```

* To view all changes arquived using stash use ```git stash list```

* To bring the changes back into current branch use ```git stash apply```

**Note: the stash commands consider the most recent stash that is represented by the number 0, that is, the higher the number of the stash the older it will be**

* Git stash apply gets the most recent stash (number 0), to get a specific stash use ```git stash apply stash@{<stash_number>}```

* To apply the stash and already remove it use ```git stash pop``` (get the most recent one) or ```git stash pop stash@{<stash_number>}`` (to specify the stash)

* To remove the stash use ```git stash drop``` (newer) or ```git stash drop stash@{<stash_number>}```

**Note: the stash can be applied to any branch**

* If the stash is for another branch, this can be created from the stash, using ```git stash branch <branch_name>``` (latest stash) or ```git stash branch <branch_name> stash@{<stash_number>}}``` (to specify the stash)

* To view a summary of the stash use ```git stash show```

* To view the complete stash comparison use ```git stash show -p```