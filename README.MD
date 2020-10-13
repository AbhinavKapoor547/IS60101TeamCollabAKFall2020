# **TEAM COLLABORATION PROJECT**
##### by _Abhinav Kapoor_

## **Introduction To GitFlow**

### _What is **GITFLOW**?_ 

* GitFlow is a branching model for Git, created by **Vincent Driessen**.
* It was very well suited to collaboration and scaling the development, which help get attract a lot of attention.

#### Key Benefits of **GITFLOW**

* Parallel Development
    * GitFlow makes parallel development very easily by isolating new development from finished work.
    * New development will be performed in **feature branches** such as non-emergency bug fixes and features.
    * Finally, when the developer is happy the code is ready to release, he/she can merge back into main body of code.
    * Note: if you are asked to switch from one task to another, you just need to commit your changes and then create a new feature for your new task. Furthermore, when the task is done, just simply checkout your original feature branch, and you can continue where you left off.
* Collaboration
    * Feature branch makes it easier for two or more developers to collaborate on the same feature.
    * Feature branch is a sandbox where the only changes are the changes necessary to get the new feature working. As a result, that makes it very easy to observe and follow what each collaborator is doing.
* Release Staging Area
    * Once new development is completed, it gets merged back to into **develop branch**, which is known as the staging area for all completed features that haven't yet released.
    * Hence, when the next release is branched off of **develop**, it will automatically contain all the new stuff that has been finished.
* Support For Emergency Fixes
    * GitFLow supports **hotfix branched**, meaning branched made from a tagged release.
    * User can use these to make an emergency changes, safe in the knowledge that the hotfix will only contain your emergency fix
    * There is no risk that you will accidentally merge in new development at the same time.

##### GITFLOW VISUAL DEMO(_How it works?_)
###### New development (new features, non-emergency bug fixes) are built in feature branches:

![](Assets/images/GITFLOW%20IMG%201.jpg)

###### Feature branches are branched off of the develop branch, and finished features and fixes are merged back into the develop branch when they’re ready for release

![](Assets/images/GITFLOW%20IMG%202.jpg)

###### When it is time to make a release, a release branch is created off of develop:
       
![](Assets/images/GITFLOW%20IMG%203.jpg)

###### The code in the release branch is deployed onto a suitable test environment, tested, and any problems are fixed directly in the release branch. 
###### Note: This deploy -> test -> fix -> redeploy -> retest cycle continues until you’re happy that the release is good enough to release to customers. When the release is finished, the release branch is merged into master and into develop too, to make sure any changes made in the release branch aren’t accidentally lost by new development.

![](Assets/images/GITFLOW%20IMG%204.jpg)

###### The master branch tracks released code only. The only commits to master are merges from release branches and hotfix branches. 
###### Note: Hotfix branches are used to create emergency fixes:

![](Assets/images/GITFLOW%20IMG%205.jpg) 

###### They are branched directly from a tagged release in the master branch, and when finished are merged back into both master and develop to make sure the hotfix isn’t accidentally lost when the next regular release occurs. 
     
##### GIT COMMANDS AND TERMINOLOGY
##### We will explain each git commands to better understand GitFlow

* REPOSITORY 
    * A directory or storage space where your projects can live.
    * **GitHub** users shorten this to “repo."
    * It can be local to a folder on your computer, or it can be a storage space on **GitHub** or another online host. You can keep code files, text files, image files, you name it, inside a **repository**.
    * For Example, Repository is like a ebook which stores all the chapters and audiobook files in it. 
    * We create by going to github>mainpage>ClickNewgreenbox, also via Webstorm Newproject>Nameyourproject>Added.gitignoreandREADME.MD>VCS>enable version control>GIT>OK

* Clone
    * Git **clone** is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository.
    * Cloning a local or remote repository. Cloning a bare repository. Using shallow options to partially clone repositories.
    * For example, you clone a repository via github>click on the CODE green tab>copy the HTTP address>open Webstorm>git from version control> in our case git and paste the HTTP address. Now you have a copy of the same repository.

* Fork
    * A **fork** is also copy of a repository.
    * Forking a repository allows you to freely experiment with changes without affecting the original project. Which helps us differentiate forking from cloning.
    * forks are used to either propose changes to someone else's project or to use someone else's project as a starting point for your own idea.
    * For example, if we fork the same repo, we can make changes in repo without anybody's permission, which automatically matches you the admin.
    
* Branch
    * A **branch** is essentially is a unique set of code changes with a unique name.
    * Each repository can have one or more branches. 
    * The main branch — the one where all changes eventually get merged back into, and is called **master**.
    * For example, we can think branches at the chapters of the book which stores many pages, and yes a book can have multiple chapter so can the repo, usually have two or more branches.

* Commit
    * For Example, “an individual change to a file (or set of files). It's like when you save a file, except with Git, every time you save it creates a unique ID (a.k.a. the "SHA" or "hash") that allows you to keep record of what changes were made when and by who. 
    
* Merge
    * Merging is Git's way of putting a forked history back together again. 
    * The git merge command lets you take the independent lines of development created by git branch and integrate them into a single branch.
    * Note: All the commands presented below merge into the current branch.
    * For example, when working with a partner, in order to share your own code to repo will be done via git merge command.

* Checkout
    * A "**checkout**" is the act of switching between different versions of a target entity.
    * The git checkout command operates upon three distinct entities: files, commits, and branches.
    * In the Undoing Changes topic, we saw how git checkout can be used to view old commits.
    * For example, git checkout is used to get pull request on local, fix bug, added features to a branch.

* Push
    * The git **push** command is used to upload local repository content to a remote repository.
    * Pushing is how you transfer commits from your local repository to a remote repo. It's the counterpart to git fetch , but whereas fetching imports commits to local branches, pushing exports commits to remote branches.
    * For example, while write code in local master on webstorm, we use git push command to upload our code to the remote master on github.

* Pull
    * The git pull command is used to fetch and download content from a remote repository and immediately update the local repository to match that content.
    * Merging remote upstream changes into your local repository is a common task in Git-based collaboration work flows.
    * For example, Git pull helps us download updated remote master to local master in our webstorm project.
    
* Remote Add / Remove / Show
    * Add
        * Git remote **add** is to add a "short name", such as origin , and it can be any name as well, which is like an alias to a URL.
        * Origin is the usual path of where the remote repo points to.
        * For example, in http://git-scm.com/book/en/Git-Basics-Working-with-Remotes under "Adding Remote Repositories"
    * Remove 
        * To remove a remote, navigate to the directory your repository is stored at, and use the git remote rm (or git remote remove ) command followed by the remote name: git remote rm remote-name.
        * For example, to remove remote named testing , you would type: git remote rm testing.
    * Show
        * This command help see the fetch and push.
        * For example, if you want to see which remote master is pushing and fetching from which local master. 
    
* Status
    * The **git status** command shows the state of the working directory and the staging area.
    * It allows us to see staged changes and the files that aren't being tracked by Git. 
    * The **Status** output does not display any information about the committed project history.
    * For example, if we want to give our output in short format. We will use git status --short--origin master.
   
* Master Branch
    * In Git, "**master**" is naming convention for a branch.
    * After cloning, a project from a remote server, the resulting local repository has a single local branch; which is called "**master**" **branch**.
    * Hence, we can see master can be seen as a repository's default branch.
    
    
    

    

