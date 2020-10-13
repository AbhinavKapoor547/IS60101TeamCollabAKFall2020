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
     

    

