### How to install Zsh in ubuntu
Here is the step-by-step process to fix the issue and properly set up Zsh, Oh My Zsh, and plugins such as zsh-autosuggestions and zsh-syntax-highlighting. We'll start fresh to ensure everything is set up correctly.

### Install Zsh: If you haven't already installed Zsh, do so:
  ```
    sudo apt update
    sudo apt install zsh -y
  ```

### Install Oh My Zsh: Remove any incomplete installation:
  ```
    rm -rf ~/.oh-my-zsh
  ```

### Then, install Oh My Zsh:
  ```
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

### Verify Installation: After installation, ensure Zsh is working and set as your default shell:
  ```
    echo $SHELL
  ```
### Output should be:
  ```
  /usr/bin/zsh
  ```
### Step 2: Install Plugins

### Install zsh-autosuggestions: Clone the repository into the Oh My Zsh custom/plugins directory:
```
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
### Install zsh-syntax-highlighting: Similarly, clone the repository:
  ```
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  ```

### Verify Plugin Installation: Run:
  ```
    ls ~/.oh-my-zsh/custom/plugins
  ```
You should see both zsh-autosuggestions and zsh-syntax-highlighting listed.


### Step 3: Configure .zshrc
### Open the .zshrc file:
```
  nano ~/.zshrc
```
### Look for the plugins=() line. Add the plugins inside the parentheses:
```
  plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```
### Make sure the ZSH variable points to the correct directory:
```
  export ZSH="$HOME/.oh-my-zsh"
```
### Save and exit the editor (in nano, press CTRL+O, then Enter, and CTRL+X).

### Step 4: Reload Configuration
Reload the .zshrc file to apply the changes:
  ```
    source ~/.zshrc
  ```
