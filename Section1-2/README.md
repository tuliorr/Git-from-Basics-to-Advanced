## Section 1 - Version Control

* System that records changes to a file or set of files over time so that you can recall specific versions later

* Most used for software development, provides change history and can be used on small or large projects

* Many people's version-control method of choice is to copy files into another directory. This approach is very common because it is so simple, but it is also incredibly error prone.
  It is easy to forget which directory you're in and accidentally write to the wrong file or copy over files you don't mean to

**1.1 Functionalities**

* History
  * Change between versions
  * Restore old versions in case there is a problem

* Branches
  * Possibility to create different versions from a single starting point
  * Merge functionalities after testing

  ![1.1](/images/branch.png)

* Work Fronts
  * Parallel development on the same project

* Traceability
  * Identify when one or more changes were made

**1.2 Types of Version Control System (VCS)**

* Local
  * It has a simple database that keeps all changes to files under revision control
  * Example: RCS
  ![1.2](/images/local.png)

* Centralized
  * Server holds all history
  * Any problem on the server impacts the progress of the project
  * Example: VS Team Foundation Server, Subversion and Perforce
  ![1.3](/images/centralized.png)

* Distributed
  * Every computer has a copy of the repository
  * Changes are made locally
  * Does not depend on a single computer
  ![1.4](/images/distributed.png)

**1.3 Git**

* Git is a Distributed VSC created in 2005

* Features
  * Local actions
    * History navegation
    * Branch creation
    
  * Integrity
    * Once the file is added, its entire history is saved
    * Removing a file is done through a version addition, which says that the file has been removed

  * Non-linear development
    * Different versions from a single point
    * Facility for several people to make changes without file dependency

  * Independence from project complexity
    * Efficient for small or large projects
    * Usage mode remains the same

## Section 2 - Installation and Configuration

* Check if your machine have Git installed
  * Open terminal and type ```git```

* [Download Git here](https://git-scm.com/) and install
