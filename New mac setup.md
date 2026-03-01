Things that needs to be done for a new Mac. Last update: [[2025-07-10]]

## Mac settings
- use Migration Assistant if available
- enable iCloud Drive sync
- enable Desktop and Documents sync
- Keyboard settings
	- go to Shortcuts and check "Use keyboard navigation to move focus between controls"
	- go to Input sources and check "Show input menu in menubar"
- Dock and Menu Bar settings
	- set position to left
	- reduce size and enable magnification
	- show in menu bar: wifi, bluetooth, battery (with show percentage), sound
	- clock show date set to never
- enable Night Shift
- set Hot Corner
	- top right: mission control
	- bottom right: desktop
- Disable click on wallpaper to reveal desktop
	- Desktop & Dock -> Click wallpaper to reveal desktop -> Only in Stage Manager
- install [DejaVu Sans Mono](https://dejavu-fonts.github.io) (also consider the [nerd font patched version](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/DejaVuSansMono)) font and [Meslo nerd font patched](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/Meslo) 
- Setup 10 virtual desktops, assign keys cmd+shift+1..0 for desktop 1 to 10
- 1Password and Nimble Commander should have "Assign to all desktops"

## App to be installed from CLI
- [homebrew](https://brew.sh)
- xcode cli tool (`xcode-select --install`)
- [oh-my-zsh](https://ohmyz.sh/#install)
- [teamocil](https://github.com/remi/teamocil) (`sudo gem install teamocil`)

## App to be installed through homebrew
- mas (required to install from app store for brew bundle)

## Post-homebrew installation
Run `brew bundle` to install from `Brewfile`

After Brewfile is installed
- chiaki-ng: to play ps5 games and ensure that the quarantine tag is removed (see: [[Allow running unsigned app on mac by removing quarantine flag]])
	- `xattr -r -d com.apple.quarantine /Applications/chiaki-ng.app`
- pipx: to run python app in isolated env
	- pipx ensurepath
	- sudo pipx --global ensurepath
- skhd: use this to launch safari/finder using shortcut keys
	- `skhd --install-service`
	- `skhd --start-service`
- yabai: only to help listing window within space
	- `brew install koekeishiya/formulae/yabai`
	- `yabai --install-service`
	- `yabai --start-service`

## Rust
After `rustup` is installed, run `rustup-init`

## Fish plugin
- [Bass](https://github.com/edc/bass) to run bash script on fish properly

## Zsh plugin
- [powerlevel10k](https://github.com/romkatv/powerlevel10k)
	- `git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) - to simulate fish shell highlighter. 
	- `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) - to simulate fish shell autosuggestions
	- `git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`

## dotfiles
Use `chezmoi` to restore the dotfiles and apply it
- `chezmoi init --apply --verbose git@github.com:ronaldsuwandi/dotfiles.git`

## App to be installed from App Store (already handled by Brewfile)
- AutoMounter
- Day One
- JSON Peep for Safari
- Micro Snitch
- MindNode
- MoneyWiz
- Overlap by Moleskin Studio
- Simple Comic
- WhatsApp Desktop

## App to be downloaded manually
- aText Legacy - new version is too bloated

## Python
- poetry (for dependency management, require pipx to be installed)
	- `pipx install poetry`

## Copy settings (if not using Migration Assistant)
- fish
	- copy settings to `.config/fish`
- zsh
	- configure powershell `p10k configure`
	- configure `~/.zshrc` to include the plugins: `plugins=(git zsh-autosuggestions zsh-syntax-highlighting)`
	- add alias and command_not_found_handler from my [gist](https://gist.github.com/ronaldsuwandi/62aeafabadbc7f6ec63c23b05e4e11a9)
- Sublime Text
	- delete `~/Library/Application Support/Sublime Text/Packages/User`
	- create a **symbolic link** (from icloud sync) `ln -s ~/Documents/00\ Management\ \&\ Meta/02\ Settings/Sublime\ Text/User/ ~/Library/Application\ Support/Sublime\ Text/Packages/User`
- Nimble Commander
	- copy settings to `~/Library/Application Support/Nimble Commander`
- tmux
	- copy `~/.tmux.conf` from my [gist](https://gist.github.com/ronaldsuwandi/af3ef5daa65a8b511e07)
- vim
	- copy `~/.vimrc` from my [gist](https://gist.github.com/ronaldsuwandi/5aa9b67a96d90365701b0ed2f593979b)
- git
	- copy `~/.gitconfig` from my [gist](https://gist.github.com/ronaldsuwandi/9966293)
	- copy `~/.gitignore_global` from my [gist](https://gist.github.com/ronaldsuwandi/1cdcad4101a72fab8dd75b9e1ddfed34)
- iTerm2
	- quit iTerm2 if it's running
	- delete original preference if exists `~/Library/Preferences/com.googlecode.iterm2.plist`
	- create a **hard link** to the settings (from icloud sync) `ln ~/Documents/00\ Management\ \&\ Meta/02\ Settings/iTerm2/com.googlecode.iterm2.plist ~/Library/Preferences/com.googlecode.iterm2.plist`
	- Load the newly copied plist file `defaults read com.googlecode.iterm2.plist`
	- Run iTerm2
- karabiner-elements
	- copy settings to `~/.config/karabiner`
- Obsidian
	- enable Sync
	- sync everything including the community plugins
	- restart Obsidian
	- disable active community plugin list from being synced
- IntelliJ
	- sync setting using account: [reference](https://www.jetbrains.com/help/idea/sharing-your-ide-settings.html#IDE_settings_sync)

## See also
- [[💻 Desktop Workflow System]]
- [[macOS]]

