Install python using uv

```bash
# list available python version's available for download
uv python list --only-installed

# install python with desired version
uv python install <version>

# Install a new python's binary and set up it as the default version then add `--default` flag.
uv python install --default 3.15
```
