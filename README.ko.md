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

`?w=1`를 diff URL에 추가하면 변경된 코드만 볼 수 있도록, 공백만 바뀐 수정을 제거할 수 있습니다.

## Cloning a Repo

저장소를 클론할 때, 맨 뒤의 `.git`은 생략할 수 있습니다.

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

## Hub - Git Wrapper

[Hub](https://github.com/github/hub)는 깃허브를 좀 더 쉽게 사용할 수 있도록 추가 기능 및 명령을 제공하는 커맨드 라인 깃 래퍼입니다.

이런 명령 대신에

```bash
$ git clone https://github.com/tiimgreen/toc.git
```

이렇게 할 수 있습니다.

```bash
$ hub clone tiimgreen/toc
```

## Previous Branch

커맨드 라인에서 이전 디렉터리로 이동하려면 이렇게 합니다.

```bash
$ cd -
```

비슷하게, 깃에서 마지막 브랜치로 돌아가는 건 이렇게 할 수 있습니다.

```bash
$ git checkout -
# Switched to branch 'master'

$ git checkout -
# Switched to branch 'next'

$ git checkout -
# Switched to branch 'master'
```

## git.io

[git.io](http://git.io)는 깃허브를 위한 간단한 URL 단축기입니다.

[http://git.io/wO0xUg](http://git.io/wO0xUg)

## Gists

[Gists](https://gist.github.com/)는 본격적인 저장소를 만들지 않고, 작은 코드 조각과 일할 수 있는 쉬운 방법입니다.

쉬운 방법이긴 하지만, Gists는 본격적인 저장소처럼 취급할 수 있고 클론도 됩니다.

```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/dULZXXo.png)

## Keyboard Shortcuts

저장소 페이지에서 단축키를 사용하면 쉽게 이동할 수 있습니다.

`t`를 누르면 파일 탐색 페이지로 이동합니다.

`w`를 누르면 브렌치 선택 페이지로 이동합니다.

`s`를 누르면 검색 창으로 이동합니다.

__파일을 보고 있을 때__ (예를 들어 `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`) `y`를 누르면 URL을 지금 보고 있는 페이지를 사실상 고정하도록 합니다. 코드가 바뀐다고 해도 이번에 본 내용을 다시 볼 수 있습니다.

지금 페이지에서 쓸 수 있는 모든 단축키를 보시려면 `?`를 누르세요.

## Closing Issues with Commits

어떤 커밋이 이슈를 고쳤다면, `fix/fixes/fixed`나 `close/closes/closed`를 키워드로 해당 이슈를 닫을 수 있습니다.

```bash
$ git commit -m "Fix cock up, fixes #12"
```

이렇게 하면 이슈를 닫고 클로징 커맨트로 참조하게 합니다.

![Closing Repo](http://i.imgur.com/URXFprQ.png)

## Checking out Pull Requests

풀 리퀘스트를 체크아웃하려면, 다음 명령어로 가져올 수 있습니다.

```bash
$ git fetch origin '+refs/pull/*/head:refs/pull/*'
```

그리고 다음 명령을 사용해 풀 리퀘스트(예를 들어 42라면)를 체크아웃합니다.

```bash
$ git checkout refs/pull/42
```

아니면, 리모트 브랜치에서 가져올 수도 있습니다.

```bash
$ git fetch origin '+refs/pull/*/head:refs/remotes/origin/pr/*'
```

그리고 체크아웃은 이렇게 합니다.

```bash
$ git checkout origin/pr/42
```

그리고 밑의 줄을 .git/config에 추가하면, 자동으로 가져오게도 할 수 있습니다.

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

같은 저장소의 다른 이슈를 링크하기 원한다면, `#`뒤에 이슈 번호만 입력하시면 자동으로 링크됩니다.

다른 저장소의 이슈를 링크하고 싶다면 `사람_이름/저장소_이름#이슈_번호`로 할 수 있습니다. (예 `tiimgreen/toc#12`)

## Syntax Highlighting in Markdown Files

마크다운에서 예를 들어, 루비 코드를 신텍스 하이라이트 하려면 이렇게 합니다.

    ```ruby
    require 'tabbit'
    table = Tabbit.new('Name', 'Email')
    table.add_row('Tim Green', 'tiimgreen@gmail.com')
    puts table.to_s
    ```

이렇게 보입니다.

```ruby
require 'tabbit'
table = Tabbit.new('Name', 'Email')
table.add_row('Tim Green', 'tiimgreen@gmail.com')
puts table.to_s
```

깃허브는 [Linguist](https://github.com/github/linguist)를 사용해 언어를 감지하고 신텍스를 하이라이트합니다. [언어 YAML 파일](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)을 정독하시면 어떤 키워드가 유효한지 확인하실 수 있습니다.

## Commit History by Author

특정 커미터가 한 모든 커밋을 보고 싶다면 URL에 `?author=username`를 추가하세요.

```
https://github.com/rails/rails/commits/master?author=dhh
```

## Empty Commits

`--allow-empty`를 추가하시면 코드의 변경 없이 커밋을 넣을 수 있습니다.

```bash
$ git commit -m "Big-ass commit" --allow-empty
```

![Trololol](http://img1.wikia.nocookie.net/__cb20130905205853/flylikeabird3/images/0/0c/Mexican_troll_face_by_mariodude12312-d5mtl9z.png)

## Comparing Branches

깃허브에서 브랜치 비교를 하시려면, URL을 이런 식으로 바꾸세요.

```
https://github.com/user/repo/compare/{range}
```

`{range}`는 `master...4-1-stable`식으로 적습니다.

예를 들어:
```
https://github.com/rails/rails/compare/master...4-1-stable
```

`{range}` 는 이렇게 적을 수도 있습니다.

```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```

이렇게 하면 특정 날짜나 한 시간 전의 마스터 브랜치의 차이를 확인할 수 있습니다.

## Line Highlighting in Repos

코드 파일 URL의 끝에 `#L52`를 추가하거나 줄 번호를 클릭하면 그 줄 번호를 하이라이트합니다.

`#L53-L60`처럼 범위지정도 가능합니다. 범위를 지정하려면 `shift`키를 누른 채 두 라인을 클릭하면 됩니다.

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

## Emojis

에모지는 풀 리퀘스트, 이슈, 커밋 메세지, README등등에서 `:에모지의_이름:`으로 만들 수 있습니다.

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

깃허브에서 사용 가능한 에모지의 전 목록은 [여기](http://www.emoji-cheat-sheet.com/) 나 [여기](https://github.com/scotch-io/All-Github-Emoji-Icons)에서 확인하실 수 있습니다.

깃허브에서 많이 사용하는 에모지 탑 5위는 이렇습니다.

1. :shipit: `:shipit:`
2. :sparkles: `:sparkles:`
3. :-1: `:-1:`
4. :+1: `:+1:`
5. :clap: `:clap:`

## Images/GIFs

커맨트나 README등등에 이미지와 GIF를 넣을 수 있습니다.

```
![Alt Text](http://image_url.com/image.jpg)
```

![Chuck Norris](http://gifs.joelglovier.com/chuck-norris/chuck-norris.gif)

모든 이미지는 GitHub에서 케쉬합니다. 그래서 호스트가 죽어도 이미지는 여전히 남습니다.

## Quick Quoting

스레드에 답글들 때 전에 누가 말한 어떤 내용을 인용하고 싶다면, 텍스트를 하이라이트하고 `r`을 누르세요. 이렇게 하면 내용을 텍스트 박스에 인용 포맷으로 복사해 줍니다.

![Quick Quote](http://i.imgur.com/TzpMIOA.png)

## Styled Git Status

```bash
$ git status
```

![git status](http://i.imgur.com/o3PEHAA.png)

이렇게 바뀝니다.

```bash
$ git status -sb
```

![git status -sb](http://i.imgur.com/xNI1bT0.png)

## Styled Git Log

```bash
$ git log --all --graph --decorate --oneline --abbrev-commit
```

![git log --all --graph --decorate --oneline --abbrev-commit](http://i.imgur.com/RUPycwI.png)

NOTE: 이 명령을 알리아스 (단축 명령)으로 넣을 수 있습니다. [여기](#aliases)의 소개를 보세요.

## Git Query

깃 쿼리는 모든 이전 커밋 메시지에서 검색해 가장 최근의 쿼리에 맞는 커밋을 찾아줍니다.

```bash
$ git show :/query
```

`query`에는 검색하고 싶은 말을 넣으세요. 주어진 검색어가 있는 가장 마지막 커밋을 표시하고 변경된 라인을 보여줍니다.

```bash
$ git show :/typo
```
![git show :/query](http://i.imgur.com/SA0oZbE.png)

NOTE: 나오려면 `q`를 누르세요.

## Merged Branches

```bash
$ git branch --merged
```

이 명령어는 현재 브랜치에 머지된 모든 브랜치의 목록을 보여줍니다.

거꾸로

```bash
$ git branch --no-merged
```

이 명령어는 현재 브랜치에 머지되지 않은 브랜치의 목록을 보여줍니다.

## Quick Licensing

저장소를 만들 때, 깃허브는 만들어진 저작권을 추가할 수 있는 옵션을 제공합니다.

![Licese](http://i.imgur.com/Chqj4Fg.png)

이미 있는 저장소에도 웹 인터페이스에서 새 파일을 만들어 추가할 수 있습니다.
이름에 `LICENSE`를 입력하면 옵션으로 템플릿을 사용할 수 있습니다.

![License](http://i.imgur.com/fTjQict.png)

`.gitignore`에도 똑같이 적용됩니다.

## TODO Lists

이슈와 풀 리퀘스트에서 밑의 문법으로 체크박스를 넣을 수 있습니다.(스페이스에 주의하세요.)

```
- [ ] Be awesome
- [ ] Do stuff
- [ ] Sleep
```

![TODO List](http://i.imgur.com/k2qZi56.png)

체크박스가 클릭 되면, 순수 마크다운에서 갱신이 이루어집니다.

```
- [x] Be awesome
- [x] Do stuff
- [ ] Sleep
```

## .gitconfig Recommendations

`.gitconfig`는 모든 설정이 들어있는 파일입니다.

### Aliases

알리아스는 커스텀 깃 명령어를 등록할 수 있는 핼퍼입니다. 예를 들어 `git a`로 `git add --all`를 실행하게 할 수 있습니다.

알리아스를 추가하려면 `~/.gitconfig`를 찾아 다음 포멧으로 입력하거나

```
[alias]
	co = checkout
	cm = commit
	p = push
```

커맨드 라인에서 다음 명령을 입력합니다.

```bash
$ git config alias.new_alias git_function
```

예를들면

```bash
$ git config alias.cm commit
```

NOTE: 여러 함수를 알리아스하려면 따옴표를 이용하세요.

```bash
$ git config alias.ac 'add -A . && commit'
```

여기 몇 가지 권장 알리아스가 있습니다.

| Alias | Current Command | What to Type |
| --- | --- | --- |
| `git cm` | `git commit` | `git config --global alias.cm commit` |
| `git co` | `git checkout` | `git config --global alias.co checkout` |
| `git ac` | `git add . -A` `git commit` | `git config --global alias.ac '!git add -A && git commit'` |
| `git st` | `git status -sb` | `git config --global alias.st 'status -sb'` |

### Auto-correct

현재 `git comit`를 치면 이런 결과를 보실 수 있습니다.

```bash
$ git comit -m "Message"
# git: 'comit' is not a git command. See 'git --help'.

# Did you mean this?
# 	commit
```

`comit`을 쳤을 때 `commit`을 부르려면, 자동 교정을 켜두세요.

```bash
$ git config --global help.autocorrect 1
```

이제 이런 결과를 보실 수 있습니다.

```bash
$ git comit -m "Message"
# WARNING: You called a Git command named 'comit', which does not exist.
# Continuing under the assumption that you meant 'commit'
# in 0.1 seconds automatically...
```

### Color

깃 커맨드 라인에 색을 넣으려면 이렇게 하세요.

```bash
$ git config --global color.ui 1
```

# Sharing

[트위터](https://twitter.com/intent/tweet?source=webclient&text=http%3A%2F%2Fgit.io%2FvvT17g%20-%20GitHub%20치트%20시트)에 공유하기
