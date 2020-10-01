### Lab: Clone repository

<!-- .slide: class="is-lab" -->

---

## Git clone

![Git clone](../../img/git-commands/clone.svg)

<!-- ``` mermaid
sequenceDiagram
    participant lw as Local: Workspace
    participant ls  as Local: Staging (index)
    participant lr as Local: Repository
    participant rr as Remote: Repository
    Note over rr,lr: Create a copy of an remote repository
    rr->>lr: git clone
    #Note over lw,lr: Switch to another branch on local workspace
    #lr->>lw: git checkout
    #Note over lw,ls: A new files
    #lw->>ls: git add
    #Note over ls,lr: Persist changes in local repository
    #ls->>lr: git commit
    #Note over lr,rr: Persist changes in remote repository
    #lr->>rr: git push
    #Note over lr,rr: Update latest changes from remote repository
    #rr->>lr: git fetch
    #Note over lw,rr: Update latest changes from remote repository & Apply on local repository
    #rr->>lw: git pull
``` -->

---

## Git clone commands

Clone a remote repository to local repository
```
git clone <url remote repository>
```

Clone a remote repository to local repository with specific directory name instead of name of remote repository
```
git clone <url remote repository> <directory name>
```

---

## Git clone

Clone remote repository

``` bash
git clone https://github.com/{username}/Git-workshop.git
```
⚠️ *Replace {username} with your own github username*

This creates a directory “Git-workshop” in the workspace-directory, makes the a local Git repository, and creates a copy of all content in the central Git repository. 

---

## Lab checklist

- Remote repository cloned to local repository ✅
  