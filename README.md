## Git It On

A lot of times we have to look at files on GitHub.  But this intrudes our ideal command-line workflow, having to switch to a browser and navigate to the URL.  Wouldn't it be nice to just be able to open that file from the command line?

*Git It On*, the plugin for zshell, comes in here.

*Note:* This plugin is stable, but still in active development.  I do not yet consider this plugin finished.

* `gitit repo` -- opens the base repository to your current branch
* `gitit repo <folder>` -- opens that folder in your current branch
* `gitit repo .` -- opens current folder in GitHub at your current branch
* `gitit repo ../` -- open one folder up in GitHub.  You can do relative paths.
* `gitit repo <username> <reponame>` -- opens up the specified repository.
* `gitit branch <branch>` -- open the repo for a chosen branch.
* `gitit compare` -- opens the compare file between your branch and master
* `gitit compare <branch>` -- opens the compare file for a chosen branch.
* `gitit commits` -- opens the commits for your current branch
* `gitit commits <branch>` -- opens the commits for a chosen branch.
* `gitit file <filename>` -- opens the github page for the desired file (use either a relative or absolute path).
* `gitit file <filename> <branch>` -- opens the desired file on the chosen branch.
* `gitit history <filename>` -- opens the github history page for the file.
* `gitit history <filename> <branch>` -- opens the history page for the file on the chosen branch.
* `gitit pulls` -- open the list of pull requests for the repo.
* `gitit pulls <filters>` -- open the list of pull requests with filters (e.g., `is:open`, `author:peterhurford`)
* `gitit pulls <number>` -- open the pull request for that number.
* `gitit grep <term>` -- opens the github search page for your term
* `gitit ctrlp` -- opens the github file finder for master branch
* `giti ctrlp <branch>` -- opens the github file finder for your desired branch

## Installation

Assuming you have [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh), you can simply write

```bash
git clone https://github.com/peterhurford/git-it-on.zsh ~/.oh-my-zsh/custom/plugins/git-it-on
echo "plugins+=(git-it-on)" >> ~/.zshrc
```

(Alternatively, you can place the `git-it-on` plugin in the `plugins=(...)` local manually.)

If you're lame and use bash, you can install this directly to your `~/.bash_profile`:

```bash
curl -s https://raw.githubusercontent.com/peterhurford/git-it-on.zsh/master/git-it-on.plugin.zsh >> ~/.bash_profile
```````

## But why even leave vim for the command line?
TODO: Make and link vim companion plugin.


## These commands are too long, I want to be even faster!
You can make commands faster by using aliases.  Put the following in your `.zshrc` (or `.bash_profile`)

```
#Gitit Aliases
alias repo="gitit repo"
alias myrepos="gitit repo peterhurford" #put your name here (usage: `myrepos <reponame>` to open up your repo.)
alias compare="gitit compare"
alias commits="gitit commits"
alias file="gitit file"
alias branch="gitit branch"
alias gistory="gitit history"
alias prs="gitit pulls"
alias myprs="gitit pulls author:peterhurford" #put your name here
alias gitgrep="gitit grep"
alias ctrlp="gitit ctrlp"
```

Feel free to change the aliases to whatever you'd like. You can even make them shorter, but the above is what I use.  Note that these aliases are not included by default.

If you want more git-related aliases for making your git workflow faster, also look at my [Git-aliases.zsh](https://github.com/peterhurford/git-aliases.zsh) plugin.


## Got any more plugins to share?
* [Send.zsh](https://github.com/robertzk/send.zsh), a git command by ro
bertzk that combines `git add .`, `git commit -a -m`, and `git push ori
gin <branch>`.
* [Send.vim](https://github.com/peterhurford/send.vim), a vim plugin by
 me to do the above _without leaving vim_.
