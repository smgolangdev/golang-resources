Go Development Environment Setup Notes
========================================

### Environment Description
 * **vim based IDE**
 * Go plugin for vim for go development 
 * **vim plugins for autocompletion, syntax-highlighting and tagging**. The following plugins should be installed via pathogen.
	  1. [Pathogen]( https://github.com/tpope/vim-pathogen) allows you to manage your 'runtimepath' with ease. In practical terms, pathogen.vim makes it super easy to install plugins and runtime files in their own private directories.
	  2. [Syntastic](https://github.com/scrooloose/syntastic) is a syntax checking plugin for Vim that runs files through external syntax checkers and displays any resulting errors to the user. 
	  3. [vim-go](https://github.com/fatih/vim-go) development plugin for golang.
	  4. [Nerd tree](https://github.com/scrooloose/nerdtree) allows you to explore your filesystem and to open files and directories. It presents the filesystem to you in the form of a tree which you manipulate with the keyboard and/or mouse. It also allows you to perform simple filesystem operations.
	  5. [Tagbar](https://github.com/majutsushi/tagbar) is a Vim plugin that provides an easy way to browse the tags of the current file and get an overview of its structure. It does this by creating a sidebar that displays the ctags-generated tags of the current file, ordered by their scope.
 * **Golang version manager** - [gvm](https://github.com/moovweb/gvm) provides an interface to manage Go versions..

----------
### Prerequisites

  * Install vim-gtk 7.4.x 
```shell
      sudo apt-get install -y vim-gtk curl
      sudo apt-get install -y cmake build-essential python-dev exuberant-ctags

```
 1. Install golang

  Install golang via relevant package manager or using gvm (go version manager)
```shell
    sudo apt-get install -y python-software-properties
    sudo add-apt-repository ppa:duh/golang
    sudo apt-get update
    sudo apt-get install golang

    go version       
    export GOROOT=/usr/lib/go
    export GOBIN=/usr/bin/go
```
Install gvm and then manage golang versions and installs. One can work with multiple golang versions if via gvm.
Pre-requisites for gvm - install mercurial and curl
```shell
    sudo apt-get install -y curl mercurial
```
Install gvm and golang version 1.3.3.
```shell
#run the following command to install gvm

bash < <(curl  -s -S -L    https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)

#open a new terminal and type in the following commands
gvm install go1.1.3 
gvm use go1.1.3 default

#Run the following command to check if the correct version of go was installed.
gvm list 
gvm help # will list all other options
```
2. Vim plugin installs and configuration for golang development
	1. Install pathogen
	2. Install plugins listed above
	3. 	Install [badwolf](http://www.vim.org/scripts/script.php?script_id=3929) color scheme.
	3. Modify .vimrc file
	
	```shell
	# Run the following commands in order to create the following directories under your home directory.
	mkdir -p  ~/.vim/autoload ~/.vim/bundle ~/.vim/colors
	curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
   # Clone the following plugin repositories under ~/.vim/bundle directory
   git clone https://github.com/fatih/vim-go.git
   git clone https://github.com/Valloric/YouCompleteMe.git

   #Once YouCompleteMe respository is cloned, cd  to the YouCompleteMe directory and run the following commands.
   git submodule update --init --recursive
   ./install.sh  #This should build and install YouCompleteMe 
   # Now install the remaining vim bundles
   git clone https://github.com/scrooloose/syntastic.git
   git clone https://github.com/scrooloose/nerdtree.git
   git clone git://github.com/majutsushi/tagbar
  
    ```
Finally modify your **.vimrc** file and add the following lines
```
execute pathogen#infect()
set modeline
set number
syntax on
set omnifunc=syntaxcomplete#Complete
filetype plugin indent on
colorscheme badwolf " my awesome dark color schemes
set number " set line numbers on
set showcmd " show commands in the bottom bar
set cursorline " highlight current line
set wildmenu " visual autocomplete for command
set lazyredraw " only redraw when we need to
set showmatch " highlight matching [{()}]
set incsearch " search as charecters are entered.
set hlsearch " highlight matches
set foldenable " enable folding
set foldlevelstart=10 " open most folds by default
set mouse=a
set autoindent
set ts=4 sts=4 sw=4 expandtab
filetype plugin indent on " required!
filetype plugin on
" Gundo is a plugin to make browsing this ridiculousley powerful undo tree less
" painful.
nnoremap <F5> :GundoToggle<CR>
nmap <F8> :TagbarToggle<CR>

au Filetype go nnoremap <leader>v :vsp <CR>:exe "GoDef" <CR>
au Filetype go nnoremap <leader>s :sp <CR>:exe "GoDef"<CR>

```
Finally, you vim IDE should look like this:
![enter image description here](http://www.metal3d.org/statics/go-vim.png)

### References

 1. [Gopher Academy Blog](http://blog.gopheracademy.com/vimgo-development-environment)
 2. [Setting Up a Docker Environment for Golang Development](http://www.medding.me/blog/2014/09/06/setting-up-a-docker-environment-for-golang-development-part-1/)
 3. [My go development environment](http://www.rounds.com/blog/development-environment/)
 4. Used [SlackEdit](https://stackedit.io/editor#), the online Markdown editor.
 5. [A good vimrc file](http://dougblack.io/words/a-good-vimrc.html) 
 

  


----------


----------


----------


