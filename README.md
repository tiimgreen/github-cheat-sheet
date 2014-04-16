# GitHub Cheat Sheet
A collection of cool hidden and not so hidden features of Git and GitHub. This cheat sheet was inspired by [Zach Holman](https://github.com/holman)'s [Git and GitHub Secrets](http://www.confreaks.com/videos/1229-aloharuby2012-git-and-github-secrets) talk at Aloha Ruby Conference 2012 ([slides](https://speakerdeck.com/holman/git-and-github-secrets)) and his [More Git and GitHub Secrets](https://vimeo.com/72955426) talk at WDCNZ 2013 ([slides](https://speakerdeck.com/holman/more-git-and-github-secrets)).

## Table of Contents
 - [GitHub](#github)
  - [Ignore Whitespace](#ignore-whitespace)
  - [Commit History by Author](#commit-history-by-author)
  - [Cloning a Repository](#cloning-a-repository)
  - [Comparing Branches](#comparing-branches)
  - [Compare Branches across Forked Repositories](#compare-branches-across-forked-repositories)
  - [Gists](#gists)
  - [Git.io](#gitio)
  - [Keyboard Shortcuts](#keyboard-shortcuts)
  - [Line Highlighting in Repositories](#line-highlighting-in-repositories)
  - [Closing Issues via Commit Messages](#closing-issues-via-commit-messages)
  - [Cross-Link Issues](#cross-link-issues)
  - [CI Status on Pull Requests](#ci-status-on-pull-requests)
  - [Syntax Highlighting in Markdown Files](#syntax-highlighting-in-markdown-files)
  - [Emojis](#emojis)
  - [Images/GIFs](#imagesgifs)
    - [Embedding Images in GitHub Wiki](#embedding-images-in-github-wiki)
  - [Quick Quoting](#quick-quoting)
  - [Quick Licensing](#quick-licensing)
  - [Task Lists](#task-lists)
  - [Relative Links](#relative-links)
  - [Metadata and Plugin Support for GitHub Pages](#metadata-and-plugin-support-for-github-pages)
  - [Diffs](#diffs)
    - [Rendered prose Diffs](#rendered-prose-diffs)
    - [Diffable Maps](#diffable-maps)
    - [Expanding Context in Diffs](#expanding-context-in-diffs)
    - [Diff or Patch of Pull Request](#diff-or-patch-of-pull-request)
  - [Hub](#hub)
  - [Decreasing Contributor Friction](#decreasing-contributor-friction)
  - [Contributing Guidelines](#contributing-guidelines)
  - [GitHub Resources](#github-resources)
    - [GitHub Talks](#github-talks)
 - [Git](#git)
  - [Previous Branch](#previous-branch)
  - [Stripspace](#stripspace)
  - [Checking out Pull Requests](#checking-out-pull-requests)
  - [Empty Commits :trollface:](#empty-commits-trollface)
  - [Styled Git Status](#styled-git-status)
  - [Styled Git Log](#styled-git-log)
  - [Git Query](#git-query)
  - [Merged Branches](#merged-branches)
  - [Web Server for Browsing Local Repositories](#web-server-for-browsing-local-repositories)
  - [Git Configurations](#git-configurations)
    - [Aliases](#aliases)
    - [Auto-Correct](#auto-correct)
    - [Color](#color)
  - [Git Resources](#git-resources)
    - [Git Books](#git-books)

## GitHub
### Ignore Whitespace
Adding `?w=1` to any diff URL will remove any changes only in whitespace, enabling you to see only that code that has changed.

![Diff without whitespace](https://camo.githubusercontent.com/797184940defadec00393e6559b835358a863eeb/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f776869746573706163652e706e67)

[*Read more about GitHub secrets.*](https://github.com/blog/967-github-secrets)

### Commit History by Author
To view all commits on a repo by author add `?author=username` to the URL.

```
https://github.com/rails/rails/commits/master?author=dhh
```

![DHH commit history](http://i.imgur.com/mDWwuaY.png)

[*Read more about the differences between commits views.*](https://help.github.com/articles/differences-between-commit-views)

### Cloning a Repository
When cloning a repository the `.git` can be left off the end.

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

[*Read more about the Git `clone` command.*](http://git-scm.com/docs/git-clone)

### Comparing Branches
To use GitHub to compare branches, change the URL to look like this:

```
https://github.com/user/repo/compare/{range}
```

Where `{range} = master...4-1-stable`

For example:

```
https://github.com/rails/rails/compare/master...4-1-stable
```

![Rails branch compare example](http://i.imgur.com/0Z52X5Y.png)

`{range}` can be changed to things like:

```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```

*Dates are in the format `YYYY-DD-MM`*

![Another compare example](http://i.imgur.com/5dtzESz.png)

...which allows you to see the difference on the master branch up a set time ago or a specified date.

[*Read more about comparing commits across time.*](https://help.github.com/articles/comparing-commits-across-time)

### Compare Branches across Forked Repositories
To use GitHub to compare branches across forked repositories, change the URL to look like this:

```
https://github.com/user/repo/compare/{foreign-user}:{branch}...{own-branch}
```

For example:

```
https://github.com/rails/rails/compare/byroot:master...master
```

![Forked branch compare](http://i.imgur.com/Q1W6qcB.png)

### Gists
[Gists](https://gist.github.com/) are an easy way to work with small bits of code without creating a fully fledged repository.

![Gist](http://i.imgur.com/VkKI1LC.png?1)

Add `.pibb` to the end of any Gist URL ([like this](https://gist.github.com/tiimgreen/10545817.pibb)) in order to get the *HTML only* version suitable for embedding in any other site.

Gists can be treated as a full repository so they can be cloned like any other:

```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/dULZXXo.png)

[*Read more about creating gists.*](https://help.github.com/articles/creating-gists)

### Git.io
[Git.io](http://git.io) is a simple URL shortener for GitHub.

![Git.io](http://i.imgur.com/6JUfbcG.png?1)

You can also use it via pure HTTP using Curl:

```bash
$ curl -i http://git.io -F "url=https://github.com/..."
HTTP/1.1 201 Created
Location: http://git.io/abc123

$ curl -i http://git.io/abc123
HTTP/1.1 302 Found
Location: https://github.com/...
```

[*Read more about Git.io.*](https://github.com/blog/985-git-io-github-url-shortener)

### Keyboard Shortcuts
When on a repository page, keyboard shortcuts allow you to navigate easily.

 - Pressing `t` will bring up a file explorer.
 - Pressing `w` will bring up the branch selector.
 - Pressing `s` will select the Command Bar.
 - Pressing `l` will edit labels on existing Issues.
 - Pressing `y` **when looking at a file** (e.g. `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`) will change your URL to one which, in effect, freezes the page you are looking at. If this code changes, you will still be able to see what you saw at that current time.

To see all of the shortcuts for the current page press `?`:

![Keyboard shortcuts](http://i.imgur.com/y5ZfNEm.png)

[*Read more about using the Command Bar.*](https://help.github.com/articles/using-the-command-bar)

### Line Highlighting in Repositories
Either adding `#L52` to the end of a code file URL or simply clicking the line number will highlight that line number.

It also works with ranges, e.g. `#L53-L60`, to select ranges, hold `shift` and click two lines:

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

### Closing Issues via Commit Messages
If a particular commit fixes an issue, any of the keywords `fix/fixes/fixed` or `close/closes/closed`, followed by the issue number, will close the issue once it is committed to the master branch.

```bash
$ git commit -m "Fix cock up, fixes #12"
```

This closes the issue and references the closing commit.

![Closing Repo](http://i.imgur.com/URXFprQ.png)

[*Read more about closing Issues via commit messages.*](https://help.github.com/articles/closing-issues-via-commit-messages)

### Cross-Link Issues
If you want to link to another issue in the same repository, simple type hash `#` then the issue number, it will be auto-linked.

To link to an issue in another repository, `user_name/repo_name#ISSUE_NUMBER` e.g. `tiimgreen/toc#12`.

![Cross-Link Issues](https://camo.githubusercontent.com/447e39ab8d96b553cadc8d31799100190df230a8/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f7265666572656e6365732e706e67)

### CI Status on Pull Requests
If set up correctly, every time you receive a Pull Request, [Travis CI](https://travis-ci.org/) will build that Pull Request just like it would every time you make a new commit. Read more about how to [get started with Travis CI](http://docs.travis-ci.com/user/getting-started/).

[![Travic CI status](https://cloud.githubusercontent.com/assets/1687642/2700187/3a88838c-c410-11e3-9a46-e65e2a0458cd.png)](https://github.com/octokit/octokit.rb/pull/452)

[*Read more about the commit status API.*](https://github.com/blog/1227-commit-status-api)

### Syntax Highlighting in Markdown Files
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

### Emojis
Emojis can added to on Pull Requests, Issues, commit messages, Markdown files, etc. using `:name_of_emoji:`:

```
:smile:
```

Would produce:

:smile:

The full list of supported Emojis on GitHub can be found at [emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com/) or [scotch-io/All-Github-Emoji-Icons](https://github.com/scotch-io/All-Github-Emoji-Icons).

The top 5 used Ejmojis on GitHub are:

1. :shipit: - `:shipit:`
2. :sparkles: - `:sparkles:`
3. :-1: - `:-1:`
4. :+1: - `:+1:`
5. :clap: - `:clap:`

### Images/GIFs
Images and GIFs can be added to comments, READMEs etc.:

```
![Alt Text](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)
```

![Peter don't care](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)

All images are cached on GitHub, so if your host goes down, the image will remain available.

#### Embedding Images in GitHub Wiki
There are multiple ways of embedding images in Wiki pages. There's the standard Markdown syntax (shown above). But there's also a syntax that allows things like specifying the height or width of the image:

```markdown
[[ http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif | height = 100px ]]
```

Which produces:

![Just a screenshot](http://i.imgur.com/J5bMf7S.png)

### Quick Quoting
When on a comment thread and you want to quote something someone previously said, highlight the text and press `r`, this will copy it into your text box in the block-quote format.

![Quick Quote](https://f.cloud.github.com/assets/296432/124483/b0fa6204-6ef0-11e2-83c3-256c37fa7abc.gif)

[*Read more about quick quoting.*](https://github.com/blog/1399-quick-quotes)

### Quick Licensing
When creating a repository GitHub gives you the options of adding in a pre-made license:

![License](http://i.imgur.com/Chqj4Fg.png)

You can also add them to existing repositories by creating a new file through the web interface. When the name `LICENSE` is typed in you will get an option to use a template:

![License](http://i.imgur.com/fTjQict.png)

Also works for `.gitignore`.

[*Read more about open source licensing.*](https://help.github.com/articles/open-source-licensing)

### Task Lists
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

### Relative Links
Relative links are recommended in your Markdown files when linking to internal content.

```markdown
[Link to a header](#awesome-section)
[Link to a file](docs/readme)
```

Absolute links have to be updated whenever the URL changes (e.g. repository renamed, username changed, project forked). Using relative links makes your documentation easily stand on its own.

[*Read more about relative links.*](https://help.github.com/articles/relative-links-in-readmes)

### Metadata and Plugin Support for GitHub Pages
Within Jekyll pages and posts, repository information is available within the `site.github` namespace, and can be displayed, for example, using `{{ site.github.project_title }}`.

The Jemoji and jekyll-mentions plugins enable [emoji](#emojis) and [@mentions](https://github.com/blog/821) in your Jekyll posts and pages to work just like you'd expect when interacting with a repository on GitHub.com.

[*Read more about repository metadata and plugin support for GitHub Pages.*](https://github.com/blog/1797-repository-metadata-and-plugin-support-for-github-pages)

### Diffs
#### Rendered Prose Diffs
Commits and pull requests including rendered documents supported by GitHub (e.g. Markdown) feature *source* and *rendered* views.

![Source / Rendered view](https://github-images.s3.amazonaws.com/help/repository/rendered_prose_diff.png)

Click the "rendered" button to see the changes as they'll appear in the rendered document. Rendered prose view is handy when you're adding, removing, and editing text:

![Rendered Prose Diffs](https://f.cloud.github.com/assets/17715/2003056/3997edb4-862b-11e3-90be-5e9586edecd7.png)

[*Read more about rendered prose diffs.*](https://github.com/blog/1784-rendered-prose-diffs)

#### Diffable Maps
Any time you view a commit or pull request on GitHub that includes geodata, GitHub will render a visual representation of what was changed.

[![Diffable Maps](https://f.cloud.github.com/assets/282759/2090660/63f2e45a-8e97-11e3-9d8b-d4c8078b004e.gif)](https://github.com/benbalter/congressional-districts/commit/2233c76ca5bb059582d796f053775d8859198ec5)

[*Read more about diffable maps.*](https://github.com/blog/1772-diffable-more-customizable-maps)

#### Expanding Context in Diffs
Using the *unfold* button in the gutter of a diff, you can reveal additional lines of context with a click. You can keep clicking *unfold* until you've revealed the whole file, and the feature is available anywhere GitHub renders diffs.

![Expanding Context in Diffs](https://f.cloud.github.com/assets/22635/1610539/863c1f64-5584-11e3-82bf-151b406a272f.gif)

[*Read more about expanding context in diffs.*](https://github.com/blog/1705-expanding-context-in-diffs)

#### Diff or Patch of Pull Request
You can get the diff of a Pull Request by adding a `.diff` or `.patch`
extension to the end of the URL. For example:

```
https://github.com/tiimgreen/github-cheat-sheet/pull/15
https://github.com/tiimgreen/github-cheat-sheet/pull/15.diff
https://github.com/tiimgreen/github-cheat-sheet/pull/15.patch
```

The `.diff` extension would give you this in plain text:

```
diff --git a/README.md b/README.md
index 88fcf69..8614873 100644
--- a/README.md
+++ b/README.md
@@ -28,6 +28,7 @@ All the hidden and not hidden features of Git and GitHub. This cheat sheet was i
 - [Merged Branches](#merged-branches)
 - [Quick Licensing](#quick-licensing)
 - [TODO Lists](#todo-lists)
+- [Relative Links](#relative-links)
 - [.gitconfig Recommendations](#gitconfig-recommendations)
     - [Aliases](#aliases)
     - [Auto-correct](#auto-correct)
@@ -381,6 +382,19 @@ When they are clicked, they will be updated in the pure Markdown:
 - [ ] Sleep

(...)
```

### Hub
[Hub](https://github.com/github/hub) is a command line Git wrapper that gives you extra features and commands that make working with GitHub easier.

This allows you to do things like:

```bash
$ hub clone tiimgreen/toc
```

[*Check out some more cool commands Hub has to offer.*](https://github.com/github/hub#commands)

### Decreasing Contributor Friction
If you want people to use and contribute to your project, you need to start by answering their most basic questions. What does the project do? How do I use it? How am I allowed to use it? How do I contribute? How do I get up and running in development? How do I make sure my new features didn't break old functionality?

[Friction](https://github.com/rafalchmiel/friction) is a command line script that will check your project for common [answers to these questions](https://github.com/rafalchmiel/friction/wiki). This is some example output:

[![Friction output](http://i.imgur.com/4EgpWo4.png)](https://github.com/rafalchmiel/friction)

### Contributing Guidelines
Adding a `CONTRIBUTING` file to the root of your repository will add a link to your file when a contributor creates an Issue or opens a Pull Request.

![Contributing Guidelines](https://camo.githubusercontent.com/71995d6b0e620a9ef1ded00a04498241c69dd1bf/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f736b697463682f6973737565732d32303132303931332d3136323533392e6a7067)

[*Read more about contributing guidelines.*](https://github.com/blog/1184-contributing-guidelines)

### GitHub Resources
| Title | Link |
| ----- | ---- |
| GitHub Explore | https://github.com/explore |
| GitHub Blog | https://github.com/blog |
| GitHub Help | https://help.github.com/ |
| GitHub Training | http://training.github.com/ |
| GitHub Developer | https://developer.github.com/ |

#### GitHub Talks
| Title | Link |
| ----- | ---- |
| How GitHub Uses GitHub to Build GitHub | https://www.youtube.com/watch?v=qyz3jkOBbQY |
| Introduction to Git with Scott Chacon of GitHub | https://www.youtube.com/watch?v=ZDR433b0HJY |
| How GitHub No Longer Works | https://www.youtube.com/watch?v=gXD1ITW7iZI |
| Git and GitHub Secrets | https://www.youtube.com/watch?v=Foz9yvMkvlA |
| More Git and GitHub Secrets | https://www.youtube.com/watch?v=p50xsL-iVgU |

## Git
### Previous Branch
To move to the previous branch in Git:

```bash
$ git checkout -
# Switched to branch 'master'

$ git checkout -
# Switched to branch 'next'

$ git checkout -
# Switched to branch 'master'
```

[*Read more about Git branching.*](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)

### Stripspace

Git Stripspace:

- Strips trailing whitespace
- Collapses newlines
- Adds newline to end of file

A file must be passed when calling the command, e.g.:
```bash
$ git stripspace < README.md
```

[*Read more about the Git `stripspace` command.*](http://git-scm.com/docs/git-stripspace)

### Checking out Pull Requests
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

### Empty Commits :trollface:
Commits can be pushed with no code changes by adding `--allow-empty`:

```bash
$ git commit -m "Big-ass commit" --allow-empty
```

Some use-cases for this (that make sense), include:

 - Annotating the start of a new bulk of work or a new feature.
 - Documenting when you make changes to the project that aren't code related.
 - Communicating with people using your repository.

### Styled Git Status
Running:

```bash
$ git status
```

Produces:

![git status](http://i.imgur.com/o3PEHAA.png)

By adding `-sb`:

```bash
$ git status -sb
```

This is produced:

![git status -sb](http://i.imgur.com/xNI1bT0.png)

[*Read more about the Git `status` command.*](http://git-scm.com/docs/git-status)

### Styled Git Log
Running:

```bash
$ git log --all --graph --decorate --oneline --abbrev-commit
```

Produces:

![git log --all --graph --decorate --oneline --abbrev-commit](http://i.imgur.com/RUPycwI.png)

*This can be aliased using the instructions found [here](https://github.com/tiimgreen/github-cheat-sheet#aliases).*

[*Read more about the Git `log` command.*](http://git-scm.com/docs/git-log)

### Git Query
A Git query allows you to search all your previous commit messages and find the most recent one matching the query.

```bash
$ git show :/query
```

Where `query` is the term you want to search, this then finds the last one and gives details on the lines that were changed.

```bash
$ git show :/typo
```
![git show :/query](http://i.imgur.com/icaGiNt.png)

*Press `q` to quit.*

### Merged Branches
Running:

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

### Web Server for Browsing Local Repositories
Use the Git `instaweb` command to instantly browse your working repository in `gitweb`. This command is a simple script to set up `gitweb` and a web server for browsing the local repository.

```bash
$ git instaweb
```

Opens:

![Git instaweb](http://i.imgur.com/Dxekmqc.png)

[*Read more about the Git `instaweb` command.*](http://git-scm.com/docs/git-instaweb)

### Git Configurations
Your `.gitconfig` file contains all your Git configurations.

#### Aliases
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

...or type in the command-line:

```bash
$ git config alias.new_alias git_function
```

For example:

```bash
$ git config alias.cm commit
```

For an alias with multiple functions use quotes:

```bash
$ git config alias.ac 'add -A . && commit'
```

Some useful aliases include:

| Alias | Command | What to Type |
| --- | --- | --- |
| `git cm` | `git commit` | `git config --global alias.cm commit` |
| `git co` | `git checkout` | `git config --global alias.co checkout` |
| `git ac` | `git add . -A` `git commit` | `git config --global alias.ac '!git add -A && git commit'` |
| `git st` | `git status -sb` | `git config --global alias.st 'status -sb'` |
| `git tags` | `git tag -l` | `git config --global alias.tags 'tag -l'` |
| `git branches` | `git branch -a` | `git config --global alias.branches 'branch -a'` |
| `git remotes` | `git remote -v` | `git config --global alias.remotes 'remote -v'` |

#### Auto-Correct
If you type `git comit` you will get this:

```bash
$ git comit -m "Message"
# git: 'comit' is not a git command. See 'git --help'.

# Did you mean this?
#   commit
```

To call `commit` when `comit` is typed, just enable auto-correct:

```bash
$ git config --global help.autocorrect 1
```

So now you will get this:

```bash
$ git comit -m "Message"
# WARNING: You called a Git command named 'comit', which does not exist.
# Continuing under the assumption that you meant 'commit'
# in 0.1 seconds automatically...
```

#### Color
To add more color to your Git output:

```bash
$ git config --global color.ui 1
```

[*Read more about the Git `config` command.*](http://git-scm.com/docs/git-config)

### Git Resources
| Title | Link |
| ----- | ---- |
| Official Git Site | http://git-scm.com/ |
| Official Git Video Tutorials | http://git-scm.com/videos |
| Code School Try Git | http://try.github.com/ |
| Introductory Reference & Tutorial for Git | http://gitref.org/ |
| Official Git Tutorial | http://git-scm.com/docs/gittutorial |
| Everyday Git | http://git-scm.com/docs/everyday |
| Git Immersion | http://gitimmersion.com/ |
| Ry's Git Tutorial | http://rypress.com/tutorials/git/index.html |
| Git for Designer | http://hoth.entp.com/output/git_for_designers.html |
| Git for Computer Scientists | http://eagain.net/articles/git-for-computer-scientists/ |
| Git Magic | http://www-cs-students.stanford.edu/~blynn/gitmagic/ |

#### Git Books
| Title | Link |
| ----- | ---- |
| Pragmatic Version Control Using Git | http://www.pragprog.com/titles/tsgit/pragmatic-version-control-using-git |
| Pro Git | http://git-scm.com/book |
| Git Internals Peepcode | http://peepcode.com/products/git-internals-pdf |
| Git in the Trenches | http://cbx33.github.com/gitt/ |
| Version Control with Git | http://www.amazon.com/Version-Control-Git-collaborative-development/dp/1449316387 |
| Pragmatic Guide to Git | http://www.pragprog.com/titles/pg_git/pragmatic-guide-to-git |
| Git: Version Control for Everyone | http://www.packtpub.com/git-version-control-for-everyone/book |
