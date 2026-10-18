# Shell Variables

1. Create a temporary (in-memory) variables in shell environment:

    ```bash
    name="Saqib Bedar"          # it will create a variable in shell's memory

    # access variable
    echo $name                  # Saqib Bedar   
    echo "Hello, ${name}"       # Hello, Saqib Bedar
    ```

> Note: this variable will be removed as soon as terminal gonna dormant or it is killed.

2. Global variables

    ```bash
    export API_KEY="MY API KEY"         # export saves variable into environment variables
    ```

    > Note: this will also be removed, to write it permanently you need to save variable into your terminal config file i.e., nano ~/.bashrc and paste your desired variable.

3. View saved variables (local and global):

    In Bash, the `set` command is a built-in tool used to configure shell options and manage shell variables.

    Think of it as the **control panel** for your current terminal session. It does two main things depending on how you use it:

    - Without any arguments (`set`): It lists every single variable and function currently stored in the terminal's memory.
    
    - With flags (e.g., `set -e`): It changes how the terminal behaves (like telling a script to instantly crash if any command fails).


    ```bash
    # Shows all variables, including local shell variables and shell functions
    set | less

    # Shows only environment variables
    printenv | less
    ```

4. Search Variables

    ```bash
    set | grep name
    printenv | grep MY_GLOBAL_KEY
    ```

5. Access using Python

    ```bash
    export GEMINI_API_KEY=""
    ```