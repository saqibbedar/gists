# `--env-file`

When working with large code base repository and you don't want to install python-dotenv package then use this cmd to load the environment variable and run python file which is accessing an environment variable.

```bash
# load environment variables from .env file and then python can use those
uv run --env-file llms/.env python llms/gemini.py
```

Another approach is to save environment variables in shell memory as global variables.

```bash
export API_KEY="secret"

# -c flag = command
# -m flag = module
python -c 'import os; print(os.environ.get("API_KEY"))'     # OR

# using uv
uv run -c 'import os; print(os.environ.get("API_KEY"))'
```