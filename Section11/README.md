## Section 11 - Utilities

**11.1 Alias**

* If you use a command often during your work routine, you have the option to abbreviate that command to make it easier to type

* Use ```git config --global alias.<abbreviation> <command>```

* For example: 
    * To abbreviate ```git status``` for ```git s``` use ```git config --global alias.s status```

* If the command has a blank space use ```git config --global alias.<abbreviation> <'command'>```

* For example: 
    * To abbreviate ```git log --oneline``` for ```git line``` use ```git config --global alias.line 'log --oneline'```

* To descart alias use ```git config --global --unset alias.<abbreviation>```

**11.2 Grep**

* The Grep command is a linux command and can be used in Git too

* This command is useful to search a branch or a commit by a specified word

* For example:
    * To search for a branch containing the name **task** use ```git branch | grep task```
    * To search for a commit containing the name **feature** use ```git log --oneline | grep feature```

**Note:** This command is case sensitive 