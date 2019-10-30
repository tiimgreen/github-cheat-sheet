# GitHub 치트 시트 [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

Git과 GitHub에서 꽤 유용하지만 숨겨져 있는 기능들에 대해 다룹니다. 이 치트 시트는 [Zach Holman](https://github.com/holman)이 Aloha Ruby Conference 2012에서 발표한 [Git과 GitHub의 비밀들](http://confreaks.tv/videos/aloharuby2012-git-and-github-secrets)([슬라이드](https://speakerdeck.com/holman/git-and-github-secrets))과 WDCNZ 2013에서 발표한 [Git과 GitHub에 대한 더 많은 비밀들](https://vimeo.com/72955426)([슬라이드](https://speakerdeck.com/holman/more-git-and-github-secrets))에서 영감을 받아 작성되었습니다.

*단축주소: [`http://git.io/sheet`](http://git.io/sheet)*

*Read this in other languages: [English](README.md), [한국어](README.ko.md), [日本語](README.ja.md), [简体中文](README.zh-cn.md), [正體中文](README.zh-tw.md).*

# 목록

 - [GitHub](#github)
  - [Ignore Whitespace](#ignore-whitespace)
  - [Adjust Tab Space](#adjust-tab-space)
  - [Commit History by Author](#commit-history-by-author)
  - [Cloning a Repository](#cloning-a-repository)
  - [Branch](#branch)
    - [Compare all Branches to Another Branch](#compare-all-branches-to-another-branch)
    - [Comparing Branches](#comparing-branches)
    - [Compare Branches across Forked Repositories](#compare-branches-across-forked-repositories)
  - [Gists](#gists)
  - [Git.io](#gitio)
  - [Keyboard Shortcuts](#keyboard-shortcuts)
  - [Line Highlighting in Repositories](#line-highlighting-in-repositories)
  - [Closing Issues via Commit Messages](#closing-issues-via-commit-messages)
  - [Cross-Link Issues](#cross-link-issues)
  - [Locking Conversations](#locking-conversations)
  - [CI Status on Pull Requests](#ci-status-on-pull-requests)
  - [Filters](#filters)
  - [Syntax Highlighting in Markdown Files](#syntax-highlighting-in-markdown-files)
  - [Emojis](#emojis)
  - [Images/GIFs](#imagesgifs)
    - [Embedding Images in GitHub Wiki](#embedding-images-in-github-wiki)
  - [Quick Quoting](#quick-quoting)
  - [Pasting Clipboard Image to Comments](#pasting-clipboard-image-to-comments)
  - [Quick Licensing](#quick-licensing)
  - [Task Lists](#task-lists)
    - [Task Lists in Markdown Documents](#task-lists-in-markdown-documents)
  - [Relative Links](#relative-links)
  - [Metadata and Plugin Support for GitHub Pages](#metadata-and-plugin-support-for-github-pages)
  - [Viewing YAML Metadata in your Documents](#viewing-yaml-metadata-in-your-documents)
  - [Rendering Tabular Data](#rendering-tabular-data)
  - [Rendering PDF](#rendering-pdf)
  - [Revert a Pull Request](#revert-a-pull-request)
  - [Diffs](#diffs)
    - [Rendered Prose Diffs](#rendered-prose-diffs)
    - [Diffable Maps](#diffable-maps)
    - [Expanding Context in Diffs](#expanding-context-in-diffs)
    - [Diff or Patch of Pull Request](#diff-or-patch-of-pull-request)
    - [Rendering and diffing images](#rendering-and-diffing-images)
  - [Hub](#hub)
  - [Contribution Guidelines](#contribution-guidelines)
    - [CONTRIBUTING file](#contributing-file)
    - [ISSUE_TEMPLATE file](#issue_template-file)
    - [PULL_REQUEST_TEMPLATE file](#pull_request_template-file)
  - [Octicons](#octicons)
  - [GitHub Resources](#github-resources)
    - [GitHub Talks](#github-talks)
 - [Git](#git)
  - [Remove All Deleted Files from the Working Tree](#remove-all-deleted-files-from-the-working-tree)
  - [Previous Branch](#previous-branch)
  - [Stripspace](#stripspace)
  - [SSH keys](#ssh-keys)
  - [Checking out Pull Requests](#checking-out-pull-requests)
  - [Empty Commits](#empty-commits)
  - [Styled Git Status](#styled-git-status)
  - [Styled Git Log](#styled-git-log)
  - [Git Query](#git-query)
  - [Git Grep](#git-grep)
  - [Merged Branches](#merged-branches)
  - [Fixup and Autosquash](#fixup-and-autosquash)
  - [Web Server for Browsing Local Repositories](#web-server-for-browsing-local-repositories)
  - [Git Configurations](#git-configurations)
    - [Aliases](#aliases)
    - [Auto-Correct](#auto-correct)
    - [Color](#color)
  - [Git Resources](#git-resources)
    - [Git Books](#git-books)

## GitHub

### Ignore Whitespace

`?w=1`를 diff URL에 추가하면 변경된 코드만 볼 수 있도록, 공백만 바뀐 수정을 제거할 수 있습니다.

![Diff without whitespace](https://camo.githubusercontent.com/797184940defadec00393e6559b835358a863eeb/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f776869746573706163652e706e67)

[*GitHub의 비밀을 더 읽어 보세요.*](https://github.com/blog/967-github-secrets)

### Adjust Tab Space

diff나 파일 URL에 `?ts=4`를 덧붙이면 탭 문자의 크기를 기본값인 공백 8개 대신 4개로 보여줍니다. `ts` 뒤의 숫자는 설정에 맞게 변경 하실 수 있습니다. gist나 raw 파일 보기에는 적용 되지 않습니다만, [크롬 확장 프로그램](https://chrome.google.com/webstore/detail/github-tab-size/ofjbgncegkdemndciafljngjbdpfmbkn)이나 으로 자동화 할 수 있습니다.

여기에 있는 Go 소스 파일은 `?ts=4`를 붙이기 전에는 이렇습니다.

![Before, tab space example](http://i.imgur.com/GIT1Fr0.png)

그리고 `?ts=4`를 붙인 다음에는 이렇게 됩니다.

![After, tab space example](http://i.imgur.com/70FL4H9.png)

### Commit History by Author

특정 커미터가 한 모든 커밋을 보고 싶다면 URL에 `?author={user}`를 추가하세요.

```
https://github.com/rails/rails/commits/master?author=dhh
```

![DHH commit history](http://i.imgur.com/S7AE29b.png)

[*커밋 뷰간의 차이에 대해 더 읽어보세요.*](https://help.github.com/articles/differences-between-commit-views)

### Cloning a Repository

저장소를 클론할 때, 맨 뒤의 `.git`은 생략할 수 있습니다.

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

[*Git `clone` 명령에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-clone)

### Branch

#### Compare all Branches to Another Branch

저장소의 [브랜치](https://github.com/tiimgreen/github-cheat-sheet/branches) 페이지는, 커밋 버튼의 뒤에 있습니다.

```
https://github.com/{user}/{repo}/branches
```

... 메인 브랜치에 머지되지 않은 모든 브랜치의 리스트를 볼 수 있습니다.

여기에서 버튼 클릭으로 비교 페이지에 접속하거나 브랜치를 삭제할 수 있습니다.

![Compare branches not merged into master in rails/rails repo - https://github.com/rails/rails/branches](http://i.imgur.com/0FEe30z.png)

#### Comparing Branches

GitHub에서 브랜치 비교를 하시려면, URL을 이런 식으로 바꾸세요.

```
https://github.com/{user}/{repo}/compare/{range}
```

`{range}`는 `master...4-1-stable`과 같이 적습니다.

예를 들어

```
https://github.com/rails/rails/compare/master...4-1-stable
```

![Rails branch compare example](http://i.imgur.com/tIRCOsK.png)

`{range}`는 이렇게 적을 수도 있습니다.

```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```

*날짜는 `YYYY-MM-DD` 형식으로 적습니다*

![Another compare example](http://i.imgur.com/5dtzESz.png)

브랜치는 `diff`나 `patch` 뷰로도 확인할 수 있습니다.

```
https://github.com/rails/rails/compare/master...4-1-stable.diff
https://github.com/rails/rails/compare/master...4-1-stable.patch
```

[*시간으로 커밋을 비교하는 법에 대해 더 읽어 보세요.*](https://help.github.com/articles/comparing-commits-across-time)

#### Compare branches across forked repositories

포크된 저장소 간의 브랜치를 비교하려면 URL을 이렇게 변경하세요.

```
https://github.com/{user}/{repo}/compare/{foreign-user}:{branch}...{own-branch}
```

예를 들면

```
https://github.com/rails/rails/compare/byroot:idempotent-counter-caches...master
```

![Forked branch compare](http://i.imgur.com/Q1W6qcB.png)

### Gists

[Gist](https://gist.github.com/)는 본격적인 저장소를 만들지 않고, 작은 코드 조각과 일할 수 있는 쉬운 방법입니다.

![Gist](http://i.imgur.com/VkKI1LC.png?1)

[이렇게](https://gist.github.com/tiimgreen/10545817.pibb) Gist URL 뒤에 `.pibb`를 넣으면 다른 사이트에 첨부할 수 있는 *HTML 온리* 버전을 만들 수 있습니다.

Gist는 저장소처럼 취급할 수 있고 클론도 됩니다.

```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/BcFzabp.png)

이는 Gists에서도 수정하고 업데이트를 푸시할 수 있다는 의미입니다.

```bash
$ git commit
$ git push
Username for 'https://gist.github.com':
Password for 'https://tiimgreen@gist.github.com':
```

하지만, Gists는 디렉터리를 지원하지 않습니다. 모든 파일은 저장소의 루트에 넣을 필요가 있습니다.
[*Gist를 만드는 법에 대해 더 읽어보세요.*](https://help.github.com/articles/creating-gists)

### Git.io

[Git.io](http://git.io)는 GitHub를 위한 간단한 URL 단축기입니다.

![Git.io](http://i.imgur.com/6JUfbcG.png?1)

Curl으로 순수 HTTP를 통해 사용하실 수도 있습니다.

```bash
$ curl -i http://git.io -F "url=https://github.com/..."
HTTP/1.1 201 Created
Location: http://git.io/abc123

$ curl -i http://git.io/abc123
HTTP/1.1 302 Found
Location: https://github.com/...
```

[*Git.io에 대해 더 읽어 보세요.*](https://github.com/blog/985-git-io-github-url-shortener)

### Keyboard Shortcuts

저장소 페이지에서 단축키를 사용하면 쉽게 이동할 수 있습니다.

 - `t`를 누르면 파일 탐색 페이지로 이동합니다.
 - `w`를 누르면 브랜치 선택 페이지로 이동합니다.
 - `s`를 누르면 현재 저장소의 검색창으로 포커스가 이동합니다. 백스페이스를 누르면 채워져 있는 "This repository"를 지워 GitHub 전체에서 검색할 수 있게 됩니다.
 - `l`을 누르면 이슈의 라벨을 수정할 수 있습니다.
 - __파일을 보고 있을 때__ (예를 들어 `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`) `y`를 누르면 URL을 지금 보고 있는 페이지를 사실상 고정하도록 합니다. 코드가 바뀐다고 해도 이번에 본 내용을 다시 볼 수 있습니다.

지금 페이지에서 쓸 수 있는 모든 단축키를 보시려면 `?`를 누르세요.

![Keyboard shortcuts](http://i.imgur.com/y5ZfNEm.png)

[*사용할 수 있는 검색 문법에 대해 더 읽어 보세요.*](https://help.github.com/articles/search-syntax/)

### Line Highlighting in Repos

코드 파일 URL의 끝에 `#L52`를 추가하거나 줄 번호를 클릭하면 그 줄 번호를 하이라이트합니다.

`#L53-L60`처럼 범위 지정도 가능합니다. 범위를 지정하려면 `shift`키를 누른 채 두 라인을 클릭하면 됩니다.

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

### Closing Issues with Commits

어떤 커밋이 이슈를 고쳤다면, `fix/fixes/fixed`, `close/closes/closed`, `resolve/resolves/resolved`를 키워드로 해당 이슈가 마스터 브랜치에 커밋 될 때 닫을 수 있습니다.

```bash
$ git commit -m "Fix screwup, fixes #12"
```

이렇게 하면 이슈를 닫고 클로징 커밋으로 참조하게 합니다.

![Closing Repo](http://i.imgur.com/Uh1gZdx.png)

[*커밋 메시지로 이슈 닫기에 대해 더 읽어 보세요.*](https://help.github.com/articles/closing-issues-via-commit-messages)

### Cross-Link Issues

같은 저장소의 다른 이슈를 링크하기 원한다면, `#` 뒤에 이슈 번호만 입력하시면 자동으로 링크됩니다.

다른 저장소의 이슈를 링크하고 싶다면 `{user}/{repo}#이슈_번호`로 할 수 있습니다. (예 `tiimgreen/toc#12`)

![Cross-Link Issues](https://camo.githubusercontent.com/447e39ab8d96b553cadc8d31799100190df230a8/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f7265666572656e6365732e706e67)

### Locking Conversations

풀 리퀘스트와 이슈는 저장소의 주인이나 협업자가 잠글 수 있습니다.

![Lock conversation](https://cloud.githubusercontent.com/assets/2723/3221693/bf54dd44-f00d-11e3-8eb6-bb51e825bc2c.png)

이는 프로젝트의 협업자가 아닌 사람은 더 이상 댓글을 달 수 없게 된다는 말입니다.

![Comments locked](https://cloud.githubusercontent.com/assets/2723/3221775/d6e513b0-f00e-11e3-9721-2131cb37c906.png)

[*대화 잠그기에 대해 더 읽어 보세요.*](https://github.com/blog/1847-locking-conversations)

### CI Status on Pull Requests

정확히 설정되었다면, 풀 리퀘스트를 받거나 풀 리퀘스트에 새로운 커밋을 할 때마다, [Travis CI](https://travis-ci.org/)가 풀 리퀘스트를 빌드 할 것입니다. [Travis CI 시작하기](http://docs.travis-ci.com/user/getting-started/)를 좀 더 읽어보세요.

[![Travis CI status](https://cloud.githubusercontent.com/assets/1687642/2700187/3a88838c-c410-11e3-9a46-e65e2a0458cd.png)](https://github.com/octokit/octokit.rb/pull/452)

[*커밋 상태 API에 대해 좀 더 읽어보세요.*](https://github.com/blog/1227-commit-status-api)

### Filters

이슈, 풀 리퀘스트 둘 다 유저 인터페이스에서 필터링이 가능합니다.

레일스 저장소 <https://github.com/rails/rails/issues>에서, "activerecord" 라벨을
선택하여 다음 필터를 만들 수 있습니다.

`is:issue label:activerecord`

하지만, activerecord 라벨이 없는 모든 이슈를 찾을 수도 있습니다.

`is:issue -label:activerecord`

덧붙여, 풀 리퀘스트에도 동작합니다.

`is:pr -label:activerecord`

GitHub는 열리거나 닫힌 이슈와 풀 리퀘스트를 위한 탭이 있습니다만 머지된
풀 리퀘스트도 볼 수 있습니다. 다음 필터를 입력하기만 하면 됩니다.

`is:merged`

[*이슈 검색에 대해 좀 더 읽어보세요.*](https://help.github.com/articles/searching-issues)

마지막으로 이제 상태 API의 상태에 의한 필터도 가능해졌습니다.

성공 상태의 풀 리퀘스트는 이렇게 검색합니다.

`status:success`

[*상태 API 검색에 대해 좀 더 읽어보세요.*](https://github.com/blog/2014-filter-pull-requests-by-status)

### Syntax Highlighting in Markdown Files

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

GitHub는 [Linguist](https://github.com/github/linguist)를 사용해 언어를 감지하고 신택스를 하이라이트합니다. [언어 YAML 파일](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)을 정독하시면 어떤 키워드가 유효한지 확인하실 수 있습니다.

[*GitHub Flavored 마크다운에 대해 더 읽어 보세요.*](https://help.github.com/articles/github-flavored-markdown)

### Emojis

에모지는 풀 리퀘스트, 이슈, 커밋 메시지, 저장소 설명 등에 `:에모지의_이름:`으로 넣을 수 있습니다.

GitHub에서 사용 가능한 에모지의 전 목록은 [emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com/)나 [scotch-io/All-GitHub-Emoji-Icons](https://github.com/scotch-io/All-GitHub-Emoji-Icons)에서 확인하실 수 있습니다.
편리한 에모지 검색 엔진은 [emoji.muan.co](http://emoji.muan.co/)에 있습니다.

GitHub에서 많이 사용하는 에모지 탑 5위는 이렇습니다.

1. `:shipit:`
2. `:sparkles:`
3. `:-1:`
4. `:+1:`
5. `:clap:`

### Images/GIFs

댓글이나 README 등에 이미지와 GIF를 넣을 수 있습니다.

```
![Alt Text](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)
```

저장소에 있는 이미지는 직접 불러서 사용할 수 있습니다.

```
![Alt Text](https://github.com/{user}/{repo}/raw/master/path/to/image.gif)
```

![Peter don't care](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)

모든 이미지는 GitHub에서 캐시합니다. 그래서 호스트가 죽어도 이미지는 여전히 남습니다.

#### Embedding Images in GitHub Wiki

이미지를 위키 페이지에 넣는 방법은 여럿 있습니다. 위에 보이는 일반 마크다운 문법도 있지만, 이미지에 높이와 넓이를 지정할 수 있는 문법도 있습니다.

```markdown
[[ http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif | height = 100px ]]
```

이렇게 보입니다.

![Just a screenshot](http://i.imgur.com/J5bMf7S.png)

### Quick Quoting

스레드에 답글을 달 때 전에 누가 말한 어떤 내용을 인용하고 싶다면, 텍스트를 하이라이트하고 `r`을 누르세요. 이렇게 하면 내용을 텍스트 박스에 인용 포맷으로 복사해 줍니다.

![Quick Quote](https://f.cloud.github.com/assets/296432/124483/b0fa6204-6ef0-11e2-83c3-256c37fa7abc.gif)

[*빠른 인용에 대해 더 읽어 보세요.*](https://github.com/blog/1399-quick-quotes)

### Pasting Clipboard Image to Comments

_(크롬에서만 동작합니다)_

스크린샷을 찍고 클립보드에 복사한 경우 (mac: `cmd-ctrl-shift-4`), 간단히 이미지를 댓글 영역에 붙여넣을(`cmd-v / ctrl-v`) 수 있고 이는 자동으로 GitHub에 업로드 됩니다.

![Pasting Clipboard Image to Comments](https://cloud.githubusercontent.com/assets/39191/5794265/39c9b65a-9f1b-11e4-9bc7-04e41f59ea5f.png)

[*issue attachments에 대해 더 읽어 보세요.*](https://help.github.com/articles/issue-attachments)

### Quick Licensing

저장소를 만들 때, GitHub는 만들어진 저작권을 추가할 수 있는 옵션을 제공합니다.

![License](http://i.imgur.com/Chqj4Fg.png)

이미 있는 저장소에도 웹 인터페이스에서 새 파일을 만들어 추가할 수 있습니다.
이름에 `LICENSE`를 입력하면 옵션으로 템플릿을 사용할 수 있습니다.

![License](http://i.imgur.com/fTjQict.png)

`.gitignore`에도 똑같이 적용됩니다.

[*오픈 소스 저작권에 대해 더 읽어 보세요.*](https://help.github.com/articles/open-source-licensing)

### Task Lists

이슈와 풀 리퀘스트에서 아래의 문법으로 체크박스를 넣을 수 있습니다.(스페이스에 주의하세요.)

```
- [ ] Be awesome
- [ ] Prepare dinner
  - [ ] Research recipe
  - [ ] Buy ingredients
  - [ ] Cook recipe
- [ ] Sleep
```

![Task List](http://i.imgur.com/jJBXhsY.png)

체크박스를 클릭하면, 순수 마크다운에서 갱신이 이루어집니다.

```
- [x] Be awesome
- [ ] Prepare dinner
  - [x] Research recipe
  - [x] Buy ingredients
  - [ ] Cook recipe
- [ ] Sleep
```

[*할 일 목록에 대해 더 읽어 보세요.*](https://help.github.com/articles/writing-on-github#task-lists)

#### Task Lists in Markdown Documents

이제 마크다운 문서에서 **읽기 전용** 체크리스트를 넣을 수 있습니다.

```
- [ ] Mercury
- [x] Venus
- [x] Earth
  - [x] Moon
- [x] Mars
  - [ ] Deimos
  - [ ] Phobos
```

- [ ] Mercury
- [x] Venus
- [x] Earth
  - [x] Moon
- [x] Mars
  - [ ] Deimos
  - [ ] Phobos

[*마크다운 문서에서의 할 일 목록에 대해 더 읽어 보세요.*](https://github.com/blog/1825-task-lists-in-all-markdown-documents)

### Relative Links

상대 경로 링크는 마크다운 파일이 내부 콘텐츠로 링크될 때 추천합니다.

```markdown
[Link to a header](#awesome-section)
[Link to a file](docs/readme)
```

절대 경로 링크는 URL이 변경 될 때마다 변경해야 합니다. (예를 들어 저장소 이름 변경, 아이디 변경, 프로젝트 포크)
상대 경로 링크를 사용하면 문서를 쉽게 스스로 독립적으로 만들 수 있습니다.

[*상대 경로 링크에 대해 더 읽어 보세요.*](https://help.github.com/articles/relative-links-in-readmes)

### Metadata and Plugin Support for GitHub Pages

지킬로 작성된 페이지와 포스트에서, 저장소 정보는 예를 들어 `{{ site.github.project_title }}`처럼 `site.github` 이름 공간으로 사용하고 표시할 수 있습니다.

Jemoji와 jekyll-mentions 플러그인은 GitHub.com에서처럼 [emoji](#emojis)와 [@mentions](https://github.com/blog/821)를 지킬 포스트와 페이지에서 사용하게 합니다.

[*저장소 메타 데이터와 GitHub 페이지의 플러그인 지원에 대해 더 읽어 보세요.*](https://github.com/blog/1797-repository-metadata-and-plugin-support-for-github-pages)

### Viewing YAML Metadata in your Documents

[Jekyll](http://jekyllrb.com/)이나 [GitHub Pages](http://pages.github.com/) 같은 많은 블로그에서 포스트의 처음에 YAML 포멧의 메타데이터를 필요로 합니다. GitHub는 이 메타 정보를 읽기 편하게 테이블로 표시해 줍니다.

![YAML metadata](https://camo.githubusercontent.com/47245aa16728e242f74a9a324ce0d24c0b916075/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f36343035302f313232383236372f65303439643063362d323761302d313165332d396464382d6131636432323539393334342e706e67)

[*문서에서 YAML 메타데이터 보기에 대해 더 읽어 보세요.*](https://github.com/blog/1647-viewing-yaml-metadata-in-your-documents)

### Rendering Tabular Data

GitHub는 `.csv`(comma-separated)와 `.tsv`(tab-separated) 파일에 대해 표(tabular) 데이터 보기를 지원합니다.

![Tabular data](https://camo.githubusercontent.com/1b6dd0157ffb45d9939abf14233a0cb13b3b4dfe/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f3238323735392f3937363436322f33323038336463652d303638642d313165332d393262322d3566323863313061353035392e706e67)

[*표 데이터 표시에 대해 더 읽어 보세요.*](https://github.com/blog/1601-see-your-csvs)

### Rendering PDF

GitHub에서 PDF를 렌더할 수 있습니다.

![PDF](https://cloud.githubusercontent.com/assets/1000669/7492902/f8493160-f42e-11e4-8cea-1cb4f02757e7.png)

[*PDF 렌더링에 대해 더 읽어 보세요.*](https://github.com/blog/1974-pdf-viewing)

### Revert a Pull Request

풀 리퀘스트가 머지된 후에, 아무 도움이 안되거나 머지가 잘못된 결정이었다는 걸
눈치 챌 때가 있습니다.

풀 리퀘스트 페이지의 커밋의 오른쪽에 있는 **Revert** 버튼을 클릭하면 이 풀 리퀘스트를 되돌리는 풀 리퀘스트를 만들어 되돌릴 수 있습니다.

![Revert button](https://camo.githubusercontent.com/0d3350caf2bb1cba53123ffeafc00ca702b1b164/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f68656c702f70756c6c5f72657175657374732f7265766572742d70756c6c2d726571756573742d6c696e6b2e706e67)

[*풀 리퀘스트 되돌리기에 대해 더 읽어 보세요.*](https://github.com/blog/1857-introducing-the-revert-button)

### Diffs

#### Rendered Prose Diffs

GitHub에서 지원하는 산문(prose) 파일(예를 들어 Markdown)이 있는 커밋과 풀 리퀘스트에서는 *source*와 *rendered* 뷰 기능을 사용할 수 있습니다.

![Source / Rendered view](https://github-images.s3.amazonaws.com/help/repository/rendered_prose_diff.png)

"rendered" 버튼을 클릭하시면 렌더된 문서에서 변경을 확인하실 수 있습니다. 렌더된 산문(prose) 뷰는 문장을 추가, 삭제, 변경했을 때 유용합니다.

![Rendered Prose Diffs](https://f.cloud.github.com/assets/17715/2003056/3997edb4-862b-11e3-90be-5e9586edecd7.png)

[*렌더된 산문(prose) diff에 대해 더 읽어 보세요.*](https://github.com/blog/1784-rendered-prose-diffs)

#### Diffable Maps

지오데이터가 포함된 커밋이나 풀 리퀘스트를 볼 때마다 GitHub는 무엇이 변경 되었는지 시각적으로 보여줍니다.

[![Diffable Maps](https://f.cloud.github.com/assets/282759/2090660/63f2e45a-8e97-11e3-9d8b-d4c8078b004e.gif)](https://github.com/benbalter/congressional-districts/commit/2233c76ca5bb059582d796f053775d8859198ec5)

[*diff 가능한 맵에 대해 더 읽어 보세요.*](https://github.com/blog/1772-diffable-more-customizable-maps)

#### Expanding Context in Diffs

diff의 닫아둔 곳의 *펼침* 버튼을 클릭하면, 문맥을 더 볼 수 있습니다. 전체 파일을 표시할 때까지 계속 *펼칠* 수 있으며, GitHub에서 diff가 표시되는 장소라면 어디서든 사용가능합니다.

![Expanding Context in Diffs](https://f.cloud.github.com/assets/22635/1610539/863c1f64-5584-11e3-82bf-151b406a272f.gif)

[*diff에서의 문맥 확장에 대해 더 읽어 보세요.*](https://github.com/blog/1705-expanding-context-in-diffs)

#### Diff or Patch of Pull Request

URL 뒤에 `.diff`나 `.patch`를 붙이면 풀 리퀘스트의 diff를 얻을 수 있습니다.
예를 들면

```
https://github.com/tiimgreen/github-cheat-sheet/pull/15
https://github.com/tiimgreen/github-cheat-sheet/pull/15.diff
https://github.com/tiimgreen/github-cheat-sheet/pull/15.patch
```

`.diff` 확장자는 이런 내용의 평범한(plain) 텍스트를 줍니다.

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

#### Rendering and diffing images

GitHub는 PNG, JPG, GIF, PSD를 포함한 여러 일반적인 이미지 형식을 표시할 수 있습니다. 추가적으로 이미지 형식의 diff를 표시하는 여러 방법을 제공합니다.

[![Diffable PSD](https://cloud.githubusercontent.com/assets/2546/3165594/55f2798a-eb56-11e3-92e7-b79ad791a697.gif)](https://github.com/blog/1845-psd-viewing-diffing

[*이미지 diff에 대해 더 읽어 보세요.*](https://help.github.com/articles/rendering-and-diffing-images)

### Hub

[Hub](https://github.com/github/hub)는 GitHub를 좀 더 쉽게 사용할 수 있도록 추가 기능 및 명령을 제공하는 커맨드 라인 Git 래퍼입니다.

이렇게 할 수 있습니다.

```bash
$ hub clone tiimgreen/toc
```

[*Hub가 제공하는 더 멋진 기능들을 확인해 보세요.*](https://github.com/github/hub#commands)

### Contribution Guidelines

GitHub는 프로젝트에 기여하는 사용자를 위한 세 가지 각기 다른 파일을 지원합니다.
이 파일은 저장소의 제일 위나 그 아래의 `.github` 디렉터리에 위치할 수 있습니다.

### CONTRIBUTING File

저장소의 제일 위나 그 아래의 `.github` 디렉터리에 `CONTRIBUTING`이나 `CONTRIBUTING.md` 파일을 넣어두면 기여자가 이슈를 만들거나 풀 리퀘스트를 만들 때 링크로 보여줍니다.

![Contributing Guidelines](https://camo.githubusercontent.com/71995d6b0e620a9ef1ded00a04498241c69dd1bf/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f736b697463682f6973737565732d32303132303931332d3136323533392e6a7067)

[*기여하기에 대해 더 읽어 보세요.*](https://github.com/blog/1184-contributing-guidelines)

### ISSUE_TEMPLATE file

프로젝트의 새로운 이슈에 사용될 템플릿을 지정할 수 있습니다. 사용자가 새 이슈를 생성하면 이슈 창이 이 파일의 내용으로 채워집니다. 저장소의 제일 위나 그 아래의 `.github` 디렉터리에 `ISSUE_TEMPLATE`이나 `ISSUE_TEMPLATE.md` 파일을 넣어 두세요.

[*이슈 템플릿에 대해 더 읽어 보세요.*](https://github.com/blog/2111-issue-and-pull-request-templates)

[이슈 템플릿 파일 생성기](https://www.talater.com/open-source-templates/)

![GitHub Issue template](https://cloud.githubusercontent.com/assets/25792/13120859/733479fe-d564-11e5-8a1f-a03f95072f7a.png)

### PULL_REQUEST_TEMPLATE file

프로젝트의 새로운 풀 리퀘스트에 사용될 템플릿을 지정할 수 있습니다. 사용자가 새 풀 리퀘스트를 생성하면 텍스트 영역이 이 파일의 내용으로 채워집니다. 저장소의 제일 위나 `.github` 디렉터리에 `PULL_REQUEST_TEMPLATE`이나 `PULL_REQUEST_TEMPLATE.md` 파일을 넣어 두세요.

[*풀 리퀘스트 템플릿에 대해 더 읽어 보세요.*](https://github.com/blog/2111-issue-and-pull-request-templates)

[풀 리퀘스트 템플릿 파일 생성기](https://www.talater.com/open-source-templates/)

### Octicons

GitHub 아이콘(옥티콘)이 이제 오픈소스가 되었습니다.

![Octicons](https://og.github.com/octicons/octicons@1200x630.png)

[*GitHub 옥티콘에 대해 더 읽어보세요.*](https://octicons.github.com)

### GitHub Resources

| Title | Link |
| ----- | ---- |
| GitHub Explore | https://github.com/explore |
| GitHub Blog | https://github.com/blog |
| GitHub Help | https://help.github.com/ |
| GitHub Training | https://training.github.com/ |
| GitHub Developer | https://developer.github.com/ |
| GitHub Education (Free Micro Account and other stuff for students) | https://education.github.com/ |

#### GitHub Talks

| Title | Link |
| ----- | ---- |
| How GitHub Uses GitHub to Build GitHub | https://www.youtube.com/watch?v=qyz3jkOBbQY |
| Introduction to Git with Scott Chacon of GitHub | https://www.youtube.com/watch?v=ZDR433b0HJY |
| How GitHub No Longer Works | https://www.youtube.com/watch?v=gXD1ITW7iZI |
| Git and GitHub Secrets | https://www.youtube.com/watch?v=Foz9yvMkvlA |
| More Git and GitHub Secrets | https://www.youtube.com/watch?v=p50xsL-iVgU |

## Git

### Remove All Deleted Files from the Working Tree

`/bin/rm`을 사용해 대량의 파일을 지울 때, 하나씩 제거할 필요 없이 밑의 명령어를 사용해 작업 디렉터리와 인덱스에서 지울 수 있습니다.

```bash
$ git rm $(git ls-files -d)
```

예를 들어

```bash
$ git status
On branch master
Changes not staged for commit:
	deleted:    a
	deleted:    c

$ git rm $(git ls-files -d)
rm 'a'
rm 'c'

$ git status
On branch master
Changes to be committed:
	deleted:    a
	deleted:    c
```

### Previous Branch

Git에서 이전 브랜치로 돌아가는 건 이렇게 할 수 있습니다.

```bash
$ git checkout -
# Switched to branch 'master'

$ git checkout -
# Switched to branch 'next'

$ git checkout -
# Switched to branch 'master'
```

[*Git 브랜치에 대해 더 읽어 보세요.*](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)

### Stripspace

Git Stripspace는 이런 일을 합니다.

- 줄 끝의 공백을 제거
- 빈줄을 줄임
- 파일 끝에 빈 줄을 추가

커맨드를 실행 할 때 파일을 반드시 이런식으로 넘겨줘야 합니다.

```bash
$ git stripspace < README.md
```

[*Git `stripspace` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-stripspace)

### SSH keys

아래 주소를 방문하면 공개 ssh 키의 목록을 일반 텍스트 형식으로 볼 수 있습니다.

```
https://github.com/{user}.keys
```

예: [https://github.com/tiimgreen.keys](https://github.com/tiimgreen.keys)

[*공개 ssh 키 접근에 대해 더 읽어 보세요.*](https://changelog.com/github-exposes-public-ssh-keys-for-its-users/)

### Checking out Pull Requests

풀 리퀘스트는 GitHub 저장소에서 사용하는 특별한 브랜치로 여러 방법으로 로컬로
가져올 수 있습니다.

빠르게 `diff`나 `merge`를 하기 위해 특정 풀 리퀘스트를 임시로 `FETCH_HEAD`로
가져오려면 이렇게 합니다.

```bash
$ git fetch origin refs/pull/[PR-Number]/head
```

모든 풀 리퀘스트 브랜치를 refspec에 의한 로컬 리모트 브랜치로 받을 수도
있습니다.

```bash
$ git fetch origin '+refs/pull/*/head:refs/remotes/origin/pr/*'
```

밑의 줄들을 저장소의 `.git/config`에 추가하여, 리모트의 풀 리퀘스트를 자동으로
가져오게도 할 수 있습니다.

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

포크 기반의 풀 리퀘스트 기여를 위해, 풀 리퀘스트의 리모트 브랜치를 `checkout`해
로컬 브랜치를 만드는 것은 유용합니다.

```bash
$ git checkout pr/42 pr-42
```

여러 저장소를 다루어야 한다면, 전역 Git 설정에서 풀 리퀘스트를 받을(fetching) 수 있도록 설정 할 수도 있습니다.

```bash
git config --global --add remote.origin.fetch "+refs/pull/*/head:refs/remotes/origin/pr/*"
```

이렇게 하면 모든 저장소에서 짧은 명령어를 사용 할 수 있습니다.

```bash
git fetch origin
```

```bash
git checkout pr/42
```

[*풀 리퀘스트를 로컬로 체크아웃 하는 방법에 대해 더 읽어 보세요.*](https://help.github.com/articles/checking-out-pull-requests-locally)

### Empty Commits

`--allow-empty`를 추가하시면 코드의 변경 없이 커밋을 넣을 수 있습니다.

```bash
$ git commit -m "Big-ass commit" --allow-empty
```

있을 법한 사용법에는 이런 것들이 있습니다.

 - 한 뭉치의 일을 시작하기 전에 주석으로 사용
 - 코드와 관련없는 프로젝트 수정을 할때 주석으로 사용
 - 저장소를 사용하는 사람과의 대화
 - 저장소의 첫 커밋으로 사용 `git commit -m "Initial commit" --allow-empty`

### Styled Git Status

```bash
$ git status
```

![git status](http://i.imgur.com/qjPyvXb.png)

`-sb`를 추가하면

```bash
$ git status -sb
```

이렇게 바뀝니다.

![git status -sb](http://i.imgur.com/K0OY3nm.png)

[*Git `status` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-status)

### Styled Git Log

이 명령을 실행하면

```bash
$ git log --all --graph --pretty=format:'%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
```

이렇게 보입니다.

![git log --all --graph --pretty=format:'%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative](http://i.imgur.com/58eOtkW.png)

[Palesz](http://stackoverflow.com/users/88355/palesz) 님 고맙습니다.

NOTE: 이 명령을 알리아스(단축 명령)로 넣을 수 있습니다. [여기](#aliases)의 소개를 보세요.

[*Git `log` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-log)

### Git Query

Git 쿼리는 모든 이전 커밋 메시지에서 검색해 가장 최근의 쿼리에 맞는 커밋을 찾아줍니다.

```bash
$ git show :/query
```

`query`에는 검색하고 싶은 말을 (대소문자를 구분해) 넣으세요. 주어진 검색어가 있는 가장 마지막 커밋을 표시하고 변경된 라인을 보여줍니다.

```bash
$ git show :/typo
```

![git show :/query](http://i.imgur.com/icaGiNt.png)

*나오려면 `q`를 누르세요.*

### Git Grep

Git Grep은 패턴과 일치하는 줄의 목록을 반환합니다.

다음 명령을 실행해 보세요.

```bash
$ git grep aliases
```

*aliases* 문자열이 포함된 모든 파일을 보여줍니다.

![git grep aliases](http://i.imgur.com/DL2zpQ9.png)

*나오려면 `q`를 누르세요.*

여러 플래그를 이용해서 좀 더 복잡한 검색을 할 수 있습니다. 예를 들면,

 * `-e` 다음 파라미터는 패턴 (e.g. regex)
 * `--and`, `--or`, `--not`으로 여러 패턴을 조합

이렇게 사용할 수 있습니다.
```bash
 $ git grep -e pattern --and -e anotherpattern
```

[*Git `grep` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-grep)

### Merged Branches

```bash
$ git branch --merged
```

이 명령어는 현재 브랜치에 머지된 모든 브랜치의 목록을 보여줍니다.

거꾸로

```bash
$ git branch --no-merged
```

이 명령어는 현재 브랜치에 머지되지 않은 브랜치의 목록을 보여줍니다.

[*Git `branch` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-branch)

### Fixup and Autosquash

이전(HEAD의 한 개 이상 전의) 커밋에 잘못된 부분이 있다면, 예를 들어 `abcde`라면,
문제를 수정하고 밑의 커맨드를 입력해 고칠 수 있습니다.

```bash
$ git commit --fixup=abcde
$ git rebase abcde^ --autosquash -i
```
[*Git `commit` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-commit)
[*Git `rebase` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-rebase)

### Web Server for Browsing Local Repositories

Git `instaweb` 커맨드을 사용하면, 즉석에서 `gitweb` 안에서 작업중인 저장소를 둘러 볼
수 있습니다. 이 커맨드는 `gitweb`과 로컬 저장소를 브라우징 하기 위한 웹 서버를 설정하는 스크립트입니다.

```bash
$ git instaweb
```

Opens:

![Git instaweb](http://i.imgur.com/Dxekmqc.png)

[*Git `instaweb` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-instaweb)

### Git Configurations

`.gitconfig`는 모든 설정이 들어있는 파일입니다.

#### Aliases

알리아스는 커스텀 Git 명령어를 등록할 수 있는 헬퍼입니다. 예를 들어 `git a`로 `git add --all`를 실행하게 할 수 있습니다.

알리아스를 추가하려면 `~/.gitconfig`를 찾아 다음 포맷으로 입력하거나

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

커맨드 라인에서 다음 명령을 입력합니다.

```bash
$ git config --global alias.new_alias git_function
```

예를 들면

```bash
$ git config --global alias.cm commit
```

여러 함수를 알리아스하려면 따옴표를 이용하세요.

```bash
$ git config --global alias.ac 'add -A . && commit'
```

여기 몇 가지 유용한 알리아스가 있습니다.

| Alias | Current Command | What to Type |
| --- | --- | --- |
| `git cm` | `git commit` | `git config --global alias.cm commit` |
| `git co` | `git checkout` | `git config --global alias.co checkout` |
| `git ac` | `git add . -A` `git commit` | `git config --global alias.ac '!git add -A && git commit'` |
| `git st` | `git status -sb` | `git config --global alias.st 'status -sb'` |
| `git tags` | `git tag -l` | `git config --global alias.tags 'tag -l'` |
| `git branches` | `git branch -a` | `git config --global alias.branches 'branch -a'` |
| `git cleanup` | `git branch --merged \| grep -v '*' \| xargs git branch -d` | `git config --global alias.cleanup "!git branch --merged \| grep -v '*' \| xargs git branch -d"` |
| `git remotes` | `git remote -v` | `git config --global alias.remotes 'remote -v'` |
| `git lg` | `git log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --` | `git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --"` |

*일부 알리아스는 [@mathiasbynens](https://github.com/mathiasbynens) 님의 dotfiles에서 가져왔습니다.(https://github.com/mathiasbynens/dotfiles/blob/master/.gitconfig)*

#### Auto-correct

현재 `git comit`를 치면 이런 결과를 보실 수 있습니다.

```bash
$ git comit -m "Message"
# git: 'comit' is not a git command. See 'git --help'.

# Did you mean this?
#   commit
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

#### Color

Git 커맨드 라인에 색을 넣으려면 이렇게 하세요.

```bash
$ git config --global color.ui 1
```

[*Git `config` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-config)

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
| Git for Computer Scientists | http://eagain.net/articles/git-for-computer-scientists/ |
| Git Magic | http://www-cs-students.stanford.edu/~blynn/gitmagic/ |
| GitHub Training Kit | https://training.github.com/kit/ |
| Git Visualization Playground | http://onlywei.github.io/explain-git-with-d3/#freeplay |
| Learn Git Branching | http://pcottle.github.io/learnGitBranching/ |
| A collection of useful .gitignore templates | https://github.com/github/gitignore |

#### Git Books

| Title | Link |
| ----- | ---- |
| Pragmatic Version Control Using Git | http://www.pragprog.com/titles/tsgit/pragmatic-version-control-using-git |
| Pro Git | http://git-scm.com/book |
| Git Internals PluralSight | https://github.com/pluralsight/git-internals-pdf |
| Git in the Trenches | http://cbx33.github.com/gitt/ |
| Version Control with Git | http://www.amazon.com/Version-Control-Git-collaborative-development/dp/1449316387 |
| Pragmatic Guide to Git | http://www.pragprog.com/titles/pg_git/pragmatic-guide-to-git |
| Git: Version Control for Everyone | http://www.packtpub.com/git-version-control-for-everyone/book |

#### Git Videos

| Title | Link |
| ----- | ---- |
| Linus Torvalds on Git | https://www.youtube.com/watch?v=4XpnKHJAok8 |
| Introduction to Git with Scott Chacon | https://www.youtube.com/watch?v=ZDR433b0HJY |
| Git From the Bits Up | https://www.youtube.com/watch?v=MYP56QJpDr4 |
| Graphs, Hashes, and Compression, Oh My! | https://www.youtube.com/watch?v=ig5E8CcdM9g |
| GitHub Training & Guides | https://www.youtube.com/watch?list=PLg7s6cbtAD15G8lNyoaYDuKZSKyJrgwB-&v=FyfwLX4HAxM |

#### Git Articles

| Title | Link |
| ----- | ---- |
| GitHub Flow  | http://scottchacon.com/2011/08/31/github-flow.html |
