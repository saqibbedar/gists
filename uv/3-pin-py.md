Pin specific installed python binary

```bash
# you can pin specific python's binary in your CWD
uv python pin 3.15

# alternatively, you can set the any version as a default binary as followingly (3 choices)

# 1. set *this version global using --global
uv python pin 3.15 --global

# 2. using shell way
export UV_PYTHON="3.15"

# 3. lastly, when you install a new python binary install with --default flag
uv python install --default 3.15

# Note: if your shell doesn't recognize your changes right away, then update shell as followingly
uv python update-shell
```