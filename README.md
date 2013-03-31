dotgit
======

Easily manage a mirror of your dotfiles with git.

##Introduction

###Setup:

```
$ mkdir ~/dotfiles
$ git clone https://github.com/dbb/dotgit.git
$ vim dotgit/dotgit
    # set $git_dir to "~/dotgit"
$ ln -s ~/dotgit/dotgit ~/bin/dotgit
```

###First use:

```
$ dotgit up .Xdefaults .vimrc .zsh
```

This is functionally equivalent to:

```
$ cp ~/.Xdefaults ~/dotfiles
$ cp ~/.vimrc ~/dotfiles
$ cp ~/.zshrc ~/dotfiles

$ cd ~/dotfiles
$ git add .Xdefaults .vimrc .zsh
$ git commit -m 'Update: .Xdefaults .vimrc .zsh'
$ git push -u origin master
```

So as you can see, in the long run it can save you quite a bit of typing.
Also, it lets you avoid the sloppiness in making your whole home folder an
active git repository.

*Note: actually, the program will not do any of this in the event that the
diff of the local file and the one in the git repo is null.*

###Updating local files:

```
$ dotgit down .Xdefaults .vimrc .zshrc
```

This is functionally equivalent to:

```
$ cd ~/dotfiles
$ git pull
$ cp .Xdefaults ~
$ cp .vimrc ~
$ cp .zshrc ~
```

##Requirements
* git
* Perl version 5.10 or newer

