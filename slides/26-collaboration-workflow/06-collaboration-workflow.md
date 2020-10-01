### Lab: Collaboration workflow

<!-- .slide: class="is-lab" -->

---

## Git branches

![Git branches](../../img/branches.png)

---

## Git checkout

![Git checkout](../../img/git-commands/checkout.svg)

<!-- ``` mermaid
sequenceDiagram
    participant lw as Local: Workspace
    participant ls  as Local: Staging (index)
    participant lr as Local: Repository
    participant rr as Remote: Repository
    #Note over rr,lr: Create a copy of an remote repository
    rr->>lr: git clone
    Note over lw,lr: Switch to another branch on local workspace
    lr->>lw: git checkout
    #Note over lw,ls: A new files
    lw->>ls: git add
    #Note over ls,lr: Persist changes in local repository
    ls->>lr: git commit
    #Note over lr,rr: Persist changes in remote repository
    lr->>rr: git push
    #Note over lr,rr: Update latest changes from remote repository
    #rr->>lr: git fetch
    #Note over lw,rr: Update latest changes from remote repository & Apply on local repository
    rr->>lw: git pull
``` -->

---

## Git checkout commands

Checkout the <branch> to local workspace
```
git checkout <branch>
```

Create a new branch on the local repository based on the current branch
```
git checkout -b <name-of-new-branch>
```

---

## Lab: Collaboration workflow

When we would like to make changes to a file in the repository, we take 6 steps: 

1. Creata a new branch on local repository
2. Modify files in local repository
3. Push changes to remote respository
4. Create a pull request on github
5. Review the pull request on github
6. Merge the pull request into master on remote repository

---

### Creata a new branch on local repository

- We want to checkout the master branch and pull the latest update from the central repository 

    ```
    git checkout master
    git pull
    ```

- We creata a new branch based on the current branch (master) we are working on

    ```
    git checkout -b feature/change-feature-file
    ```

---
 
### Modify files in local repository

- Open visual studio code

```
code .
```

- In `MyWebSite/spec/MyNewFeature.feature`, we add a scenario: 

    ```
Feature: Title of this cool feature 

In order to perform my task 
as a user 
I want to be helped in a cool way

scenario:
Given a user has 3 apples
When he removes 1 apple
Then he only has 2 apples
    ```
 
- Save the file

- Verify that Git has not yet staged the changes (i.e. they are not included in a commit): 

    ```
git status
    ```
 
---

### Add it locally 

- We have to add the file to the next commit: 

    ```
    git add .
    ```

- Optionally, verify that Git is now tracking the file: 

    ```
    git status -s
    ```
 
---

### Commit it locally 

- All files that have been changed (or added) can now be committed. Each commit has to have a Commit Message that specifies what has been changed in this commit. 

    ```
    git commit -m "Scenario added for MyNewFeature" 
    ```

- Optinally, verify that the change now has been committed locally: 

    ```
    git status
    ```

---

### Push it to the repository 

- After making commiting the change locally, you can push it to master: 

    ```
    git push 
    ```
 
- The push doesn't work, because the remote doesn't know the new branch. Follow the advice of the error

    ```
    git push --set-upstream origin feature/change-feature-file 
    ```

---

### Create a pull request on github

- Navigate to your git repository https://github.com/{username}/Git-workshop
- Navigate to `Pull request` -> `New pull request`
    - Select base repository: `{username}/Git-workshop`
    - Select base: `master`
    - Select head repositoy: `{username}/Git-workshop`
    - Select head: `feature/change-feature-file`
    - Click on `Create pull request`
    - Click on `Create pull request`

---

### Review the pull request on github

- Add comment `This change looks good`
- Goto `Files changed`
    - Review the the changes in the file `MyWebSite/spec/MyNewFeature.feature`
    - Mark the file as `Viewed`

---

### Merge the pull request into master on remote repository

- Go back to `Conversation`
    - Click on `Merge pull request` -> `Confirm merge`
    - Click on `Delete branch`

---

## Lab checklist

- Creata a new branch on local repository ✅
- Modify files in local repository ✅
- Push changes to remote respository ✅
- Create a pull request on github ✅
- Review the pull request on github ✅
- Merge the pull request into master on remote repository ✅