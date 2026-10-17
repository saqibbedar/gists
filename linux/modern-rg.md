# Modern replacement for `regex`: `rg: (ripgrep)`

1. Install it:

```bash
sudo apt update
sudo apt install ripgrep

# verify version
rg --version
```

## Commands

```bash
# 1. basic search
rg "pattern" <any-path>     # if no path search in cwd

# search using explicit pattern
rg -e "--surface" <path>        
rg -- "--surface" <path>
# Note: -e and -- are used to tell the next string is pattern not a flag without -e flag or --, you will get unrecognized error. I used --surface to search through my files to find this css class but got error hence, its a nice utility to try when you need to put --infront of your pattern

# only list filenames
rg -l "TODO"
# count total number of matches
rg -c "FIXME"

# search exact word
rg -w "test"

# Case-insensitive search (matches Text, TEXT, text)
rg -i "search-term"

# Smart case search
rg -S "Search_Term"

# verbose
rg -v "exclude_this"


# 2. Filtering by File Type

# Search only within specific file types 
rg "def " -t py

# Exclude specific file types
rg "analytics" -T html

# List all supported file type shortcuts
rg --type-list


# 3. Advanced Searching (Hidden files & Regex)

# Search hidden files and ignored files (includes .env, .gitignore files, etc.)
rg -uu "secret_key"

# search using regex
rg "error_\d{3}"
```