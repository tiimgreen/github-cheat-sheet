# GitHub Cheat Sheet

All the hidden and not hidden features of Git and GitHub. This cheat sheet was inspired by [Zach Holman](https://github.com/holman)'s [Git and GitHub Secrets](http://www.confreaks.com/videos/1229-aloharuby2012-git-and-github-secrets) talk at Aloha Ruby Conference 2012 ([slides](https://speakerdeck.com/holman/git-and-github-secrets)) and his [More Git and GitHub Secrets](https://vimeo.com/72955426) talk at WDCNZ 2013 ([slides](https://speakerdeck.com/holman/more-git-and-github-secrets)).

# Contents

- [Ignore Whitespace](#ignore-whitespace)
- [Cloning a Repo](#cloning-a-repo)
- [Hub - Git Wrapper](#hub---git-wrapper)
- [Decreasing Contributor Friction](#decreasing-contributor-friction)
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
- [Metadata and Plugin Support for GitHub Pages](#metadata-and-plugin-support-for-github-pages)
- [Diffs](#diffs)
  - [Rendered Prose Diffs](#rendered-prose-diffs)
  - [Diffable Maps](#diffable-maps)
  - [Expanding Context in Diffs](#expanding-context-in-diffs)
- [Emojis](#emojis)
- [Images/GIFs](#imagesgifs)
- [Quick Quoting](#quick-quoting)
- [Styled Git Status](#styled-git-status)
- [Styled Git Log](#styled-git-log)
- [Git Query](#git-query)
- [Merged Branches](#merged-branches)
- [Quick Licensing](#quick-licensing)
- [Task Lists](#task-lists)
- [Relative Links](#relative-links)
- [.gitconfig Recommendations](#gitconfig-recommendations)
    - [Aliases](#aliases)
    - [Auto-correct](#auto-correct)
    - [Color](#color)

## Ignore Whitespace

Adding `?w=1` to any diff URL will remove any changes only in whitespace, enabling you to see only that code that has changed.

[*Read more about GitHub secrets.*](https://github.com/blog/967-github-secrets)

## Cloning a Repo

When cloning a repo the `.git` can be left off the end.

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

[*Read more about the Git `clone` command.*](http://git-scm.com/docs/git-clone)

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

[*Check out some more cool commands Hub has to offer.*](https://github.com/github/hub#commands)

## Decreasing Contributor Friction
If you want people to use and contribute to your project, you need to start by answering their most basic questions. What does the project do? How do I use it? How am I allowed to use it? How do I contribute? How do I get up and running in development? How do I make sure my new features didn't break old functionality?

[Friction](https://github.com/rafalchmiel/friction) is a command line script that will check your project for common answers to these questions. This is some example output:

[![Friction output](http://i.imgur.com/4EgpWo4.png)](https://github.com/rafalchmiel/friction)

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

[*Read more about Git branching.*](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)

## git.io

[git.io](http://git.io) is a simple URL shortener for GitHub.

[http://git.io/wO0xUg](http://git.io/wO0xUg)

[*Read more about Git.io.*](https://github.com/blog/985-git-io-github-url-shortener)

## Gists

[Gists](https://gist.github.com/) are an easy way to work with small bits of code without creating a fully fledged repo.

Although, Gists can be treated as a full repo so they can be cloned like any other:
```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/dULZXXo.png)

[*Read more about creating gists.*](https://help.github.com/articles/creating-gists)

## Keyboard Shortcuts

When on a repo page keyboard shortcuts allow you to navigate easily.

Pressing `t` will bring up a file explorer.

Pressing `w` will bring up the branch selector.

Pressing `s` will select the search bar.

Pressing `l` will edit labels on existing issues.

Pressing `y` __when looking at a file__ (e.g. `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`) will change your URL to one which, in effect, freezes the page you are looking at. If this code changes, you will still be able to see what you saw at that current time.

To see all of the shortcuts for the current page press `?`.

[*Read more about using the Command Bar.*](https://help.github.com/articles/using-the-command-bar)

## Closing Issues with Commits

If a particular commit fixes an issue, any of the keywords `fix/fixes/fixed` or `close/closes/closed`, followed by the issue number, will close the issue once it is committed to the master branch.

```bash
$ git commit -m "Fix cock up, fixes #12"
```

This closes the issue and references the closing commit.

![Closing Repo](http://i.imgur.com/URXFprQ.png)

[*Read more about closing issues via commit messages.*](https://help.github.com/articles/closing-issues-via-commit-messages)

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

[*Read more about checking out pull requests locally.*](https://help.github.com/articles/checking-out-pull-requests-locally)

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

[*Read more about GitHub Flavored Markdown.*](https://help.github.com/articles/github-flavored-markdown)

## Commit History by Author

To view all commits on a repo by author add `?author=username` to the URL.

```
https://github.com/rails/rails/commits/master?author=dhh
```

[*Read more about the differences between commits views.*](https://help.github.com/articles/differences-between-commit-views)

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

[*Read more about comparing commits across time.*](https://help.github.com/articles/comparing-commits-across-time)

### Compare branches across forked repositories

To use GitHub to compare branches across forked repositories, change the URL to look like this:

```
https://github.com/user/repo/compare/{foreign-user}:{branch}...{own-branch}
```

eg.:
```
https://github.com/rails/rails/compare/byroot:idempotent-counter-caches...master
```

## Line Highlighting in Repos

Either adding `#L52` to the end of a code file URL or simply clicking the line number will highlight that line number.

It also works with ranges, e.g. `#L53-L60`, to select ranges, hold `shift` and click two lines:

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

## Metadata and Plugin Support for GitHub Pages
Within Jekyll pages and posts, repository information is available within the `site.github` namespace, and can be displayed, for example, using `{{ site.github.project_title }}`.

The Jemoji and jekyll-mentions plugins enable [emoji](#emojis) and [@mentions](https://github.com/blog/821) in your Jekyll posts and pages to work just like you'd expect when interacting with a repository on GitHub.com.

[*Read more about repository metadata and plugin support for GitHub Pages.*](Repository metadata and plugin support for GitHub Pages)

## Diffs
### Rendered Prose Diffs
Commits and pull requests including prose files feature *source* and *rendered* views. Click the "rendered" button to see the changes as they'll appear in the rendered document. Rendered prose view is handy when you're adding, removing, and editing text:

![Rendered Prose Diffs](https://f.cloud.github.com/assets/17715/2003056/3997edb4-862b-11e3-90be-5e9586edecd7.png)

[*Read more about rendered prose diffs.*](https://github.com/blog/1784-rendered-prose-diffs)

### Diffable Maps
Any time you view a commit or pull request on GitHub that includes geodata, GitHub will render a visual representation of what was changed.

[![Diffable Maps](https://f.cloud.github.com/assets/282759/2090660/63f2e45a-8e97-11e3-9d8b-d4c8078b004e.gif)](https://github.com/benbalter/congressional-districts/commit/2233c76ca5bb059582d796f053775d8859198ec5)

[*Read more about diffable maps.*](https://github.com/blog/1772-diffable-more-customizable-maps)

### Expanding Context in Diffs
Using the *unfold* button in the gutter of a diff, you can reveal additional lines of context with a click. You can keep clicking *unfold* until you've revealed the whole file, and the feature is available anywhere GitHub renders diffs.

![Expanding Context in Diffs](https://f.cloud.github.com/assets/22635/1610539/863c1f64-5584-11e3-82bf-151b406a272f.gif)

[*Read more about expanding context in diffs.*](https://github.com/blog/1705-expanding-context-in-diffs)

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

![Cat and Rabbit](http://i.imgur.com/PoBmL0W.gif)

All images are cached on GitHub, so if your host goes down, the image will remain available.

## Quick Quoting

When on a comment thread and you want to quote something someone previously said, highlight the text and press `r`, this will copy it into your text box in the block-quote format.

![Quick Quote](https://f.cloud.github.com/assets/296432/124483/b0fa6204-6ef0-11e2-83c3-256c37fa7abc.gif)

[*Read more about quick quoting.*](https://github.com/blog/1399-quick-quotes)

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

[*Read more about the Git `status` command.*](http://git-scm.com/docs/git-status)

## Styled Git Log

```bash
$ git log --all --graph --decorate --oneline --abbrev-commit
```

![git log --all --graph --decorate --oneline --abbrev-commit](http://i.imgur.com/RUPycwI.png)

NOTE: This can be added into an Alias (shorter command) using the instructions [here](https://github.com/tiimgreen/github-cheat-sheet#aliases)

[*Read more about the Git `log` command.*](http://git-scm.com/docs/git-log)

## Git Query

A git query allows you to search all your previous commit messages and finds the most recent one matching the query.

```bash
$ git show :/query
```

Where `query` is the term you want to search, this then finds the last one and gives details on the lines that were changed.

```bash
$ git show :/typo
```
![git show :/query](http://i.imgur.com/icaGiNt.png)

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

[*Read more about the Git `branch` command.*](http://git-scm.com/docs/git-branch)

## Quick Licensing

When creating a repo GitHub gives you the options of adding in a pre-made license:

![Licese](http://i.imgur.com/Chqj4Fg.png)

You can also add them to existing repos by creating a new file through the web interface. When the name `LICENSE` is typed in you will get an option to use a template:

![License](http://i.imgur.com/fTjQict.png)

Also works for `.gitignore`.

[*Read more about open source licensing.*](https://help.github.com/articles/open-source-licensing)

## Task Lists

In Issues and Pull requests check boxes can be added with the following syntax (notice the space):
```
- [ ] Be awesome
- [ ] Do stuff
- [ ] Sleep
```

![Task List](http://i.imgur.com/k2qZi56.png)

When they are clicked, they will be updated in the pure Markdown:

```
- [x] Be awesome
- [x] Do stuff
- [ ] Sleep
```

[*Read more about task lists.*](https://github.com/blog/1375%0A-task-lists-in-gfm-issues-pulls-comments)

## Relative Links

Relative links are recommended in your Markdown files when linking to internal content.

```markdown
[Link to a header](#awesome-section)

[Link to a file](docs/readme)
```

Absolute links have to be updated whenever the URL changes (e.g. repo renamed, username changed, project forked).  
Using relative links makes your documentation easily stand on its own.

[*Read more about relative links.*](https://help.github.com/articles/relative-links-in-readmes)

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
	# Show verbose output about tags, branches or remotes
	tags = tag -l
	branches = branch -a
	remotes = remote -v
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
| `git tags` | `git tag -l` | `git config --global alias.tags 'tag -l'` |
| `git branches` | `git branch -a` | `git config --global alias.branches 'branch -a'` |
| `git remotes` | `git remote -v` | `git config --global alias.remotes 'remote -v'` |

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

[*Read more about the Git `config` command.*](http://git-scm.com/docs/git-config)

# Sharing

Share on [Twitter](https://twitter.com/intent/tweet?source=webclient&text=http%3A%2F%2Fgithub.com%2Ftiimgreen%2Fgithub-cheat-sheet%20-%20GitHub%20Cheat%20Sheet)
