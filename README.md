## Steps for successful setup of your local machine

# Part 1: Dependencies you will need to work with

## Install homebrew
```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"```

### To avoid bugs run:
 ```brew update && brew doctor```

## Install asdf
```git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.1```
```echo -e '\nautoload -U +X compinit && compinit' >> ~/.zshrc```
```echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.zshrc```
```echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.zshrc```
```source ~/.zshrc```

## Install rvm
```curl -sSL https://get.rvm.io | bash -s stable```
``` source ~/.rvm/scripts/rvm```

## Install Node.js
```asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git``` # https://github.com/asdf-vm/asdf-nodejs
```bash ~/.asdf/plugins/nodejs/bin/import-release-team-keyring```
```asdf install nodejs 12.16.3```
```asdf global nodejs 12.16.3```

## Install yarn and set to latest version
```npm install -g yarn``` # https://yarnpkg.com/getting-started/install
```yarn set version latest```

# Part 2: Connection to git

## Install git
```brew install git```

## Github
For getting set up with github, You may need to do the following:
- Generate a new key:  
  ```ssh-keygen -t rsa -b 4096 -C "your_email@example.com"```

- Copy the new rsa key:  
  ```pbcopy < ~/.ssh/id_rsa.pub```

- Add this key to your GitHub account

Additionally, you can configure your github user:  
```git config --global user.name ‘username’```  
```git config --global user.email ‘your_email@example.com’```

# Part 3: Configuration of zsh

## Instal zsh
```brew install zsh``` # https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH  

## Install oh-my-zsh
```sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"```

### Plugins for zsh that need additional installing
```git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions```
```git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting```

## Set zsh as your default shell
If you don’t get prompted to do this when installing oh-my-zsh, try this:   
```chsh -s /usr/local/bin/zsh```

Additional reading for zsh config, covers themes, colors, fonts, etc:  
https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/

# Part 4: Configuration of Terminal
## Install Warp
Install manually from # https://app.warp.dev/
Select and install font (I use Inconsolata Nerd Font) # https://starship.rs/
Install starship from # https://starship.rs/

### Not a neccessary if you have Warp
## Install iTerm2
```brew install iterm2 --cask``` # https://www.iterm2.com/

## Fonts for iterm2(fix[?])
### I use Inconsolata for PowerShell
```create folder```
```cd folder```
```git clone https://github.com/powerline/fonts.git```
```cd fonts```
```./install.sh```

Iterm2 color schemes:   
https://github.com/mbadolato/iTerm2-Color-Schemes

# Part 5: Installing languages

## Installing Ruby
Ruby is probably already installed on your Macbook. You can check to confirm with:  
```ruby -v```

To install:
via asdf:
```asdf plugin-add ruby```
```asdf install ruby 2.3.6```
```asdf global ruby 2.3.6```
OR via rvm:
```rvm install 2.3.6 --with-openssl-dir=/usr/local/Cellar/openssl@1.0/1.0.2t/```
```rvm --default use 2.3.6```
```rvm use ruby-2.3.6```
OR via homebrew:
```brew install ruby```

## Installing Python
Python is probably already installed on your Macbook. You can check to confirm with:  
```python -v```

To install:
```asdf plugin-add python```
```asdf install python 2.3.6```
```asdf global python 2.3.6```
OR
```brew install python``` 

## Installing JAVA SDK
```asdf plugin-add java```
```asdf list-all java``` # list of all of the versions available to install on asdf
```asdf install java adoptopenjdk-8.0.302+8```
```asdf global java adoptopenjdk-8.0.302+8```

## Install PDFtk
Install manually with the link:
https://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/pdftk_server-2.02-mac_osx-10.11-setup.pkg

# Part 6: Installing IDE and DEV apps

## Install a Code Editor
### VSCode
```brew install visual-studio-code --cask``` # https://code.visualstudio.com/ 

**Shortcut For VSCode**  
Open the VSCode app and type in `command + shift P`, then type in `shell command` and click the search result. This will add a shortcut so that you can use `code` to open files and directories from your terminal in VSCode. For example, to open the directory you're currently in:

```code .```

## XCode
```xcode-select --install```  # https://itunes.apple.com/us/app/xcode/id497799835?mt=12
```sudo xcodebuild -license```

### If you get the error "xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '
/Library/Developer/CommandLineTools' is a command line tools instance", run
```sudo xcode-select -s /Applications/Xcode.app/Contents/Developer```
```sudo xcodebuild -license```

## Rubymine
```brew install rubymine```

## Postgres
To install:
```brew install postgres``` 

To start:
```brew services start postgresql```  

## MySQL
To install:
```brew install mysql``` 

To start:
```brew services start mysql``` 

## Rails
```sudo gem install rails```

## Bundler
```gem update --system```
```gem install bundler```

## VIM
- [VIM links]

## Apps to use 
- Google Chrome
- Amphetamine
- Microsoft Outlook
- Microsoft Teams
- Discord
- Telegram
- Docker Desktop
- Cisko AnyConnect Secure Mobility Client (VPN)
- GlobalProtect (VPN)
- VsCode/Xcode/WebStorm/RubyMine/Pycharm/Vim(+Pluggins)
- 

 [VIM links]: <https://coderwall.com/p/1b5zcg/setup-vim-for-ruby-on-rails-osx>

## Useful Links
- Homebrew: https://brew.sh/
- iTerm: https://www.iterm2.com/
- VSCode: https://code.visualstudio.com/
- Oh-my-zsh: https://ohmyz.sh/
- Xcode: https://itunes.apple.com/us/app/xcode/id497799835?mt=12