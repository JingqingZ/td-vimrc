Thomas Ding's Vim Configuration
=========================

![snapshot](snapshots/nerdtree-ctrlp.png)

**Handy and Customizable!**

Utilize **NERDTree**, **Fugitive**, **Ctrl-P**, and many excellent plugins now.

Installation
==============

The Automatic Way
------------------

In OS X and Linux where `curl` is installed, td-vimrc can be installed with one
command in the terminal:

1. **Clone the vimrc into your home directory**:

    ```shell
    $ curl https://raw.githubusercontent.com/thomasding/td-vimrc/master/install.sh | sh -
    ```

    It will clone td-vimrc into ~/.td-vimrc, clone Vundle (the package manager that
    this vimrc uses, which need cloning manually) into ~/.vim/bundle/Vundle.vim, and
    create local customizable vimrc files `~/.vimrc.before.local`, `~/.vimrc.after.local`
    and `~/.vimrc.plugin.local`, which are well self-documented.

2. **Enable extra features (optional)**:

    Edit `~/.vimrc.before.local`and enable the features that you need. The extra
    features are mostly related to specific languages or terminal utilities. Skip
    this step if the basic feature is enough (see [Features] for what td-vimrc
    utilizes for a basic feature and extra features).

3. **Install all the plugins**:

    Run `:PluginInstall` in VIM or `vim +PluginInstall +qa` in terminal to install
    the plugins that td-vimrc requires for all the enabled features.


The Manual Way
---------------

In Windows or OS X and Linux where `curl` is not available, td-vimrc has to be
installed manually by following these steps:

1. **Clone td-vimrc into your home directory**:

    ```shell
    $ git clone https://github.com/thomasding/td-vimrc.git ~/.td-vimrc
    ```

2. **Link the vimrc to ~/.vimrc**:

    1. In OS X or Linux, run the command in terminal:

        ```shell
        $ ln -s ~/.td-vimrc/vimrc ~/.vimrc
        ```

    2. In Windows, start CMD **as administrator**, change to home directory, and run:

        ```shell
        C:\Users\{Your Home}> mklink .vimrc .td-vimrc\vimrc
        ```

3. **Clone Vundle to your vim plugin directory**:

    ```shell
    $ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
    ```

4. **Create local customizable vimrc files**:

    Create `~/.vimrc.before.local`, `~/.vimrc.after.local` and `~/.vimrc.plugin.local`
    in your home directory. See [Customization] for the descriptions of these files.

5. **Enable extra features (optional)**:

    Set global variable `g:tdvimrc_features` to enable extra features in need.

    ```VimL
    " The following statement enables all the extra features td-vimrc supports.
    " Remove the items to disable unwanted features. Set it to [] to disable
    " all extra features. See [Features] for the descriptions of each extra feature.
    let g:tdvimrc_features = ["golang", "html", "tmux"]
    ```

6. **Install all the plugins**:

    Run `:PluginInstall` in VIM or `$ vim +PluginInstall +qa` in terminal to
    install all the plugins td-vimrc requires for all enabled features.

Supported Plugins
=================

* Vundle.vim: a bundle manager for VIM.
* ctrlp: a convenient tool for fuzzy file searching.
* vim-airline: a powerful and beautiful status line enhancement implemented fully in vim script.
* vim-fugitive: use git in vim.
* vim-gitgutter: show the modifications compared to the last commit in git repo in the gutter.
* vim-surround: an easy-to-use quoting and parenthesizing plugin.
* vim-colorschemes: one colorscheme pack that rule them all.
* nerdtree: a powerful tree-structured directory manager.
* nerdtree-git-plugin: show the status of a file in the git repo in nerdtree.
* undotree: move around the undo tree more conveniently.
* emmet-vim: emmet in vim.
* vim-jinja: jinja2 syntax.
* vim-flavored-markdown: github flavord markdown syntax highlighting.
* vim-javascript: enhanced javascript syntax highlighting.
* vim-jsx: jsx syntax highlighting.
* tmuxline.vim: unify tmux statusline with vim.
* vim-tmux-nagivator: move around vim windows and tmux buffers coherently.
* better-indent-for-php-with-html: better indent for php files.
* php.vim: php syntax highlighting.
* html5.vim: html5 syntax highlighting.
* syntastic: powerful code linting tool for many languages.

Features
===========

* Structured and well-documented vimrc.
* Bind ESC to jj.
* Hide menu, scrollbars and toolbar in GUI.
* Use Monospace as the default font in Linux and Consolas in Windows.
* Map leader key to comma.
* Key bindings to frequent fugitive commands, see below.
* Disable backup and swapfile.
* Show a vertical line in Column 80.
* Do not wrap lines automatically.
* Use Github Flavored Markdown as the default markdown syntax.

Fugitive Key Bindings
======================

    Shortcut    Command     Description
  -------------------------------------------------
    ,gs         :Gstatus    show the status of the git repo
    ,gc         :Gcommit    commit the staged changes
    ,gw         :Gwrite     save the current buffer and stage the file
    ,gd         :Gdiff      diff the current buffer with the last commit
    ,gb         :Gblame     blame the current buffer

Other Key Bindings
=====================

    Shortcut    Command             Description
  ---------------------------------------------------------------
    ,n          :NERDTreeToogle     toggle the nerd tree
    ,u          :UndotreeToggle     toggle the undo tree
    Ctrl-P      :CtrlP              show the Ctrl-P panel
