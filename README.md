# Github Cheat Sheet

All the hidden and not hidden features of GitHub. Taken from Zach Holmans [talk](https://www.youtube.com/watch?v=Foz9yvMkvlA) at Aloha Ruby Conference 2012.

## Ignore Whitespace

Adding `?w=1` to any diff URL will remove any changes only in whitespace, enabling you to see only that code that has changed.

## Cloning a Repo

When cloning a repo the `.git` can be left off the edge.

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

## Hub - Git wrapper

[Hub](https://github.com/github/hub) is a command line tool that wraps git in order to extend it with extra features and commands that make working with GitHub easier.

This allows you to do things like:

```bash
$ hub clone tiimgreen/toc
```

Which translates to:

```bash
$ git clone git://github.com/tiimgreen/toc.git
```

## git.io

[git.io](http://git.io) is a simple URL shortener for GitHub.

[http://git.io/wO0xUg](http://git.io/wO0xUg)

## Gists

[Gists](https://gist.github.com/) are an easy way to work with small bits of code without creating a fully fledged repo.

Gists are also full repos so can be cloned like any other:
```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/dULZXXo.png)

## Keyboard Shortcuts

When on a repo page keyboard shortcuts allow you to navigate easily.

Pressing `t` will bring up a file explorer.

Pressing `w` will bring up the branch selector.

Pressing `s` will select the search bar.

To see all of the shortcuts for given page type `shift+?`

## Closing issues with commits

If a particular commit fixes an issue, any of the keywords `fix/fixes/fixed` or `close/closes/closed`, followed by the issue number, will close the issue.

```bash
$ git commit -m "Fix cock up, fixes #12"
```

## Cross-link issues

If you want to link to another issue in the same repo, simple type hash `#` then the issue number, it will be auto-linked.

To link to an issue in another repo, `user_name/repo_name#ISSUE_NUMBER` e.g. `tiimgreen/toc#12`.

## Syntax Highlighting in README

To add syntax highlighting to code in README:

![Syntax Highlighting](http://i.imgur.com/V9YteWf.png)

```ruby
require 'tabbit'
table = Tabbit.new('Name', 'Email')
table.add_row('Tim Green', 'tiimgreen@gmail.com')
puts table.to_s
```

## Commit History by Author

To view all commits on a repo by author add `?author=username` to the URL.

```
https://github.com/rails/rails/commits/master?author=dhh
```

## Line highlighting in repos

Adding `#L52` to the end of a code file URL will highlight that line number.

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

## Emojis

Emojis can be generated on Pull Requests, Issues, READMEs, etc. using `:name_of_emoji:`

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

The full list of supported Emojis on GitHub can be found [here](http://www.emoji-cheat-sheet.com/).
