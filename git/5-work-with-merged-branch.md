# Work with merged branch

It is never good to work on your already merged branch especially when you have linear history or branch was merged with `squash and merged`.

However, sometimes we may require it then this is the cleanest way of doing it as followingly:

1. Download remote changes on your default main branch

    ```bash
    git fetch origin
    git status          # verify your status
    ```

2. Merge the changes into your local main branch

    ```bash
    git merge origin/main                   # OR, use below command
    git merge --ff-only origin/main         # --ff-only: fast-forward tells git to slide pointer from this commit to latest
    ```

> Note: step 1 and 2 can be done performed using `git pull origin main`, however, fetching and then merging is quite nice way to demonstrate whole the process.

3. Switch back to your working branch

    ```bash
    git switch <branch-name>
    ```

4. Because `squash and merge` diverge the branch and to fix it we can simply rewrite the history with `rebase` 

    ```bash
    git rebase main
    ```

    What happens behind the scenes:

    1. Git temporarily lifts up your 3424215 commit.

    2. It fast-forwards your experiment branch base pointer up to cd142f1 (main).

    3. It tries to re-apply your changes. Because the changes are already exactly present on main, Git is smart enough to realize there is no new work to add.
    
    4. The Result: Your local experiment pointer will instantly snap onto cd142f1 alongside main. It will become perfectly linear, and you can start typing new code immediately!


5. Finally push your updated history 

    ```bash
    git push --force-with-lease origin <branch-name>
    ```