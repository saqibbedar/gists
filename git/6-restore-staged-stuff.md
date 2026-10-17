```bash
git restore --staged <file>	            # Unstage a specific file
git restore --staged .	                # Unstage all files in the repository
git restore <file>	                    # Discard changes in the working tree
git restore --worktree --staged .	    # Discard all staged and working changes
```

# Permanently discard untracked files

```bash
git clean -fdn          # preview deletion
git clean -fd           # force delete
```