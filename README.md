# Github Cheat Sheet

All the hidden and not hidden features of GitHub.

### Ignore Whitespace

Adding `?w=1` to any diff URL will remove any changes only in whitespace, enabling you to see only that code that has changed.

### Cloning a Repo

When cloning a repo the `.git` can be left off the edge.

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

### Git wrapper

[Hub](https://github.com/github/hub) is a command line tool that wraps git in order to extend it with extra features and commands that make working with GitHub easier.

This allows you to do things like:

```bash
$ hub clone tiimgreen/toc
```

Which translates to:

```bash
$ git clone git://github.com/tiimgreen/toc.git
```

### git.io

[git.io](http://git.io) is a simple URL shortner for GitHub.

### Emojis

Emojis can be generated on Pull Requests, Issues, READMEs, etc. using `:name_of_emoji:`

```
:smile:
:poop:
```

:smile:
:poop:

The full list of supported Emojis on GitHub can be found [here](http://www.emoji-cheat-sheet.com/).
