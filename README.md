## Steps for successful setup of your local machine

# Part 1: Dependencies you will need to work with

## Install homebrew
```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"```

### To avoid bugs run:
 ```brew update && brew doctor```

## Install asdf
```shell
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.1
```
```shell
echo -e '\nautoload -U +X compinit && compinit' >> ~/.zshrc
```
```shell
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.zshrc
```
```shell
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.zshrc
```
```shell
source ~/.zshrc
```

## Install rvm
```shell
curl -sSL https://get.rvm.io | bash -s stable
```
```shell
source ~/.rvm/scripts/rvm
```

## Install Node.js
```shell
asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git
```
[Node.js]
```shell
bash ~/.asdf/plugins/nodejs/bin/import-release-team-keyring
```
```shell
asdf install nodejs 12.16.3
```
```shell
asdf global nodejs 12.16.3
```

## Install yarn and set to latest version
```shell
npm install -g yarn
```
[yarn]

```shell
yarn set version latest
```

# Part 2: Connection to git

## Install git
```shell
brew install git
```

## Github
For getting set up with github, You may need to do the following:
- Generate a new key:  
  ```shell
  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```

- Copy the new rsa key:  
  ```shell
  pbcopy < ~/.ssh/id_rsa.pub
  ```

- Add this key to your GitHub account

Additionally, you can configure your github user:  
```shell
git config --global user.name ‘username’
```  
```shell
git config --global user.email ‘your_email@example.com’
```

# Part 3: Configuration of zsh

## Instal zsh
```shell
brew install zsh
```
[zsh]  

## Install oh-my-zsh
```shell
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### Plugins for zsh that need additional installing
```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
```
```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

## Set zsh as your default shell
If you don’t get prompted to do this when installing oh-my-zsh, try this:   
```shell
chsh -s /usr/local/bin/zsh
```

Additional reading for zsh config, covers themes, colors, fonts, etc:  
https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/

# Part 4: Configuration of Terminal
## Install Warp
Install manually from [warp].

Select and install font  from [nerdfonts]. # I use Inconsolata Nerd Font

Install starship from [starship].


## Install iTerm2
```shell
brew install iterm2 --cask
```
[iterm2]

## Fonts for iterm2(fix[?])
### I use Inconsolata for PowerShell
```shell
create folder
```
```shell
cd folder
```
```shell
git clone https://github.com/powerline/fonts.git
```
```shell
cd fonts
```
```shell
./install.sh
```

Iterm2 color schemes:   
https://github.com/mbadolato/iTerm2-Color-Schemes

# Part 5: Installing languages

## Installing Ruby
Ruby is probably already installed on your Macbook. You can check to confirm with:  
```shell
ruby -v
```

To install:
via asdf:
```shell
asdf plugin-add ruby
```
```shell
asdf install ruby 2.3.6
```
```shell
asdf global ruby 2.3.6
```
OR via rvm:
```shell
rvm install 2.3.6 --with-openssl-dir=/usr/local/Cellar/openssl@1.0/1.0.2t/
```
```shell
rvm --default use 2.3.6
```
```shell
rvm use ruby-2.3.6
```
OR via homebrew:
```shell
brew install ruby
```

## Installing Python
Python is probably already installed on your Macbook. You can check to confirm with:  
```shell
python -v
```

To install:
```shell
asdf plugin-add python
```
```shell
asdf install python 2.3.6
```
```shell
asdf global python 2.3.6
```
OR
```shell
brew install python
``` 

## Installing JAVA SDK
```shell
asdf plugin-add java
```
```shell
asdf list-all java
``` # list of all of the versions available to install on asdf
```shell
asdf install java adoptopenjdk-8.0.302+8
```
```shell
asdf global java adoptopenjdk-8.0.302+8
```

## Install PDFtk
Install manually with the link:
[pdftk]

# Part 6: Installing IDE and DEV apps

## Install a Code Editor
### VSCode
```shell
brew install visual-studio-code --cask
```
[vs code]

**Shortcut For VSCode**  
Open the VSCode app and type in `command + shift P`, then type in `shell command` and click the search result. This will add a shortcut so that you can use `code` to open files and directories from your terminal in VSCode. For example, to open the directory you're currently in:

```shell
code .
```

## XCode
```shell
xcode-select --install
```
[xcode]
```shell
sudo xcodebuild -license
```

### If you get the error "xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '
/Library/Developer/CommandLineTools' is a command line tools instance", run
```shell
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
```
```shell
sudo xcodebuild -license
```

## Rubymine
```shell
brew install rubymine
```

## Postgres
To install:
```shell
brew install postgres
``` 

To start:
```shell
brew services start postgresql
```  

## MySQL
To install:
```shell
brew install mysql
``` 

To start:
```shell
brew services start mysql
``` 

## Rails
```shell
sudo gem install rails
```

## Bundler
```shell
gem update --system
```
```shell
gem install bundler
```

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

 [VIM links]: <https://coderwall.com/p/1b5zcg/setup-vim-for-ruby-on-rails-osx>
 [Node.js]: <https://github.com/asdf-vm/asdf-nodejs>
 [yarn]: <https://yarnpkg.com/getting-started/install>
 [zsh]: <https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH>
 [warp]: <https://app.warp.dev/>
 [nerdfonts]: <https://www.nerdfonts.com/>
 [starship]: <https://starship.rs/>
 [iterm2]: <https://www.iterm2.com/>
 [pdftk]: <https://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/pdftk_server-2.02-mac_osx-10.11-setup.pkg>
 [vs code]: <https://code.visualstudio.com/>
 [xcode]: <https://itunes.apple.com/us/app/xcode/id497799835?mt=12>

## Useful Links
- Homebrew: https://brew.sh/
- iTerm: https://www.iterm2.com/
- VSCode: https://code.visualstudio.com/
- Oh-my-zsh: https://ohmyz.sh/
- Xcode: https://itunes.apple.com/us/app/xcode/id497799835?mt=12
