1. fetch changes

    ```bash
    git fetch origin        # Downloads updates for all branches that exist on the remote repository (including main, develop, feature branches, and tags).

    git fetch origin main   # Downloads updates only for the main branch.  
    ```

2. Merge changes

    ```bash
    git merge origin/main       # (Merge the changes I already downloaded into my current branch)

    git merge --ff-only origin/main     # directly fast-forward (slide) pointer

    # direct step does not even require fetch and merge separately but does it on fly 
    git pull origin main        # (Go to the internet, look at origin, grab main, and pull it down)
    ```
    
## The Difference Between origin/main vs origin main

| Concept | origin/main (With a Slash) | origin main (With a Space) |
|---|---|---|
| What it is | A pointer/branch on your local machine. | Two separate arguments passed to a command. |
| Meaning | It represents "the state of the main branch on the remote (origin) the last time you fetched data." | origin is the remote repository URL, and main is the branch name on that remote server. |
| How it works | It is read-only and lives locally in your .git folder. It doesn't need an internet connection to read. | It tells Git to actively look up or push/pull data over the internet to the origin server's main branch. |
| Example Command | git merge origin/main (Merge the changes I already downloaded into my current branch) | git pull origin main (Go to the internet, look at origin, grab main, and pull it down) |