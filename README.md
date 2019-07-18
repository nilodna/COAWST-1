# COAWST
COAWST from svn 7/16/19, Version 3.4

Notes:
* Words that look <like this> in the instructions are placeholders and should be replaced with the name you are using; do not keep the brackets <>'s.
* Kristen initialized the CSOMIO/COAWST repository 7/16/19 from the COAWST svn repo. It's history has been preserved.
* I added in the one change to the original COAWST repo, which was a small change by Courtney to a compiler file
* I have registered for a free improved github account as being a teacher/researcher. You all have this option too (there is also an option for students).
* CSOMIO/COAWST is the group, collective, shared code repository of COAWST (located at https://github.com/CSOMIO/COAWST). We want to keep it clean of any changes except when we intend to share improved code that already works and doesn't break anything.
* repo == repository which is a code storage spot
* you'll want to stay up to date with the CSOMIO/COAWST master branch so that you don't have a harder time merging the code later and having to potentially change some of your own implementation.

Common github commands for reference:
* `git status`: check what has been added, changed, what branch you are on
* `git pull`: get changes
* `git push`: share changes


More information about git: https://www.smashwords.com/books/view/498426

Instructions for setting up and using git/github to maintain code and collaborate:
1. Get a github account of your own.
2. Fork CSOMIO/COAWST to your own github profile:
    1. on page https://github.com/CSOMIO/COAWST, click "fork" in upper right hand
    2. I clicked "fork to...  kthyng/COAWST", since kthyng is my own github user account
3. Clone the COAWST repo from your github account to your computer
    1. Click the green "clone or download" button on https://github.com/<username>/COAWST (but with your github profile name in there) and copy the link to clipboard
    2. On your computer, open terminal window and navigate to where you want to clone repo and type 
    
       `git clone https://github.com/<username>/COAWST.git` 
       
       but with <username> as your github username. This will bring all of the COAWST repo to the clone location, and call the directory "COAWST"
4. Do your work on COAWST on your own computer(s) and keep it version controlled with your github profile and with a branch; don't work on the master branch directly.
    1. Set up a remote to the group CSOMIO/COAWST repo. This will allow you to get new code when someone else has put in their part or other changes have been made.
        1. `git remote add upstream https://github.com/CSOMIO/COAWST.git`
        2. You can check your remotes with 
    
           `git remote -v`
           
            1. This shows you the github repos that you are connected with. You will have "origin", which points to your fork of COAWST on github, and "upstream" which points to the original group CSOMIO/COAWST.
        3. You can later get updates from CSOMIO/COAWST with `git pull upstream master`. You may have to merge the code with your code. Google for an example for how to merge. It's not hard generally, but you have to go through by hand if git can't figure out how to do it all automatically (that is, if you made edits to the same place someone else did).
    2. Make a new branch in your version of COAWST in the terminal window with 
    
       `git branch <branchname>`
       
    3. Work in your branch by checking out the branch: 
    
       `git checkout <branchname>`
       
        1. You can always check which branch you are in and what has been changed with 
        
           `git status`
        
    4. After you make changes to your code that you want to preserve (which you should do frequently), do these steps:
        1. add the files with changes that you want to have tracked with version control: 
        
           `git add <filenames>`
           
            1. check they are added appropriately with 
            
               `git status`
               
        2. commit the changes you have made to your local git so the changes aren't lost: 
         
           `git commit -m '<commit message>'`
           
            1. the better your commit message is, the more everyone will like you
        3. push the changes to github so they aren't only on your computer and so that you can share them: `git push`
            1. If this is the first time you are pushing your branch, it will pop up and tell you what to do
    5. If others want to work on your branched code too:
        1. Set up the other person's branch (on otheir github profile) as a remote so that you can pull their branch to be a branch in your profile.
            1. To add the oil branch from DJ's github profile to my local machine, set up his repo as another remote: 
            
               `git remote add oil https://github.com/dkobashi/COAWST.git`
               
            1. Grab DJ's code but without integrating it: 
               `git fetch oil`
               
            1. Locally change to the branch you are wanting to use: 
            
               `git checkout --track oil/csomio-oil`
               
            1. Later you can update your code if DJ has made changes:
    
               `git checkout foo` 
    
               `git pull`
               
            1. DJ will be able to get your code changes too via a pull request.
            1. Later once your code is integrated together and it works correctly, you can proceed down this list to share the code more widely.
    
    6. If your code is completed, or at a stage where it won't break your master code (be sure of this), merge it with your master branch:
        1. `git checkout master`
        2. `git merge <branchname>`
        3. now the changes from your branch are in the master branch of your local version of COAWST
        4. push the changes to your github profile so they aren't just on your computer: 
        
           `git push`
           
    7. If you want to share this code widely and it is ready to be integrated into the master branch of the CSOMIO/COAWST repo (which means it is ready to be used by others), then do a pull request:
        1. From your github profile COAWST or CSOMIO/COAWST, click on pull request and follow directions. Others will need to look at your code and it will need to be merged with the existing code.
