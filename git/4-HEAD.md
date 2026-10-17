# HEAD~1 vs HEAD@{1}

These two look almost identical, but they mean completely different things. The key difference is that HEAD~1 looks at your repository's commit history, while HEAD@{1} looks at your personal activity log.
Here is the direct breakdown:

| Command | What it actually means | What it tracks |
|---|---|---|
| HEAD~1 | "Move back to the parent commit of my current commit." | The shared, chronological timeline of code commits. |
| HEAD@{1} | "Move back to the exact place I was standing 1 action ago." | Your private, local action diary (git reflog). |


```bash
git reset --soft HEAD@{1}
git reset --soft HEAD~1

# another common flag (to wipeout everything)
git reset --hard HEAD@{1}
git reset --hard HEAD~1
```