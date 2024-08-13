### How to Install Python 3.12 on Ubuntu 22.04
[How to Install Python 3.12 on Ubuntu 22.04](https://www.linuxtuto.com/how-to-install-python-3-12-on-ubuntu-22-04/)

### You can use the poetry env use command to set the Python version for your project
- poetry env use 3.12
  
### Installing pipx
```
    sudo apt update
    sudo apt install pipx
    pipx ensurepath
    sudo pipx ensurepath --global 
```
### Install Poetry using pipx
  - pipx install poetry
    
### Install zsh
  - sudo apt install zsh
  -  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

### Poetry configuration zsh
   - Step1:
     ```
       nano ~/.zshrc
     ```
   - Step2:Add the following line to include Poetry's installation path:
     ```
       export PATH="$HOME/.local/bin:$PATH"
     ```
   - Step3: Save the file and reload your Zsh configuration:
     ```
      source ~/.zshrc
     ```
   - Step4: Check if it works:
     ```
      poetry --version
     ```
