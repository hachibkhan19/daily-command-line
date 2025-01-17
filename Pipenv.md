### Step-by-Step Guide to Install and Setup pipenv on Ubuntu
### Step 1: Install pipx
pipx is a tool to install and manage Python applications in isolated environments.

1. Update your package list:
   ```
     sudo apt update
   ```
2. Install pipx using apt:
  ```
    sudo apt install pipx
  ```
3. Ensure pipx is ready to use:
  ```
    pipx --version
  ```
### Step 2: Install pipenv Using pipx
Install pipenv, a popular tool for managing Python virtual environments, globally via pipx.
1. Install pipenv:
  ```
    pipx install pipenv
  ```
2. Verify installation:
  * If successful, you’ll see a message like:
  ```
    installed package pipenv <version>, installed using Python <version>
These apps are now globally available:
  - pipenv
  - pipenv-resolver
  ```
### Step 3: Fix the PATH Issue
If pipenv is not accessible, it’s likely because ~/.local/bin is not in your PATH.
1. Add ~/.local/bin to your PATH:
  * Open your shell configuration file (~/.zshrc for zsh users, or ~/.bashrc for bash users):
    ```
    nano ~/.zshrc
    ```
  * Add this line to the file:
    ```
      export PATH="$HOME/.local/bin:$PATH"
    ```
2. Save the file and reload the shell configuration:
  ```
    source ~/.zshrc
  ```
### Step 4: Verify PATH Update
  Check if ~/.local/bin is now included in your PATH:
  ```
    echo $PATH
  ```
You should see /home/<your-username>/.local/bin in the output.

### Step 5: Test pipenv Installation
  ```
    pipenv --version
  ```
You should see the version number of pipenv.


