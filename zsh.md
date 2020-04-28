# oh-my-zsh 主题

1. 安装字体

   nerd-fonts https://github.com/ryanoasis/nerd-fonts

   https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/Meslo/L-DZ/Regular/complete/Meslo%20LG%20L%20DZ%20Regular%20Nerd%20Font%20Complete%20Mono%20Windows%20Compatible.ttf

2. 安装zplug 插件管理器和依赖项

   https://github.com/zplug/zplug

   ```bash
   curl -sL --proto-redir -all,https https://raw.githubusercontent.com/zplug/installer/master/installer.zsh | zsh
   
   sudo apt install gawk
   ```

3. 覆盖 .zshrc 文件内容

   ```bash
   # Path to your oh-my-zsh installation.
   export ZSH=$HOME/.oh-my-zsh
   
   # Set name of the theme to load.
   # Look in ~/.oh-my-zsh/themes/
   # Optionally, if you set this to "random", it'll load a random theme each
   # time that oh-my-zsh is loaded.
   ZSH_THEME=powerlevel10k/powerlevel10k
   
   POWERLEVEL9K_MODE='nerdfont-complete'
   #POWERLEVEL9K_SHORTEN_DIR_LENGTH=1
   #POWERLEVEL9K_SHORTEN_DELIMITER=""
   #POWERLEVEL9K_SHORTEN_STRATEGY="truncate_from_right"
   POWERLEVEL9K_PROMPT_ON_NEWLINE=true
   POWERLEVEL9K_LEFT_SEGMENT_SEPARATOR=''
   POWERLEVEL9K_RIGHT_SEGMENT_SEPARATOR=''
   POWERLEVEL9K_LEFT_SUBSEGMENT_SEPARATOR=''
   POWERLEVEL9K_RIGHT_SUBSEGMENT_SEPARATOR=''
   POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX="%F{blue}\u256D\u2500%F{white}"
   POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="%F{blue}\u2570\uf460%F{white} "
   POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(root_indicator dir dir_writable_joined)
   POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(command_execution_time
                                       vcs background_jobs_joined time_joined)
   POWERLEVEL9K_VCS_MODIFIED_BACKGROUND="clear"
   POWERLEVEL9K_VCS_UNTRACKED_BACKGROUND="clear"
   POWERLEVEL9K_VCS_MODIFIED_FOREGROUND="yellow"
   POWERLEVEL9K_VCS_UNTRACKED_FOREGROUND="yellow"
   POWERLEVEL9K_DIR_HOME_BACKGROUND="clear"
   POWERLEVEL9K_DIR_HOME_FOREGROUND="blue"
   POWERLEVEL9K_DIR_HOME_SUBFOLDER_BACKGROUND="clear"
   POWERLEVEL9K_DIR_HOME_SUBFOLDER_FOREGROUND="blue"
   POWERLEVEL9K_DIR_WRITABLE_FORBIDDEN_BACKGROUND="clear"
   POWERLEVEL9K_DIR_WRITABLE_FORBIDDEN_FOREGROUND="red"
   POWERLEVEL9K_DIR_DEFAULT_BACKGROUND="clear"
   POWERLEVEL9K_DIR_DEFAULT_FOREGROUND="white"
   POWERLEVEL9K_ROOT_INDICATOR_BACKGROUND="red"
   POWERLEVEL9K_ROOT_INDICATOR_FOREGROUND="white"
   POWERLEVEL9K_STATUS_OK_BACKGROUND="clear"
   POWERLEVEL9K_STATUS_OK_FOREGROUND="green"
   POWERLEVEL9K_STATUS_ERROR_BACKGROUND="clear"
   POWERLEVEL9K_STATUS_ERROR_FOREGROUND="red"
   POWERLEVEL9K_TIME_BACKGROUND="clear"
   POWERLEVEL9K_TIME_FOREGROUND="cyan"
   POWERLEVEL9K_COMMAND_EXECUTION_TIME_BACKGROUND='clear'
   POWERLEVEL9K_COMMAND_EXECUTION_TIME_FOREGROUND='magenta'
   POWERLEVEL9K_BACKGROUND_JOBS_BACKGROUND='clear'
   POWERLEVEL9K_BACKGROUND_JOBS_FOREGROUND='green'
   
   
   # Example aliases
   # alias zshconfig="mate ~/.zshrc"
   # alias ohmyzsh="mate ~/.oh-my-zsh"
   
   # Uncomment the following line to use case-sensitive completion.
   # CASE_SENSITIVE="true"
   
   # Uncomment the following line to disable bi-weekly auto-update checks.
   # DISABLE_AUTO_UPDATE="true"
   
   # Uncomment the following line to change how often to auto-update (in days).
   # export UPDATE_ZSH_DAYS=13
   
   # Uncomment the following line to disable colors in ls.
   # DISABLE_LS_COLORS="true"
   
   # Uncomment the following line to disable auto-setting terminal title.
   # DISABLE_AUTO_TITLE="true"
   
   # Uncomment the following line to disable command auto-correction.
   # DISABLE_CORRECTION="true"
   
   # Uncomment the following line to display red dots whilst waiting for completion.
   # COMPLETION_WAITING_DOTS="true"
   
   # Uncomment the following line if you want to disable marking untracked files
   # under VCS as dirty. This makes repository status check for large repositories
   # much, much faster.
   # DISABLE_UNTRACKED_FILES_DIRTY="true"
   
   # Uncomment the following line if you want to change the command execution time
   # stamp shown in the history command output.
   # The optional three formats: "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
   # HIST_STAMPS="mm/dd/yyyy"
   
   # Would you like to use another custom folder than $ZSH/custom?
   # ZSH_CUSTOM=/path/to/new-custom-folder
   
   # Which plugins would you like to load? (plugins can be found in ~/.oh-my-zsh/plugins/*)
   # Custom plugins may be added to ~/.oh-my-zsh/custom/plugins/
   # Example format: plugins=(rails git textmate ruby lighthouse)
   #plugins=(git autojump zsh-autosuggestions vi-mode)
   
   source $ZSH/oh-my-zsh.sh
   
   # User configuration
   
   export PATH=$HOME/bin:/usr/local/bin:$PATH
   # export MANPATH="/usr/local/man:$MANPATH"
   
   # You may need to manually set your language environment
   #export LANG=en_US.UTF-8
   
   # Preferred editor for local and remote sessions
   # if [[ -n $SSH_CONNECTION ]]; then
   #   export EDITOR='vim'
   # else
   #   export EDITOR='mvim'
   # fi
   
   # Compilation flags
   # export ARCHFLAGS="-arch x86_64"
   
   # ssh
   # export SSH_KEY_PATH="~/.ssh/dsa_id"
   
   # open vscode from terminal
   function code {
       if [[ $# = 0 ]]
       then
           open -a "Visual Studio Code"
       else
           local argPath="$1"
           [[ $1 = /* ]] && argPath="$1" || argPath="$PWD/${1#./}"
           open -a "Visual Studio Code" "$argPath"
       fi
   }
   
   # fzf config, must brew install fzf
   [ -f ~/.fzf.zsh ] && source ~/.fzf.zsh
   
   # the fuck config, must brew install thefuck
   eval $(thefuck --alias)
   
   # autojump config, brew innstall autojump
   [[ -s `brew --prefix`/etc/autojump.sh  ]] && . `brew --prefix`/etc/autojump.sh
   [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
   
   
   # install zplug, plugin manager for zsh, https://github.com/zplug/zplug
   # curl -sL --proto-redir -all,https https://raw.githubusercontent.com/zplug/installer/master/installer.zsh | zsh
   # zplug configruation
   if [[ ! -d "${ZPLUG_HOME}" ]]; then
     if [[ ! -d ~/.zplug ]]; then
       git clone https://github.com/zplug/zplug ~/.zplug
       # If we can't get zplug, it'll be a very sobering shell experience. To at
       # least complete the sourcing of this file, we'll define an always-false
       # returning zplug function.
       if [[ $? != 0 ]]; then
         function zplug() {
           return 1
         }
       fi
     fi
     export ZPLUG_HOME=~/.zplug
   fi
   if [[ -d "${ZPLUG_HOME}" ]]; then
     source "${ZPLUG_HOME}/init.zsh"
   fi
   zplug 'plugins/git', from:oh-my-zsh, if:'which git'
   zplug 'romkatv/powerlevel10k', use:powerlevel10k.zsh-theme
   zplug "plugins/vi-mode", from:oh-my-zsh
   zplug 'zsh-users/zsh-autosuggestions'
   zplug 'zsh-users/zsh-completions', defer:2
   zplug 'zsh-users/zsh-history-substring-search'
   zplug 'zsh-users/zsh-syntax-highlighting', defer:2
   
   if ! zplug check; then
     zplug install
   fi
   
   zplug load
   
   # source your own shrc file if exists
   [ -f ~/.env.sh ] && source ~/.env.sh
   ```

   

