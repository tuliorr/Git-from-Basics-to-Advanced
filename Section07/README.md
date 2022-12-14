## Section 7 - Source Code Management (SCM)

**7.1 Intro**

* SCM is a standard used by software developers to streamline and organize the creation and distribution of code

* However, the SCM can also be used for other purposes, such as: a writer who is writing a book and needs to control the changes made to each chapter; a video editing that has many changes, etc.

* It can be understood that the SCM is a version control of the project files and not only for software

**7.2 SCM Example**

* The example below has a main branch (main) that contains the stable code, which has already been tested and runs without breaking with all its features, or which contains the chapters of the book without grammatical errors for the writer's example.

* The develop branch contains new or changed features under test and from the develop branch other branches are created to test other features

* When the version finishes the test phase in the develop branch and is stable, it is merged into the main branch

* This network graph is an example of how source code control is performed in projects. depending on the project this flowchart can have a different structure

![7.1](/images/scm.png)

* Github provides a visualization of the network graph with all branches too
    






