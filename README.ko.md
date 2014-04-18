# 깃허브 치트 시트

A collection of cool hidden and not so hidden features of Git and GitHub. This cheat sheet was inspired by [Zach Holman](https://github.com/holman)'s [Git and GitHub Secrets](http://www.confreaks.com/videos/1229-aloharuby2012-git-and-github-secrets) talk at Aloha Ruby Conference 2012 ([slides](https://speakerdeck.com/holman/git-and-github-secrets)) and his [More Git and GitHub Secrets](https://vimeo.com/72955426) talk at WDCNZ 2013 ([slides](https://speakerdeck.com/holman/more-git-and-github-secrets)).

# 목록

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

`?w=1`를 diff URL에 추가하면 변경된 코드만 볼 수 있도록, 공백만 바뀐 수정을 제거할 수 있습니다.

![Diff without whitespace](https://camo.githubusercontent.com/797184940defadec00393e6559b835358a863eeb/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f776869746573706163652e706e67)

[*깃허브의 비밀을 더 읽어 보세요.*](https://github.com/blog/967-github-secrets)

### Commit History by Author

특정 커미터가 한 모든 커밋을 보고 싶다면 URL에 `?author=username`를 추가하세요.

```
https://github.com/rails/rails/commits/master?author=dhh
```

![DHH commit history](http://i.imgur.com/mDWwuaY.png)

[*커밋 뷰간의 차이에 대해 더 읽어보세요.*](https://help.github.com/articles/differences-between-commit-views)

### Cloning a Repository

저장소를 클론할 때, 맨 뒤의 `.git`은 생략할 수 있습니다.

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

[*깃 `clone` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-clone)

### Comparing Branches

깃허브에서 브랜치 비교를 하시려면, URL을 이런 식으로 바꾸세요.

```
https://github.com/user/repo/compare/{range}
```

`{range}`는 `master...4-1-stable`식으로 적습니다.

예를 들어

```
https://github.com/rails/rails/compare/master...4-1-stable
```

![Rails branch compare example](http://i.imgur.com/0Z52X5Y.png)

`{range}` 는 이렇게 적을 수도 있습니다.

```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```

*날짜는 `YYYY-DD-MM`형식으로 적습니다*

![Another compare example](http://i.imgur.com/5dtzESz.png)

이렇게 하면 특정 날짜나 한 시간 전의 마스터 브랜치의 차이를 확인할 수 있습니다.

[*시간으로 커밋을 비교하는 법에 대해 더 읽어 보세요.*](https://help.github.com/articles/comparing-commits-across-time)

### Compare branches across forked repositories

포크된 저장소간의 브랜치를 비교하려면 URL을 이렇게 변경하세요.

```
https://github.com/user/repo/compare/{foreign-user}:{branch}...{own-branch}
```

예를 들면

```
https://github.com/rails/rails/compare/byroot:idempotent-counter-caches...master
```

![Forked branch compare](http://i.imgur.com/Q1W6qcB.png)

### Gists

[Gists](https://gist.github.com/)는 본격적인 저장소를 만들지 않고, 작은 코드 조각과 일할 수 있는 쉬운 방법입니다.

![Gist](http://i.imgur.com/VkKI1LC.png?1)

[이렇게](https://gist.github.com/tiimgreen/10545817.pibb) Gist URL뒤에 `.pibb`를 넣으면 다른 사이트에 넣을수 있는 *HTML 온리* 버전을 만들 수 있습니다.

Gists는 본격적인 저장소처럼 취급할 수 있고 클론도 됩니다.

```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/dULZXXo.png)

[*gist를 만드는 법에 대해 더 읽어보세요.*](https://help.github.com/articles/creating-gists)

### Git.io

[Git.io](http://git.io)는 깃허브를 위한 간단한 URL 단축기입니다.

![Git.io](http://i.imgur.com/6JUfbcG.png?1)

순수 HTTP에서 Curl으로 사용하실 수도 있습니다.

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
 - `w`를 누르면 브렌치 선택 페이지로 이동합니다.
 - `s`를 누르면 커맨드 창으로 이동합니다.
 - `l`를 누르면 있는 이슈의 라벨을 수정할 수 있습니다.
 - __파일을 보고 있을 때__ (예를 들어 `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`) `y`를 누르면 URL을 지금 보고 있는 페이지를 사실상 고정하도록 합니다. 코드가 바뀐다고 해도 이번에 본 내용을 다시 볼 수 있습니다.

지금 페이지에서 쓸 수 있는 모든 단축키를 보시려면 `?`를 누르세요.

![Keyboard shortcuts](http://i.imgur.com/y5ZfNEm.png)

[*커맨드 바의 사용법을 더 읽어 보세요.*](https://help.github.com/articles/using-the-command-bar)

### Line Highlighting in Repos

코드 파일 URL의 끝에 `#L52`를 추가하거나 줄 번호를 클릭하면 그 줄 번호를 하이라이트합니다.

`#L53-L60`처럼 범위지정도 가능합니다. 범위를 지정하려면 `shift`키를 누른 채 두 라인을 클릭하면 됩니다.

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

### Closing Issues with Commits

어떤 커밋이 이슈를 고쳤다면, `fix/fixes/fixed`, `close/closes/closed`, `resolve/resolves/resolved`를 키워드로 해당 이슈가 마스터 브랜치에 커밋 될 때 닫을 수 있습니다.

```bash
$ git commit -m "Fix cock up, fixes #12"
```

이렇게 하면 이슈를 닫고 클로징 커맨트로 참조하게 합니다.

![Closing Repo](http://i.imgur.com/URXFprQ.png)

[*커밋 메세지로 이슈 닫기에 대해 더 읽어 보세요.*](https://help.github.com/articles/closing-issues-via-commit-messages)

### Cross-Link Issues

같은 저장소의 다른 이슈를 링크하기 원한다면, `#`뒤에 이슈 번호만 입력하시면 자동으로 링크됩니다.

다른 저장소의 이슈를 링크하고 싶다면 `사람_이름/저장소_이름#이슈_번호`로 할 수 있습니다. (예 `tiimgreen/toc#12`)

![Cross-Link Issues](https://camo.githubusercontent.com/447e39ab8d96b553cadc8d31799100190df230a8/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f7265666572656e6365732e706e67)

### CI Status on Pull Requests

정확히 설정되었다면, 풀 리퀘스트를 받거나 풀 리퀘스트에 새로운 커밋을 할 때 마다, [Travis CI](https://travis-ci.org/)가 풀 리퀘스트를 빌드 할 것입니다. [Travis CI 시작하기](http://docs.travis-ci.com/user/getting-started/)를 좀 더 읽어보세요.

[![Travic CI status](https://cloud.githubusercontent.com/assets/1687642/2700187/3a88838c-c410-11e3-9a46-e65e2a0458cd.png)](https://github.com/octokit/octokit.rb/pull/452)

[*커밋 상태 API에 대해 좀 더 읽어보세요.*](https://github.com/blog/1227-commit-status-api)

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

깃허브는 [Linguist](https://github.com/github/linguist)를 사용해 언어를 감지하고 신텍스를 하이라이트합니다. [언어 YAML 파일](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)을 정독하시면 어떤 키워드가 유효한지 확인하실 수 있습니다.

[*깃허브 Flavored 마크다운에 대해 더 읽어 보세요.*](https://help.github.com/articles/github-flavored-markdown)

### Emojis

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

깃허브에서 사용 가능한 에모지의 전 목록은 [emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com/) 나 [scotch-io/All-Github-Emoji-Icons](https://github.com/scotch-io/All-Github-Emoji-Icons)에서 확인하실 수 있습니다.

깃허브에서 많이 사용하는 에모지 탑 5위는 이렇습니다.

1. :shipit: - `:shipit:`
2. :sparkles: - `:sparkles:`
3. :-1: - `:-1:`
4. :+1: - `:+1:`
5. :clap: - `:clap:`

### Images/GIFs

커맨트나 README등등에 이미지와 GIF를 넣을 수 있습니다.

```
![Alt Text](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)
```

![Peter don't care](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)

모든 이미지는 GitHub에서 케쉬합니다. 그래서 호스트가 죽어도 이미지는 여전히 남습니다.

#### Embedding Images in GitHub Wiki

이미지를 위키 페이지ㅇ넣는 방법은 여럿 있습니다. 위에 보이는 일반 마크다운 문법도 있지만, 이미지에 높이와 넓이를 지정할 수 있는 문법도 있습니다.

```markdown
[[ http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif | height = 100px ]]
```

이렇게 보입니다.

![Just a screenshot](http://i.imgur.com/J5bMf7S.png)

### Quick Quoting

스레드에 답글들 때 전에 누가 말한 어떤 내용을 인용하고 싶다면, 텍스트를 하이라이트하고 `r`을 누르세요. 이렇게 하면 내용을 텍스트 박스에 인용 포맷으로 복사해 줍니다.

![Quick Quote](https://f.cloud.github.com/assets/296432/124483/b0fa6204-6ef0-11e2-83c3-256c37fa7abc.gif)

[*빠른 인용에 대해 더 읽어 보세요.*](https://github.com/blog/1399-quick-quotes)

### Quick Licensing

저장소를 만들 때, 깃허브는 만들어진 저작권을 추가할 수 있는 옵션을 제공합니다.

![License](http://i.imgur.com/Chqj4Fg.png)

이미 있는 저장소에도 웹 인터페이스에서 새 파일을 만들어 추가할 수 있습니다.
이름에 `LICENSE`를 입력하면 옵션으로 템플릿을 사용할 수 있습니다.

![License](http://i.imgur.com/fTjQict.png)

`.gitignore`에도 똑같이 적용됩니다.

[*오픈 소스 저작권에 대해 더 읽어 보세요.*](https://help.github.com/articles/open-source-licensing)

### Task Lists

이슈와 풀 리퀘스트에서 밑의 문법으로 체크박스를 넣을 수 있습니다.(스페이스에 주의하세요.)

```
- [ ] Be awesome
- [ ] Do stuff
- [ ] Sleep
```

![Task List](http://i.imgur.com/k2qZi56.png)

체크박스가 클릭 되면, 순수 마크다운에서 갱신이 이루어집니다.

```
- [x] Be awesome
- [x] Do stuff
- [ ] Sleep
```

[*테스크 리스트에 대해 더 읽어 보세요.*](https://github.com/blog/1375%0A-task-lists-in-gfm-issues-pulls-comments)

### Relative Links

상대 경로 링크는 마크다운 파일이 내부 건탠츠로 링크될 때 추천합니다.

```markdown
[Link to a header](#awesome-section)

[Link to a file](docs/readme)
```

절대 경로 링크는 URL이 변경 될 때 마다 변경해야 합니다. (예를 들어 저장소 이름 변경, 유저이름 변경, 프로젝트 포크)
상대 경로 링크를 사용하면 문서를 쉽게 스스로 독립적으로 만들 수 있습니다.

[*상대 경로 링크에 대해 더 읽어 보세요.*](https://help.github.com/articles/relative-links-in-readmes)

### Metadata and Plugin Support for GitHub Pages

지킬로 작성된 페이지와 포스트에서, 저장소 정보는 예를 들어 `{{ site.github.project_title }}`처럼 `site.github` 이름 공간으로 사용하고 표시할 수 있습니다.

Jemoji와 jekyll-mentions플러그인은 GitHub.com에서 처럼 [emoji](#emojis)와 [@mentions](https://github.com/blog/821)을 지킬 포스트와 페이지에서 사용하게 합니다.

[*저장소 메타 데이타와 깃허브 페이지의 플러그인 지원에 대해 더 읽어 보세요.*](https://github.com/blog/1797-repository-metadata-and-plugin-support-for-github-pages)

### Diffs

#### Rendered Prose Diffs

산문(prose) 파일이 있는 커밋과 풀 리퀘스트는 *source*와 *rendered* 뷰 기능을 사용할 수 있습니다.

![Source / Rendered view](https://github-images.s3.amazonaws.com/help/repository/rendered_prose_diff.png)

"rendered" 버튼을 클릭하시면 렌더된 문서에서 변경을 확인하실 수 있습니다. 렌더된 산문(prose) 뷰는 문장을 추가, 삭제, 변경했을때 유용합니다.

![Rendered Prose Diffs](https://f.cloud.github.com/assets/17715/2003056/3997edb4-862b-11e3-90be-5e9586edecd7.png)

[*렌더된 산문(prose) diff에 대해 더 읽어 보세요.*](https://github.com/blog/1784-rendered-prose-diffs)

#### Diffable Maps

지오데이타가 포함된 커밋이나 풀 리퀘스트를 볼 때마다 깃허브는 무엇이 변경 되었는지 시각적으로 보여줍니다.

[![Diffable Maps](https://f.cloud.github.com/assets/282759/2090660/63f2e45a-8e97-11e3-9d8b-d4c8078b004e.gif)](https://github.com/benbalter/congressional-districts/commit/2233c76ca5bb059582d796f053775d8859198ec5)

[*diff 가능한 맵에 대해 더 읽어 보세요.*](https://github.com/blog/1772-diffable-more-customizable-maps)

#### Expanding Context in Diffs

diff의 닫아둔 곳의 *펼침* 버튼을 클릭하면, 문맥을 더 볼 수 있습니다. 전채 파일을 표시할때까지 계속 *펼칠* 수 있으며, 깃허브에서 diff가 표시되는 장소라면 어디서든 사용가능합니다.

![Expanding Context in Diffs](https://f.cloud.github.com/assets/22635/1610539/863c1f64-5584-11e3-82bf-151b406a272f.gif)

[*diff에서의 문맥 확장에 대해 더 읽어 보세요.*](https://github.com/blog/1705-expanding-context-in-diffs)

#### Diff or Patch of Pull Request

URL뒤에 `.diff` 나 `.patch`를 붙이면 풀 리퀘스트의 diff를 얻을 수 있습니다.
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

### Hub - Git Wrapper

[Hub](https://github.com/github/hub)는 깃허브를 좀 더 쉽게 사용할 수 있도록 추가 기능 및 명령을 제공하는 커맨드 라인 깃 래퍼입니다.

이렇게 할 수 있습니다.

```bash
$ hub clone tiimgreen/toc
```

[*Hub가 제공하는 더 멋진 기능들을 확인해 보세요.*](https://github.com/github/hub#commands)

### Decreasing Contributor Friction

사람들이 사용하고 기여할 수 있는 프로젝트를 만드려면, 가장 기본적인 질문에 대답할 수 있어야합니다. 이 프로젝트는 무엇입니까? 어떻게 사용합니까? 어디까지 허용됩니까? 어떻게 기여합니까? 어떻게 개발하고 실행해야 합니까? 어떻게 새로운 기능이 이전 기능을 손상되지 않았는지 확인해야 합니까?

[Friction](https://github.com/rafalchmiel/friction)은 이러한 일반적인 [질문들의 답](https://github.com/rafalchmiel/friction/wiki)이 프로젝트 안에 있는지 확인하는 커맨드 라인 스크립트 입니다. 다음은 샘플 출력 입니다.

[![Friction output](http://i.imgur.com/4EgpWo4.png)](https://github.com/rafalchmiel/friction)

*Friction 은 MRI 2.1.0, MRI 2.0.0, MRI 1.9.3을 지원합니다.*

### Contributing Guidelines

저장소의 제일 위에 `CONTRIBUTING` 파일을 넣어두면 기여자가 이슈를 만들거나 풀 리퀘스트를 만들 때 링크로 보여줍니다.

![Contributing Guidelines](https://camo.githubusercontent.com/71995d6b0e620a9ef1ded00a04498241c69dd1bf/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f736b697463682f6973737565732d32303132303931332d3136323533392e6a7067)

[*기여하기에 대해 더 읽어 보세요.*](https://github.com/blog/1184-contributing-guidelines)

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

[*깃 브랜치에 대해 더 읽어 보세요.*](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)

### Stripspace

깃 Stripspace는 이런 일을 합니다.

- 줄 끝의 공백을 제거
- 빈줄을 줄임
- 파일 끝에 빈 줄을 추가

커맨드를 실행 할 때 파일을 반드시 이런식으로 넘겨줘야 합니다.

```bash
$ git stripspace < README.md
```

[*깃 `stripspace` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-stripspace)

### Checking out Pull Requests

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

[*풀 리퀘스트를 로컬로 체크아웃 하는 방법에 대해 더 읽어 보세요.*](https://help.github.com/articles/checking-out-pull-requests-locally)

### Empty Commits :trollface:

`--allow-empty`를 추가하시면 코드의 변경 없이 커밋을 넣을 수 있습니다.

```bash
$ git commit -m "Big-ass commit" --allow-empty
```

있을 법한 사용법에는 이런 것들이 있습니다.

 - 한 뭉치의 일을 시작하기 전에 주석으로 사용
 - 코드와 관련없는 프로젝트 수정을 할때 주석으로 사용
 - 저장소를 사용하는 사람과의 대화

### Styled Git Status

```bash
$ git status
```

![git status](http://i.imgur.com/o3PEHAA.png)

이렇게 바뀝니다.

```bash
$ git status -sb
```

![git status -sb](http://i.imgur.com/xNI1bT0.png)

[*깃 `status` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-status)

### Styled Git Log

```bash
$ git log --all --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
```

![git log --all --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative](http://i.imgur.com/R2z8l7c.png)

[Palesz](http://stackoverflow.com/users/88355/palesz)님 고맙습니다.

NOTE: 이 명령을 알리아스 (단축 명령)으로 넣을 수 있습니다. [여기](#aliases)의 소개를 보세요.

[*깃 `log` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-log)

### Git Query

깃 쿼리는 모든 이전 커밋 메시지에서 검색해 가장 최근의 쿼리에 맞는 커밋을 찾아줍니다.

```bash
$ git show :/query
```

`query`에는 검색하고 싶은 말을 넣으세요. 주어진 검색어가 있는 가장 마지막 커밋을 표시하고 변경된 라인을 보여줍니다.

```bash
$ git show :/typo
```

![git show :/query](http://i.imgur.com/icaGiNt.png)

NOTE: 나오려면 `q`를 누르세요.

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

[*깃 `branch` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-branch)

### Web Server for Browsing Local Repositories

깃 `instaweb` 커맨드을 사용하면, 즉석에서 `gitweb`안에서 작업중인 저장소를 둘러 볼
수 있습니다. 이 커맨드는 `gitweb`과 로컬 저장소를 브라우징 하기 위한 웹 서버를 설정하는 스크립트입니다.

```bash
$ git instaweb
```

Opens:

![Git instaweb](http://i.imgur.com/Dxekmqc.png)

[*깃 `instaweb` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-instaweb)

### Git Configurations

`.gitconfig`는 모든 설정이 들어있는 파일입니다.

#### Aliases

알리아스는 커스텀 깃 명령어를 등록할 수 있는 핼퍼입니다. 예를 들어 `git a`로 `git add --all`를 실행하게 할 수 있습니다.

알리아스를 추가하려면 `~/.gitconfig`를 찾아 다음 포멧으로 입력하거나

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
| `git tags` | `git tag -l` | `git config --global alias.tags 'tag -l'` |
| `git branches` | `git branch -a` | `git config --global alias.branches 'branch -a'` |
| `git remotes` | `git remote -v` | `git config --global alias.remotes 'remote -v'` |

#### Auto-correct

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

#### Color

깃 커맨드 라인에 색을 넣으려면 이렇게 하세요.

```bash
$ git config --global color.ui 1
```

[*깃 `config` 커맨드에 대해 더 읽어 보세요.*](http://git-scm.com/docs/git-config)

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
