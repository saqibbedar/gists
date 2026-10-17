List python:

```bash
# check uv default python version
uv run python --version 

# locate the active or default Python binary
uv python find      # return default binary

# list python (installed + available for download)
uv python list      # return installed + available for download

# list only installed on your machine
uv python list --only-installed     # return only installed

# list python version's available for download
uv python list --only-downloads
```