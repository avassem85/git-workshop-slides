sequenceDiagram
    participant lw as Local: Workspace
    participant ls  as Local: Staging (index)
    participant lr as Local: Repository
    participant rr as Remote: Repository
    Note over rr,lr: Create a copy of an remote repository
    rr->>lr: git clone
    Note over lw,lr: Switch to another branch on local workspace
    lr->>lw: git checkout
    Note over lw,ls: A new files
    lw->>ls: git add
    Note over ls,lr: Persist changes in local repository
    ls->>lr: git commit
    Note over lr,rr: Persist changes in remote repository
    lr->>rr: git push
    Note over lr,rr: Update latest changes from remote repository
    rr->>lr: git fetch
    Note over lw,rr: Update latest changes from remote repository & Apply on local repository
    rr->>lw: git pull
