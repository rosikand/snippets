---
layout: default
title: Push/pull to Github with git 
---

# Push/pull to Github with git 

This is a simple guide on how to push native source files from the command line to a Github repository. 


## Setting up

1. First, set up the repo on Github. 
2. Then, separately, open the terminal and in the directory you wish to push to that Github repo you just created. 
    1. Type: 
    
    ```bash
    git init 
    ```
    
3. Then, add the files to the staging area: 
    
    ```bash
    git add .
    ```
    
4. Commit the additions: 
    
    ```bash
    git commit -m "Initial commit"
    ```
    
5. Connect to Github: 
    
    ```bash
    git remote add origin <git-repo-url>
    ```
    
6. Set branch: 
    
    ```bash
    git branch -M main
    ```
    
7. Push the commit: 
    
    ```bash
    git push -u origin main
    ```
    

## New additions

Every time you want to update the Github repo, simply do: 

```bash
git add .
git commit -m "Another commit" 
git push -u origin main
```

## git `pull`

Let’s say someone updates the remote repository on Github but of course your local folder will stay the same. To update your native folder to reflect the changes, use `git pull`: 

```bash
git pull origin <branch-name>
```

See [here](https://www.freecodecamp.org/news/git-pull-explained/) for more.
