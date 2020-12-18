# shell.preferences
Files containing the way I like my shell to look and run. 

## Install Oh-my-zsh

```sh
	sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
 ```
## Install Theme 

Adding and customizing your own themes pretty much works the same as with plugins.

Themes are located in a themes folder and must end with .zsh-theme. The basename of the file is the name of the theme.

	```
	$ZSH_CUSTOM
	└── themes
	    └── rocinante.zsh-theme
	```

	Then edit your .zshrc to use that theme.

	```shell
	ZSH_THEME="rocinante"
	```

## Install plugins 

### Enabling Plugins (zsh-autosuggestions & zsh-syntax-highlighting)
 - Download zsh-autosuggestions by
 
 `git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions`
 
 - Download zsh-syntax-highlighting by
 
 `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting`
 
 - Download solarized dir colors
 
 `git clone --recursive git://github.com/joel-porquet/zsh-dircolors-solarized $ZSH_CUSTOM/plugins/zsh-dircolors-solarized`

 - `vim ~/.zshrc` find `plugins=(git)`
 
 - Append `zsh-autosuggestions & zsh-syntax-highlighting` to  `plugins()` like this 
 
 `plugins=(git zsh-autosuggestions zsh-syntax-highlighting zsh-dircolors-solarized)`
 
 - Reopen terminal


### Solarized dir colors Usage

This plugin offers two commands:

* `lssolarized` which lists the available solarized themes. For now there are:
    * `dircolors.ansi-universal` (universal theme for 16- and 256-color terminals)
    * `dircolors.ansi-dark` (optimized version of universal for dark background)
    * `dircolors.ansi-light` (optimized version of universal for light background)
    * `dircolors.256dark` (degraded solarized dark theme) -> My preference

* `setupsolarized` which installs a theme and saves the current configuration to
  the configuration file (`$HOME/.zsh-dircolors.config` by default). Without any
  argument, `setupsolarized` will use the theme `dircolors.ansi-universal`.
  
`setupsolarized` must be run at least once in order to create the configuration file. After doing so, the plugin will automatically load your configuration each time a zsh session is started.

### OSX Support
A required command for this library is `dircolors`. This command is not available on OSX. Instead, `gdircolors`
is provided through Homebrew.

1. Install core-utils.
    ```
    brew install coreutils
    ```
2. Add the following alias to your `.zshrc` anywhere prior to where this plugin is installed.
    ```
    alias dircolors='gdircolors'
    ```
