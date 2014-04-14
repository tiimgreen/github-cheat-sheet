# GitHub Cheat Sheet

All the hidden and not hidden features of Git and GitHub. This cheat sheet was inspired by [Zach Holman](https://github.com/holman)'s [Git and GitHub Secrets](http://www.confreaks.com/videos/1229-aloharuby2012-git-and-github-secrets) talk at Aloha Ruby Conference 2012 ([slides](https://speakerdeck.com/holman/git-and-github-secrets)) and his [More Git and GitHub Secrets](https://vimeo.com/72955426) talk at WDCNZ 2013 ([slides](https://speakerdeck.com/holman/more-git-and-github-secrets)).

# Contents

- [Ignore Whitespace](#ignore-whitespace)
- [Cloning a Repo](#cloning-a-repo)
- [Hub - Git Wrapper](#hub---git-wrapper)
- [Previous Branch](#previous-branch)
- [git.io](#gitio)
- [Gists](#gists)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Closing Issues with Commits](#closing-issues-with-commits)
- [Checking out Pull Requests](#checking-out-pull-requests)
- [Cross-Link Issues](#cross-link-issues)
- [Syntax Highlighting in Markdown Files](#syntax-highlighting-in-markdown-files)
- [Commit History by Author](#commit-history-by-author)
- [Empty Commits](#empty-commits)
- [Comparing Branches](#comparing-branches)
- [Line Highlighting in Repos](#line-highlighting-in-repos)
- [Emojis](#emojis)
- [Images/GIFs](#imagesgifs)
- [Quick Quoting](#quick-quoting)
- [Styled Git Status](#styled-git-status)
- [Styled Git Log](#styled-git-log)
- [Git Query](#git-query)
- [Merged Branches](#merged-branches)
- [Quick Licensing](#quick-licensing)
- [TODO Lists](#todo-lists)
- [.gitconfig Recommendations](#gitconfig-recommendations)
    - [Aliases](#aliases)
    - [Auto-correct](#auto-correct)
    - [Color](#color)

## Ignore Whitespace

Adding `?w=1` to any diff URL will remove any changes only in whitespace, enabling you to see only that code that has changed.

## Cloning a Repo

When cloning a repo the `.git` can be left off the end.

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

## Hub - Git Wrapper

[Hub](https://github.com/github/hub) is a command line git wrapper that gives extra features and commands that make working with GitHub easier.

This allows you to do things like:

```bash
$ hub clone tiimgreen/toc
```

instead of:

```bash
$ git clone https://github.com/tiimgreen/toc.git
```

## Previous Branch

To move to the previous directory in the command line:

```bash
$ cd -
```

Similarly, to move to the last branch in git:

```bash
$ git checkout -
# Switched to branch 'master'

$ git checkout -
# Switched to branch 'next'

$ git checkout -
# Switched to branch 'master'
```

## git.io

[git.io](http://git.io) is a simple URL shortener for GitHub.

[http://git.io/wO0xUg](http://git.io/wO0xUg)

## Gists

[Gists](https://gist.github.com/) are an easy way to work with small bits of code without creating a fully fledged repo.

Although, Gists can be treated as a full repo so they can be cloned like any other:
```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/dULZXXo.png)

## Keyboard Shortcuts

When on a repo page keyboard shortcuts allow you to navigate easily.

Pressing `t` will bring up a file explorer.

Pressing `w` will bring up the branch selector.

Pressing `s` will select the search bar.

Pressing `y` __when looking at a file__ (e.g. `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`) will change your URL to one which, in effect, freezes the page you are looking at. If this code changes, you will still be able to see what you saw at that current time.

To see all of the shortcuts for the current page press `?`.

## Closing Issues with Commits

If a particular commit fixes an issue, any of the keywords `fix/fixes/fixed` or `close/closes/closed`, followed by the issue number, will close the issue.

```bash
$ git commit -m "Fix cock up, fixes #12"
```

This closes the issue and references the closing commit.

![Closing Repo](http://i.imgur.com/URXFprQ.png)

## Checking out Pull Requests

If you want to check out pull request locally, you can fetch it using that command:

```bash
$ git fetch origin '+refs/pull/*/head:refs/pull/*'
```

then, checkout Pull Request (i.e. 42) using

```bash
$ git checkout refs/pull/42
```

Alternatively, you can fetch them as remote branches:

```bash
$ git fetch origin '+refs/pull/*/head:refs/remotes/origin/pr/*'
```

and checkout as:

```bash
$ git checkout origin/pr/42
```

and even fetch them automatically, if you add corresponding lines in your .git/config:


```
[remote "origin"]
    fetch = +refs/heads/*:refs/remotes/origin/*
    url = git@github.com:tiimgreen/github-cheat-sheet.git
```

```
[remote "origin"]
    fetch = +refs/heads/*:refs/remotes/origin/*
    url = git@github.com:tiimgreen/github-cheat-sheet.git
    fetch = +refs/pull/*/head:refs/remotes/origin/pr/*
```

## Cross-link Issues

If you want to link to another issue in the same repo, simple type hash `#` then the issue number, it will be auto-linked.

To link to an issue in another repo, `user_name/repo_name#ISSUE_NUMBER` e.g. `tiimgreen/toc#12`.

## Syntax Highlighting in Markdown Files

For example, to syntax highlight Ruby code in your Markdown files write:

    ```ruby
    require 'tabbit'
    table = Tabbit.new('Name', 'Email')
    table.add_row('Tim Green', 'tiimgreen@gmail.com')
    puts table.to_s
    ```

This will produce:

```ruby
require 'tabbit'
table = Tabbit.new('Name', 'Email')
table.add_row('Tim Green', 'tiimgreen@gmail.com')
puts table.to_s
```

GitHub uses [Linguist](https://github.com/github/linguist) to perform language detection and syntax highlighting. You can find out which keywords are valid by perusing the [languages YAML file](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml).

## Commit History by Author

To view all commits on a repo by author add `?author=username` to the URL.

```
https://github.com/rails/rails/commits/master?author=dhh
```

## Empty Commits

Commits can be pushed with no code changes by adding `--allow-empty`

```bash
$ git commit -m "Big-ass commit" --allow-empty
```

![Trololol](http://img1.wikia.nocookie.net/__cb20130905205853/flylikeabird3/images/0/0c/Mexican_troll_face_by_mariodude12312-d5mtl9z.png)

## Comparing Branches

To use GitHub to compare branches, change the URL to look like this:

```
https://github.com/user/repo/compare/{range}
```

Where `{range} = master...4-1-stable`

e.g.:
```
https://github.com/rails/rails/compare/master...4-1-stable
```

`{range}` can be changed to things like:
```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```
which allows you to see the difference on the master branch up a set time ago or a specified date.

## Line Highlighting in Repos

Either adding `#L52` to the end of a code file URL or simply clicking the line number will highlight that line number.

It also works with ranges, e.g. `#L53-L60`, to select ranges, hold `shift` and click two lines:

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

## Emojis

Emojis can be generated on Pull Requests, Issues, Commit Messages, READMEs, etc. using `:name_of_emoji:`

```
:smile:
:poop:
:shipit:
:+1:
```

:smile:
:poop:
:shipit:
:+1:

The full list of supported Emojis on GitHub can be found [here](http://www.emoji-cheat-sheet.com/) or [here](https://github.com/scotch-io/All-Github-Emoji-Icons).

The top 5 used Ejmojis on GitHub are:

1. :shipit: `:shipit:`
2. :sparkles: `:sparkles:`
3. :-1: `:-1:`
4. :+1: `:+1:`
5. :clap: `:clap:`

## Images/GIFs

Images and GIFs can be added to comments, READMEs etc.:

```
![Alt Text](http://image_url.com/image.jpg)
```

![Chuck Norris](http://gifs.joelglovier.com/chuck-norris/chuck-norris.gif)

All images are cached on GitHub, so if your host goes down, the image will remain available.

## Quick Quoting

When on a comment thread and you want to quote something someone previously said, highlight the text and press `r`, this will copy it into your text box in the block-quote format.

![Quick Quote](http://i.imgur.com/TzpMIOA.png)

## Styled Git Status

```bash
$ git status
```

![git status](http://i.imgur.com/o3PEHAA.png)

Can be changed to:

```bash
$ git status -sb
```

![git status -sb](http://i.imgur.com/xNI1bT0.png)

## Styled Git Log

```bash
$ git log --all --graph --decorate --oneline --abbrev-commit
```

![git log --all --graph --decorate --oneline --abbrev-commit](http://i.imgur.com/RUPycwI.png)

NOTE: This can be added into an Alias (shorter command) using the instructions [here](https://github.com/tiimgreen/github-cheat-sheet#aliases)

## Git Query

A git query allows you to search all your previous commit messages and finds the most recent one matching the query.

```bash
$ git show :/query
```

Where `query` is the term you want to search, this then finds the last one and gives details on the lines that were changed.

```bash
$ git show :/typo
```
![git show :/query](http://i.imgur.com/SA0oZbE.png)

NOTE: Press `q` to quit.

## Merged Branches

```bash
$ git branch --merged
```

Will give you a list of all branches that have been merged into your current branch.

Conversely:

```bash
$ git branch --no-merged
```

Will give you a list of branches that have not been merged into your current branch.

## Quick Licensing

When creating a repo GitHub gives you the options of adding in a pre-made license:

![Licese](http://i.imgur.com/Chqj4Fg.png)

You can also add them to existing repos by creating a new file through the web interface. When the name `LICENSE` is typed in you will get an option to use a template:

![License](http://i.imgur.com/fTjQict.png)

Also works for `.gitignore`.

## TODO Lists

In Issues and Pull requests check boxes can be added with the following syntax (notice the space):
```
- [ ] Be awesome
- [ ] Do stuff
- [ ] Sleep
```

![TODO List](http://i.imgur.com/k2qZi56.png)

When they are clicked, they will be updated in the pure Markdown:

```
- [x] Be awesome
- [x] Do stuff
- [ ] Sleep
```

## .gitconfig Recommendations

Your `.gitconfig` is the file that contains all your preferences.

### Aliases

Aliases are helpers that let you define your own git calls. For example you could set `git a` to run `git add --all`.

To add an alias, either navigate to `~/.gitconfig` and fill it out in the following format:

```
[alias]
	co = checkout
	cm = commit
	p = push
```

or type in the command line:

```bash
$ git config alias.new_alias git_function
```
e.g.
```bash
$ git config alias.cm commit
```

NOTE: for an alias with multiple functions use quotes:
```bash
$ git config alias.ac 'add -A . && commit'
```

Some recommendations include:

| Alias | Current Command | What to Type |
| --- | --- | --- |
| `git cm` | `git commit` | `git config --global alias.cm commit` |
| `git co` | `git checkout` | `git config --global alias.co checkout` |
| `git ac` | `git add . -A` `git commit` | `git config --global alias.ac '!git add -A && git commit'` |
| `git st` | `git status -sb` | `git config --global alias.st 'status -sb'` |

### Auto-correct

Currently if you type `git comit` you will get this result:
```bash
$ git comit -m "Message"
# git: 'comit' is not a git command. See 'git --help'.

# Did you mean this?
# 	commit
```

To call `commit` when `comit` is typed, just enable autocorrect:

```bash
$ git config --global help.autocorrect 1
```

So now you will get this result:

```bash
$ git comit -m "Message"
# WARNING: You called a Git command named 'comit', which does not exist.
# Continuing under the assumption that you meant 'commit'
# in 0.1 seconds automatically...
```

### Color

To add more colour to your git command line:

```bash
$ git config --global color.ui 1
```

# Sharing

Share on [Twitter](https://twitter.com/intent/tweet?source=webclient&text=http%3A%2F%2Fgithub.com%2Ftiimgreen%2Fgithub-cheat-sheet%20-%20GitHub%20Cheat%20Sheet)
