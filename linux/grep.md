```bash
grep -riE "context managers?" .

```

- `-r`: recursively

- `-i`: case-insensitive

- `-E`: enable extended regex (This allows the use of the ? quantifier.)

- `.`: search in current working dir

```bash
# Only Show the File Names
grep -rilE "context managers?" .

grep -riE --exclude-dir=.venv "context managers?" .

grep -riE --exclude-dir={.venv,.git,__pycache__} --exclude="*.md" "namedtuple" main/ai-ml/
```

- `--exclude-dir=.venv`: ignore .venv (as its large dir) and only search through other files

- `--exclude-dir={.venv,.git,node_modules}`: exclude multi-files

- `--exclude="*.log" --exclude="*.pyc"`: exclude files  


# Modern alternative

```bash
# no need to pass .dir's or binary files as they are discarded automatically
rg "namedtuple" main/ai-ml/
```

Next, read this [modern-rg](modern-rg.md) for grep alternative.