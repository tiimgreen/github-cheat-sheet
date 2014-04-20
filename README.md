# GitHub Cheat Sheet（日本語訳）

## 日本語翻訳に関するノート 
GitやGtihubの便利な使い方をまとめたられた[Github cheat sheet](https://github.com/tiimgreen/github-cheat-sheet)の日本語訳です。もっと分かりやすくしたいので翻訳に関するダメ出しは歓迎です。

- 元のレポジトリ
 - [tiimgreen/github-cheat-sheet](https://github.com/tiimgreen/github-cheat-sheet)
- 日本語翻訳レポジトリ
 - [sota0805/github-cheat-sheet](https://github.com/sota0805/github-cheat-sheet/tree/feature-japanese)

## 概要
このチートシートは、[Zach Holman](https://github.com/holman)さんがAloha Ruby Conference 2012 ([slides](https://speakerdeck.com/holman/git-and-github-secrets))で発表された[Git and GitHub Secrets](http://www.confreaks.com/videos/1229-aloharuby2012-git-and-github-secrets) と WDCNZ 2013 ([slides](https://speakerdeck.com/holman/more-git-and-github-secrets))で発表された彼の[More Git and GitHub Secrets](https://vimeo.com/72955426)に触発されまとめました。


## 目次
 - [GitHub](#github)
  - [空行を無視](#ignore-whitespace)
  - [ユーザー別のコミットヒストリー表示](#commit-history-by-author)
  - [レポジトリのクローン](#cloning-a-repository)
  - [ブランチの比較](#comparing-branches)
  - [フォークされたブランチとの比較](#compare-branches-across-forked-repositories)
  - [Gists](#gists)
  - [Git.io](#gitio)
  - [ショットカットキー](#keyboard-shortcuts)
  - [レポジトリ内のコードをハイライト](#line-highlighting-in-repositories)
  - [コミットメッセージによるissueのクローズ](#closing-issues-via-commit-messages)
  - [issue同士のリンク](#cross-link-issues)
  - [プルリクエストにCIステータスを表示](#ci-status-on-pull-requests)
  - [マークダウンファイル内でのコードのハイライト](#syntax-highlighting-in-markdown-files)
  - [絵文字](#絵文字)
  - [画像（GIF）](#imagesgifs)
    - [Github Wikiに画像を埋め込む](#embedding-images-in-github-wiki)
  - [素早く引用（Quick Quoting）](#quick-quoting)
  - [ライセンスを簡単に表示（Quick Licensing）](#quick-licensing)
  - [タスクリスト](#task-lists)
  - [相対リンク](#relative-links)
  - [Metadata and Plugin Support for GitHub Pages](#metadata-and-plugin-support-for-github-pages)
  - [Viewing YAML Metadata in your Documents](#viewing-yaml-metadata-in-your-documents)
  - [Rendering Tabular Data](#rendering-tabular-data)
  - [差分](#diffs)
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
  - [Git 設定](#git-configurations)
    - [エイリアス](#aliases)
    - [コマンドの自動補完](#auto-correct)
    - [色](#color)
  - [Git リソース](#git-resources)
    - [Git 本](#git-books)

## GitHub
### 空行を無視
`?w=1`をdiff URLにつけることによって空白行が削除されるので、変わったところだけを見ることができます

![Diff without whitespace](https://camo.githubusercontent.com/797184940defadec00393e6559b835358a863eeb/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f776869746573706163652e706e67)

[*より詳しいGtihubの秘密についてはこちらを参照してください。*](https://github.com/blog/967-github-secrets)

### ユーザー別のコミットヒストリー表示
URLに`?author=username`を加えることでユーザーごとのコミットを見ることができます。

```
https://github.com/rails/rails/commits/master?author=dhh
```

![DHH commit history](http://i.imgur.com/mDWwuaY.png)

[*commit viewに関してのより詳しい内容はこちらを参照してください。*](https://help.github.com/articles/differences-between-commit-views)

### レポジトリのクローン
レポジトリのクローンは以下のコマンドを使用することでできます

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

[*Gitの `clone` コマンドに関してのより詳しい内容はこちらを参照してください。*](http://git-scm.com/docs/git-clone)

### ブランチの比較
ブランチの比較をGtihubを使ってやるためには以下のようにURLを変更します：

```
https://github.com/user/repo/compare/{範囲}
```

 範囲の指定方法、`{範囲} = master...4-1-stable`

例：

```
https://github.com/rails/rails/compare/master...4-1-stable
```

![Rails branch compare example](http://i.imgur.com/0Z52X5Y.png)

`{範囲}` は以下のようにも指定することもできます：

```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```

*日付の指定は `YYYY-DD-MM` のようにします*

![Another compare example](http://i.imgur.com/5dtzESz.png)

日付を指定るすることによって、何日前のものや特定のmasterブランチと比較をすることができます

[*時間によってcommitメッセージを比較することに関してのより詳しい内容はこちらを参照してください*](https://help.github.com/articles/comparing-commits-across-time)

<!-- TODO Consider it again later -->
<!-- ### Compare Branches across Forked Repositories -->

### forkされたbranchとの比較
Githubを使ってforkされたbranchとの比較をする際には以下のようにURLを変更します：

```
https://github.com/user/repo/compare/{foreign-user}:{branch}...{own-branch}
```

例：

```
https://github.com/rails/rails/compare/byroot:master...master
```

![Forked branch compare](http://i.imgur.com/Q1W6qcB.png)

### Gists
[Gists](https://gist.github.com/) はわざわざrepositroryを作るまでもないちょっとしたコードを扱う際に便利です

![Gist](http://i.imgur.com/VkKI1LC.png?1)

Add `.pibb` to the end of any Gist URL ([like this](https://gist.github.com/tiimgreen/10545817.pibb)) in order to get the *HTML only* version suitable for embedding in any other site.

<!-- TODO: Consider it again later -->
<!-- Gists can be treated as a full repository so they can be cloned like any other: -->
Gistsはレポジトリと同じようにクローンをすることができます：

```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/dULZXXo.png)

[*Gistsに関してのより詳しい内容はこちらを参照してください*](https://help.github.com/articles/creating-gists)

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

[*Git.ioに関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/985-git-io-github-url-shortener)

### ショットカットキー
ショットカットキーを使うことによって簡単に操作することができます

 - `t` を押すとファイル一覧を表示します
 - `w` を押すとブランチ一覧を表示します
 - `s` を押すと検索部分にフォカースします
 - `l` を押すと既存のissueでラベルを編集できます
 - `y` を押すと例えば、(e.g. `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`)をそのURLを固定します。なのでもしコードを変更しても、今見ているコードはそのままみることができます。

<!-- 
 - Pressing `t` will bring up a file explorer.
 - Pressing `w` will bring up the branch selector.
 - Pressing `s` will select the Command Bar.
 - Pressing `l` will edit labels on existing Issues.
 - Pressing `y` **when looking at a file** (e.g. `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`) will change your URL to one which, in effect, freezes the page you are looking at. If this code changes, you will still be able to see what you saw at that current time.
-->


現在のページで使えるショートカットキーを知りたい場合はその画面で `?` を押してください：

![Keyboard shortcuts](http://i.imgur.com/y5ZfNEm.png)

[*ショートカットキーに関してのより詳しい内容はこちらを参照してください*](https://help.github.com/articles/using-the-command-bar)

### レポジトリ内のコードをハイライト
Either adding `#L52` to the end of a code file URL or simply clicking the line number will highlight that line number.

It also works with ranges, e.g. `#L53-L60`, to select ranges, hold `shift` and click two lines:

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

### コミットメッセージによるissueのクローズ

もしある issue を解決した際に、`fix/fixes/fixed`
、`close/closes/closed`、`resolve/resolves/resolved`とそのissueの番号などのキワードをcommitメッセージがmasterブランチにコミットされることでそのissueを閉じることができます

<!-- TODO: Consider it again later -->
<!--
If a particular commit fixes an issue, any of the keywords `fix/fixes/fixed`, `close/closes/closed` or `resolve/resolves/resolved`, followed by the issue number, will close the issue once it is committed to the master branch.
-->

```bash
$ git commit -m "Fix cock up, fixes #12"
```

<!-- This closes the issue and references the closing commit. -->


![Closing Repo](http://i.imgur.com/URXFprQ.png)

[*Commitメッセージによる既存のissue閉じ方に関してのより詳しい内容はこちらを参照してください*](https://help.github.com/articles/closing-issues-via-commit-messages)

### issue同士のリンク
同じレポジトリ内のissueに他のissueを紐付けたい場合には、`#`でissueの番号をつけると自動的にリンクを張ってくれます
If you want to link to another issue in the same repository, simple type hash `#` then the issue number, it will be auto-linked.

別のレポジトリのissueと紐付けたい場合には `user_name/repo_name#ISSUE_NUMBER` 例えば `tiimgreen/toc#12` とします

![Cross-Link Issues](https://camo.githubusercontent.com/447e39ab8d96b553cadc8d31799100190df230a8/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f7265666572656e6365732e706e67)

### Pull RequestにCIステータスを表示
プルリクエストを受け取った際に毎回、[Travis CI](https://travis-ci.org/) が毎回のコミットメッセージの際にテストを通すようにそのプルリクエストに対してテストをします。その方法についてはTravis CIの[get started with Travis CI](http://docs.travis-ci.com/user/getting-started/).を参照してください。

<!-- 
If set up correctly, every time you receive a Pull Request, [Travis CI](https://travis-ci.org/) will build that Pull Request just like it would every time you make a new commit. Read more about how to [get started with Travis CI](http://docs.travis-ci.com/user/getting-started/).
-->

[![Travic CI status](https://cloud.githubusercontent.com/assets/1687642/2700187/3a88838c-c410-11e3-9a46-e65e2a0458cd.png)](https://github.com/octokit/octokit.rb/pull/452)

[*commit statusのAPIに関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1227-commit-status-api)

### マークダウンファイル内でのコードのハイライト
例えば、Rubyのコードをマークダウンのファイルでハイライトする場合には以下のようにします：

    ```ruby
    require 'tabbit'
    table = Tabbit.new('Name', 'Email')
    table.add_row('Tim Green', 'tiimgreen@gmail.com')
    puts table.to_s
    ```

すると以下のようになります：

```ruby
require 'tabbit'
table = Tabbit.new('Name', 'Email')
table.add_row('Tim Green', 'tiimgreen@gmail.com')
puts table.to_s
```

Githubはコードの判定とそのシンタックスハイライトをするために [Linguist](https://github.com/github/linguist) を使用しています。どのキーワードが使えるかは [languages YAML file](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml) で見ることができます。

<!-- 
GitHub uses [Linguist](https://github.com/github/linguist) to perform language detection and syntax highlighting. You can find out which keywords are valid by perusing the [languages YAML file](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml).
-->

[*Read more about GitHub Flavored Markdown.*](https://help.github.com/articles/github-flavored-markdown)

### 絵文字
絵文字を、プルリクエスト、issues、commitメッセージ、マークダウンファイルなどで使うことができます `:絵文字の名前:`：

例：

```
:smile:
```

すると以下のような絵文字が表示されます：

:smile:

Githubで使える絵文字のリストは [emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com/) か [scotch-io/All-Github-Emoji-Icons](https://github.com/scotch-io/All-Github-Emoji-Icons)で見ることができます。

ちなみにGithubでよく使われる絵文字５つはこれです：

1. :shipit: - `:shipit:`
2. :sparkles: - `:sparkles:`
3. :-1: - `:-1:`
4. :+1: - `:+1:`
5. :clap: - `:clap:`

### 画像（GIF）
画像やGIFをcommnetsやREADMEファイルなどに使うことができます：

```
![Alt Text](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)
```

![Peter don't care](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)

すべての画像はGithubでキャッシュされます。なので画像のホスト先が落ちても画像は消えません

#### Github Wikiに画像を埋め込む

Wikiページに画像を埋め込む方法はいくつかあります。主な方法としては以下のような基本的なマークダウンの記法があります。画像の幅や高さを指定する方法があります。

<!--
There are multiple ways of embedding images in Wiki pages. There's the standard Markdown syntax (shown above). But there's also a syntax that allows things like specifying the height or width of the image:
-->

```markdown
[[ http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif | height = 100px ]]
```

すると以下のようになります：

![Just a screenshot](http://i.imgur.com/J5bMf7S.png)

### 素早く引用（Quick Quoting）
コメントをする際に前のコメントを引用したいとき、まずそのテキストを選択して `r` を押すとその部分があなたのコメント部分に `>` がついた形で反映されます

![Quick Quote](https://f.cloud.github.com/assets/296432/124483/b0fa6204-6ef0-11e2-83c3-256c37fa7abc.gif)

[*素早く引用（quick quoting）に関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1399-quick-quotes)

### ライセンスを簡単に表示（Quick Licensing）
レポジトリを作成した際にGithubが簡単にライセンスを表示できる選択肢があります：
<!-- When creating a repository GitHub gives you the options of adding in a pre-made license: -->

![License](http://i.imgur.com/Chqj4Fg.png)

もちろん既存のレポジトリに対してライセンスを作成することができます。ファイル名に `LICENSE` と入力するとライセンスの選択肢が表示されます：

<!-- 
You can also add them to existing repositories by creating a new file through the web interface. When the name `LICENSE` is typed in you will get an option to use a template:
-->

![License](http://i.imgur.com/fTjQict.png)

`.gitigonre`でも同様のことができます

[*オープンソースライセンスに関してのより詳しい内容はこちらを参照してください*](https://help.github.com/articles/open-source-licensing)

### タスクリスト
issueやプルリクエストの中に以下のような方法で書くとチェックボックスを追加することができます：

<!-- TODO Consider it againg later -->
<!--
In Issues and Pull requests check boxes can be added with the following syntax (notice the space):
-->

```
- [ ] Be awesome
- [ ] Do stuff
- [ ] Sleep
```

![Task List](http://i.imgur.com/k2qZi56.png)

リストをクリックすると、自動的にマークダウンにも反映されます：

```
- [x] Be awesome
- [x] Do stuff
- [ ] Sleep
```

[*タスクリストに関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1375%0A-task-lists-in-gfm-issues-pulls-comments)

### 相対リンク
マークダウンで相対リンクの使用は推奨されています
<!--
Relative links are recommended in your Markdown files when linking to internal content.
-->

```markdown
[Link to a header](#awesome-section)
[Link to a file](docs/readme)
```

絶対リンクはレポジトリ名やユーザー名が、フォーク先などが変更された際に必ずそれを変更しなければなりません。なので相対リンクを使うことによってドキュメントの保守性を高めることができます
<!-- 
Absolute links have to be updated whenever the URL changes (e.g. repository renamed, username changed, project forked). Using relative links makes your documentation easily stand on its own.
--> 

[*Githubでの相対リンクに関してのより詳しい内容はこちらを参照してください*](https://help.github.com/articles/relative-links-in-readmes)


### Githubページで使えるメタデータやプラグイン
Jekyllのpagesとpostsにレポジトリ情報を`site.github`で表示することができます。例えば、 `{{ site.github.project_title }}`のように使います。

<!-- 
Within Jekyll pages and posts, repository information is available within the `site.github` namespace, and can be displayed, for example, using `{{ site.github.project_title }}`.
-->

Jemojiとjekyll-mentionプラグインで[emoji](#emojis)や[@mentions](https://github.com/blog/821) をJekyllのpostsやpagesGtihub.comのレポジトリが変更されればそれにともなって動的に変わります。
<!-- 
The Jemoji and jekyll-mentions plugins enable [emoji](#emojis) and [@mentions](https://github.com/blog/821) in your Jekyll posts and pages to work just like you'd expect when interacting with a repository on GitHub.com.
-->


[*Githubページで使えるレポジトリのメタデータやプラグインに関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1797-repository-metadata-and-plugin-support-for-github-pages)

### Viewing YAML Metadata in your Documents
Many blogging websites, like [Jekyll](http://jekyllrb.com/) with [GitHub Pages](http://pages.github.com/), depend on some YAML-formatted metadata at the beginning of your post. GitHub will render this metadata as a horizontal table, for easier reading

![YAML metadata](https://camo.githubusercontent.com/47245aa16728e242f74a9a324ce0d24c0b916075/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f36343035302f313232383236372f65303439643063362d323761302d313165332d396464382d6131636432323539393334342e706e67)

[*Read more about viewing YAML metadata in your documents.*](https://github.com/blog/1647-viewing-yaml-metadata-in-your-documents)

### Rendering Tabular Data
GitHub supports rendering tabular data in the form of `.csv` (comma-separated) and `.tsv` (tab-separated) files.

![Tabular data](https://camo.githubusercontent.com/1b6dd0157ffb45d9939abf14233a0cb13b3b4dfe/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f3238323735392f3937363436322f33323038336463652d303638642d313165332d393262322d3566323863313061353035392e706e67)

[*Read more about rendering tabular data.*](https://github.com/blog/1601-see-your-csvs)

### 差分
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
[Hub](https://github.com/github/hub)はGitのラッパーでさらに便利な機能やGithubと一緒に使うとと便利なコマンドなどが追加されています。
<!--
[Hub](https://github.com/github/hub) is a command line Git wrapper that gives you extra features and commands that make working with GitHub easier.
-->

以下のコマンドでこれまでの`$ git clone`と同様のことができます：

```bash
$ hub clone tiimgreen/toc
```

[*Hubのコマンドに関してのクールな機能についてのより詳しい内容はこちらを参照してください*](https://github.com/github/hub#commands)

### Decreasing Contributor Friction
If you want people to use and contribute to your project, you need to start by answering their most basic questions. What does the project do? How do I use it? How am I allowed to use it? How do I contribute? How do I get up and running in development? How do I make sure my new features didn't break old functionality?

[Friction](https://github.com/rafalchmiel/friction) is a command line script that will check your project for common [answers to these questions](https://github.com/rafalchmiel/friction/wiki). This is some example output:

[![Friction output](http://i.imgur.com/4EgpWo4.png)](https://github.com/rafalchmiel/friction)

*Friction supports MRI 2.1.0, MRI 2.0.0, and MRI 1.9.3.*

### Contributing Guidelines
`CONTRIBUTING` ファイルをレポジトリのルートに追加することによって、協力してくれる方がissueを作くる時やプルリクエストを送る際に際に以下の画像のように`CONTRIBUTING`ファイルへのリンクが表示されます。

![Contributing Guidelines](https://camo.githubusercontent.com/71995d6b0e620a9ef1ded00a04498241c69dd1bf/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f736b697463682f6973737565732d32303132303931332d3136323533392e6a7067)

[*Contributing Guidelinesに関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1184-contributing-guidelines)

### GitHub　リソース
| タイトル | リンク |
| ----- | ---- |
| GitHub Explore | https://github.com/explore |
| GitHub Blog | https://github.com/blog |
| GitHub Help | https://help.github.com/ |
| GitHub Training | http://training.github.com/ |
| GitHub Developer | https://developer.github.com/ |

#### GitHub ドーク
| タイトル | リンク |
| ----- | ---- |
| How GitHub Uses GitHub to Build GitHub | https://www.youtube.com/watch?v=qyz3jkOBbQY |
| Introduction to Git with Scott Chacon of GitHub | https://www.youtube.com/watch?v=ZDR433b0HJY |
| How GitHub No Longer Works | https://www.youtube.com/watch?v=gXD1ITW7iZI |
| Git and GitHub Secrets | https://www.youtube.com/watch?v=Foz9yvMkvlA |
| More Git and GitHub Secrets | https://www.youtube.com/watch?v=p50xsL-iVgU |

## Git
### 前のBranchへ
Gitで前のbranchに戻る：

```bash
$ git checkout -
# Switched to branch 'master'

$ git checkout -
# Switched to branch 'next'

$ git checkout -
# Switched to branch 'master'
```

[*Git branchingに関してのより詳しい内容はこちらを参照してください。*](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)

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

### 空のコミット :trollface:
`--allow-empty`を追加することによってコードに何も変更を加えてなくてもそのcommitメッセージをpushできます：

```bash
$ git commit -m "Big-ass commit" --allow-empty
```

例えば、以下のようなときに使います：

 - 新しい機能の追加などの始まりを明確かさせるために
 - コードに関係ないドキュメントの変化をした場合
 - レポジトリ上でのコミュニケーションをするために

### Git Statusのスタイル
実行：

```bash
$ git status
```

すると以下のようになります：

![git status](http://i.imgur.com/o3PEHAA.png)

`-sb` を追加すると：

```bash
$ git status -sb
```

すると以下のようになります：

![git status -sb](http://i.imgur.com/xNI1bT0.png)

[* Git `status` コマンドに関してのより詳しい内容はこちらを参照してください。*](http://git-scm.com/docs/git-status)

### Git Logのスタイル
実行：

```bash
$ git log --all --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
```

すると以下のようになります：

![git log --all --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative](http://i.imgur.com/R2z8l7c.png)

Credit to [Palesz](http://stackoverflow.com/users/88355/palesz)

*[ここ](https://github.com/tiimgreen/github-cheat-sheet#aliases)にエイリアスの仕組みを参照されます*

[* Git `log` コマンドに関してのより詳しい内容はこちらを参照してください。*](http://git-scm.com/docs/git-log)

### Git Query
Git Queryを使うことによって今までのコミットメッセージの中の最も新しいものから**query**にマッチするものを検索することができます。

```bash
$ git show :/query
```

`query` 部分には検索したい単語をいれます。そしてマッチする最も新しいものの詳細が表示されます。


```bash
$ git show :/typo
```
![git show :/query](http://i.imgur.com/icaGiNt.png)

*`q` と押すと中断されます*

### マージされたブランチ
実行：

```bash
$ git branch --merged
```
これまでに現在のブランチに**マージされたブランチ**の一覧が表示されます。

逆の場合：

```bash
$ git branch --no-merged
```

これまでに現在のブランチに**マージされていないブランチ**の一覧が表示されます。


[*Read more about the Git `branch` command.*](http://git-scm.com/docs/git-branch)

### Web Server for Browsing Local Repositories
`gitweb`で`instaweb` コマンドを使うことによって現在のレポジトリを見ることができます。このコマンドは簡単に `gitweb` を立ち上げるためのものでこれはローカルレポジトリを見るためのウェブサーバーです。
<!--
Use the Git `instaweb` command to instantly browse your working repository in `gitweb`. This command is a simple script to set up `gitweb` and a web server for browsing the local repository.
-->

```bash
$ git instaweb
```

すると以下のような画面が開きます：

![Git instaweb](http://i.imgur.com/Dxekmqc.png)

[*Git `instaweb`コマンドに関してのクールな機能についてのより詳しい内容はこちらを参照してください*](http://git-scm.com/docs/git-instaweb)

### Gitの設定
`.gitconfig`にはGitの設定のすべてが含まれています。

#### エイリアス
エイリアスを使うことによってGitコマンドの呼び方を自分で設定することができます。例えば、`git a`を`git add --all`のエイリアスとして設定できます。

<!-- 
Aliases are helpers that let you define your own git calls. For example you could set `git a` to run `git add --all`.
-->
エイリアスを設定する際には `~/.gitconfig` に以下のようになります：
<!-- 　To add an alias, either navigate to `~/.gitconfig` and fill it out in the following format: -->

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

もしくは以下のようなコマンドを打って `~/.gitconfig` に追加します：

```bash
$ git config --global alias.new_alias git_function
```

例：

```bash
$ git config --global alias.cm commit
```

複数のコマンドを合わせたものを設定したい場合は、シングルクォーテーションで囲みます：

```bash
$ git config --global alias.ac 'add -A . && commit'
```

いくつかの便利なエイリアス一覧：

| Alias | Command | What to Type |
| --- | --- | --- |
| `git cm` | `git commit` | `git config --global alias.cm commit` |
| `git co` | `git checkout` | `git config --global alias.co checkout` |
| `git ac` | `git add . -A` `git commit` | `git config --global alias.ac '!git add -A && git commit'` |
| `git st` | `git status -sb` | `git config --global alias.st 'status -sb'` |
| `git tags` | `git tag -l` | `git config --global alias.tags 'tag -l'` |
| `git branches` | `git branch -a` | `git config --global alias.branches 'branch -a'` |
| `git remotes` | `git remote -v` | `git config --global alias.remotes 'remote -v'` |

#### コマンドの自動補完機能
もし間違って、`$ git comt` と打ってしまうと以下のようになります：
If you type `git comit` you will get this:

```bash
$ git comit -m "Message"
# git: 'comit' is not a git command. See 'git --help'.

# Did you mean this?
#   commit
```

`comit` と打っても`commit` を自動的に補完させるためには以下のします：
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
Gitコマンドに関するアウトプットに色をつけるために：


```bash
$ git config --global color.ui 1
```

[*Read more about the Git `config` command.*](http://git-scm.com/docs/git-config)

### Gitに関するサイトなどの情報
| タイトル | リンク |
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

#### Gitに関する本の一覧
| タイトル | リンク |
| ----- | ---- |
| Pragmatic Version Control Using Git | http://www.pragprog.com/titles/tsgit/pragmatic-version-control-using-git |
| Pro Git | http://git-scm.com/book |
| Git Internals Peepcode | http://peepcode.com/products/git-internals-pdf |
| Git in the Trenches | http://cbx33.github.com/gitt/ |
| Version Control with Git | http://www.amazon.com/Version-Control-Git-collaborative-development/dp/1449316387 |
| Pragmatic Guide to Git | http://www.pragprog.com/titles/pg_git/pragmatic-guide-to-git |
| Git: Version Control for Everyone | http://www.packtpub.com/git-version-control-for-everyone/book |
