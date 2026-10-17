1. Check origin

    ```bash
    # Lists all remote names with their fetch and push URLs
    git remote -v

    # Prints only the URL assigned to origin
    git remote get-url origin

    # get exact url of your repo with suffix .git at the end
    git config --get remote.origin.url      # output: https://github.com/<your-username>/<reposiotry-name>.git

    # Shows a verbose report of URLs and tracked branches
    git remote show origin
    ```
