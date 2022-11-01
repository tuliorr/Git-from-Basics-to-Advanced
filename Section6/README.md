## Section 6 - Merge

**6.1 Merge Changes**

* To merge a branch use ```git merge <branch_name>```

Note: Git merge always brings changes from the identified branch (<branch_name>) to the branch you are checking. Git will incorporate the changes from the identified branch into the branch you are checking

* To see which branches have not yet been merged use ```git branch --no-merged```

* To see which branches were merged use ```git branch --merged```

**6.2 Resolving conflicts**

* In the example below, a develop branch and index.html file was created on the master branch

* Then, the file was changed from ```lang="en"``` to ```lang="pt"``` and committed on the **master branch**

![6.1](/images/lang_pt.png)

* In the **develop branch** the file was changed from ```lang="en"``` to ```lang="pt-br"``` and commited 

![6.2](/images/lang_pt-br.png)

* The branch was changed to the **master** and the ```git merge develop``` was done. So, we can see that there was a conflict in the merge, because the merge change was from ```lang="en"``` to ```lang="pt-br"```, but the file was changed to ```lang="pt"``` on the master branch

![6.3](/images/merge_conflict-br.png)

* In this case, git does not know what to choose and generates a conflict. This is so that changes in the master (or main) branch are not lost during a merge

* Opening the file in VScode, it will appear the current change (head -> master branch) and the incoming change (develop branch)

Note: since a conflict was generated, the master branch will be in merging status (master | MERGING)

* There are several options to solve the conflict
    * To abort the merge use ```git merge --abort``` or ```git reset --hard```
    * The file change can be done manually (using the text editor) by deleting the current change or the incoming change. However, depending on where the conflict appears, it may be difficult to locate
![6.4](/images/resolve_merge.png)
    
    * 








