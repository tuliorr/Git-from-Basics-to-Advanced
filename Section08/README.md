## Section 8 - Tags

* The function of the tag is to mark important commits within a project that may have many commits, i.e., the tag acts as a pointer to a specific commit that represents an important milestone in the project

* Tags usually indicate important releases or versions and in real projects the number of tags is much smaller than the number of commits

* The tag name is unique and can be replace the commit hash in commands

**8.1 Create and list tags**

* To create a "light" tag use ```git tag <tag_name>```

* Note: the message of the light tag is the same as the commit it points to

* To create an "annotated" tag use ```git tag -a -m "<tag_message>" <tag_name>```

* The annotated tag includes more information than the light tag, such as:
    * Tagger name
    * Email
    * Creation date
    * Tag description (tag_message)

![8.1](/images/create_tag.png)

* To show the tag and thus the commit relative to it use ```git show <tag_name>```

* To show all tags in the project use ```git tag``` or ```git tag -l``` or ```git tag --list```

* To show all project tags and their comments use ```git tag -n```

![8.2](/images/list_tags.png)


**8.2 Create tag in old commits**

* To create a tag on an old commit use 

    * light tag:  ```git tag <tag_name> <commit_hash>```

    * Annotated tag:  ```git tag -a -m "<tag_message>" <tag_name> <commit_hash>```

**8.3 Send tag to repository**

* To send a tag (one) to the remote repository (Github) or server use ```git push origin <tag_name>```

* To send all tags from the local to the remote repository use ```git push --tags```

* Sending all tags at once is not recommended, as there may be local tags that have been deleted/changed in the remote repository and when sending them, they are created again, messing up the repository

**8.4 Use tags**

* The tag can be used as a commit identifier, that is, in place of the commit hash

* Then, all commands that use the commit hash can be used with the tag name as well, for example:

    * ```git checkout <tag_name>```

    * ```git diff <tag_name1> <tag_name2>```

**8.5 Remove tags**

* First the local removal is done, then the server (or remote repositorie) removal

* To remove a tag locally use ```git tag -d <tag_name>```

* To remove a tag from the server use ```git push --delete origin <tag_name>```

