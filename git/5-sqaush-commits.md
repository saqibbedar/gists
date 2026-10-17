## Step 1: Set up a messy history to play with

Let's intentionally create three quick, messy commits on your machine so we have something to fix. Run these commands one by one in your terminal:

# 1. Create a dummy file and commit it

```bash
echo "Line 1" >> experiment.txt
git add experiment.txt
git commit -m "feat: start working on cool feature"
```

# 2. Make a typo fix commit (the kind of noise we want to get rid of)

```bash
echo "Line 2 typo" >> experiment.txt
git commit -am "fix: oops fixed a typo"
```

# 3. Complete the work

```bash
echo "Line 3 final" >> experiment.txt
git commit -am "feat: finish cool feature"
```

If you run git log --oneline, you will see three separate commits. We want to squash these into one clean commit before pushing.

## Step 2: Trigger the Interactive Rebase

We want to modify the last 3 commits we just made. To do this, tell Git to open the interactive editor looking back 3 steps:

```bash
git rebase -i HEAD~3
```

## Step 3: The Secret Text File Interface

Your terminal is going to open a text editor (like Nano, Vim, or VS Code) displaying a file that looks like this. Notice that the oldest commit is at the top, and the newest is at the bottom:

```bash
pick 1a2b3c4 feat: start working on cool feature
pick 5e6f7g8 fix: oops fixed a typo
pick 9z8y7x6 feat: finish cool feature

# Rebase 7ebc8df..9z8y7x6 onto 7ebc8df
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
```

At the bottom, Git lists its commands. Your job is to change the word pick next to the commits you want to alter

To compress everything into the very first commit, change the text to look like this:

```bash
pick 1a2b3c4 feat: start working on cool feature
squash 5e6f7g8 fix: oops fixed a typo
squash 9z8y7x6 feat: finish cool feature
```

(Tip: You can just type s instead of the whole word squash).
Save and close the file:

* If using Nano: Press Ctrl + O, then Enter, then Ctrl + X.
* If using Vim: Type :wq and press Enter.

## Step 4: Craft your final commit message

Immediately after you save and close, Git will pop open a second text file. This file combines all three of your original commit messages and asks you what you want the final, clean message to be.

It will look like this:

```bash
# This is a combination of 3 commits.
# This is the 1st commit message:

feat: start working on cool feature

# This is the commit message #2:

fix: oops fixed a typo

# This is the commit message #3:

feat: finish cool feature

Delete the messy lines and rewrite it so it looks pristine:

feat: completely build out the new cool feature asset
```

Save and close this file just like you did the first one.

## Step 5: Check your work!

Your terminal will print: Successfully rebased and updated.

Now, run your log command:

```bash
git log --oneline
```

Look at that! The three separate, messy commits are completely gone. In their place is one single, beautiful commit containing all of your code changes. You are now ready to push a perfectly clean branch to GitHub.
Try running those steps on your machine right now. Let me know:
