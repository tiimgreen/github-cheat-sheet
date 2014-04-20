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
  - [空行を無視](#%E7%A9%BA%E8%A1%8C%E3%82%92%E7%84%A1%E8%A6%96)
  - [ユーザー別のコミットヒストリー表示](#%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%88%A5%E3%81%AE%E3%82%B3%E3%83%9F%E3%83%83%E3%83%88%E3%83%92%E3%82%B9%E3%83%88%E3%83%AA%E3%83%BC%E8%A1%A8%E7%A4%BA)
  - [レポジトリのクローン](#%E7%A9%BA%E8%A1%8C%E3%82%92%E7%84%A1%E8%A6%96)
  - [ブランチの比較](#%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%81%AE%E6%AF%94%E8%BC%83)
  - [フォークされたブランチとの比較](#fork%E3%81%95%E3%82%8C%E3%81%9Fbranch%E3%81%A8%E3%81%AE%E6%AF%94%E8%BC%83)
  - [Gists](#gists)
  - [Git.io](#gitio)
  - [ショットカットキー](#%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%E3%82%AB%E3%83%83%E3%83%88%E3%82%AD%E3%83%BC)
  - [レポジトリ内のコードをハイライト](#%E3%83%AC%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E5%86%85%E3%81%AE%E3%82%B3%E3%83%BC%E3%83%89%E3%82%92%E3%83%8F%E3%82%A4%E3%83%A9%E3%82%A4%E3%83%88)
  - [コミットメッセージによるissueのクローズ](#%E3%82%B3%E3%83%9F%E3%83%83%E3%83%88%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%81%AB%E3%82%88%E3%82%8Bissue%E3%81%AE%E3%82%AF%E3%83%AD%E3%83%BC%E3%82%BA)
  - [issue同士のリンク](#issue%E5%90%8C%E5%A3%AB%E3%81%AE%E3%83%AA%E3%83%B3%E3%82%AF)
  - [プルリクエストにCIステータスを表示](#pull-request%E3%81%ABci%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%82%92%E8%A1%A8%E7%A4%BA)
  - [マークダウンファイル内でのコードのハイライト](#%E3%83%9E%E3%83%BC%E3%82%AF%E3%83%80%E3%82%A6%E3%83%B3%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E5%86%85%E3%81%A7%E3%81%AE%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E3%83%8F%E3%82%A4%E3%83%A9%E3%82%A4%E3%83%88)
  - [絵文字](#%E7%B5%B5%E6%96%87%E5%AD%97)
  - [画像（GIF）](#%E7%94%BB%E5%83%8Fgif)
    - [Github Wikiに画像を埋め込む](#github-wiki%E3%81%AB%E7%94%BB%E5%83%8F%E3%82%92%E5%9F%8B%E3%82%81%E8%BE%BC%E3%82%80)
  - [素早く引用（Quick Quoting）](#%E7%B4%A0%E6%97%A9%E3%81%8F%E5%BC%95%E7%94%A8quick-quoting)
  - [ライセンスを簡単に表示（Quick Licensing）](#%E3%83%A9%E3%82%A4%E3%82%BB%E3%83%B3%E3%82%B9%E3%82%92%E7%B0%A1%E5%8D%98%E3%81%AB%E8%A1%A8%E7%A4%BAquick-licensing)
  - [タスクリスト](#%E3%82%BF%E3%82%B9%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88)
  - [相対リンク](#%E7%9B%B8%E5%AF%BE%E3%83%AA%E3%83%B3%E3%82%AF)
  - [Githubページで使えるメタデータやプラグイン](#github%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%A7%E4%BD%BF%E3%81%88%E3%82%8B%E3%83%A1%E3%82%BF%E3%83%87%E3%83%BC%E3%82%BF%E3%82%84%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3)
  - [YAMLメタデータをドキュメントで表示](#yaml%E3%83%A1%E3%82%BF%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E3%83%89%E3%82%AD%E3%83%A5%E3%83%A1%E3%83%B3%E3%83%88%E3%81%A7%E8%A1%A8%E7%A4%BA)
  - [表形式データの表示](#%E8%A1%A8%E5%BD%A2%E5%BC%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A1%A8%E7%A4%BA)
  - [差分](#%E5%B7%AE%E5%88%86)
    - [Rendered prose Diffs](#rendered-prose-diffs)
    - [地図の差分](#%E5%9C%B0%E5%9B%B3%E3%81%AE%E5%B7%AE%E5%88%86)
    - [差分コンテンツの展開](#%E5%B7%AE%E5%88%86%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%81%AE%E5%B1%95%E9%96%8B)
    - [差分（Diff・Patch） of Pull Request](#%E5%B7%AE%E5%88%86diffpatch-of-pull-request)
  - [Hub](#hub)
  - [Frictionと使ってコントリビューターとの衝突（Friction）を減らす](##friction%E3%81%A8%E4%BD%BF%E3%81%A3%E3%81%A6%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%BF%E3%83%BC%E3%81%A8%E3%81%AE%E8%A1%9D%E7%AA%81friction%E3%82%92%E6%B8%9B%E3%82%89%E3%81%99)
  - [コントリビューティングガイドライン](#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3)
  - [GitHubに関するサイトなどの情報](#github-resources)
    - [GitHub トーク](#github-talks)
 - [Git](#git)
  - [前のBranchへ](#%E5%89%8D%E3%81%AEbranch%E3%81%B8)
  - [Stripspace](#stripspace)
  - [プルリクエストをチェックアウト](##%E3%83%97%E3%83%AB%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%82%92%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%82%A2%E3%82%A6%E3%83%88)
  - [空のコミット :trollface:](#%E7%A9%BA%E3%81%AE%E3%82%B3%E3%83%9F%E3%83%83%E3%83%88-trollface)
  - [Git Statusのスタイル](#git-status%E3%81%AE%E3%82%B9%E3%82%BF%E3%82%A4%E3%83%AB)
  - [Git Logのスタイル](#git-log%E3%81%AE%E3%82%B9%E3%82%BF%E3%82%A4%E3%83%AB)
  - [Git Query](#git-query)
  - [マージされたブランチ](#%E3%83%9E%E3%83%BC%E3%82%B8%E3%81%95%E3%82%8C%E3%81%9F%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81)
  - [ローカルレポジトリを見るためのウェブサーバ](#web-server-for-browsing-local-repositories)
  - [Gitの設定](#git%E3%81%AE%E8%A8%AD%E5%AE%9A)
    - [エイリアス](##%E3%82%A8%E3%82%A4%E3%83%AA%E3%82%A2%E3%82%B9)
    - [コマンドの自動補完機能](#%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%81%AE%E8%87%AA%E5%8B%95%E8%A3%9C%E5%AE%8C%E6%A9%9F%E8%83%BD)
    - [色](#color)
  - [Gitに関するサイトなどの情報](#git%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AA%E3%81%A9%E3%81%AE%E6%83%85%E5%A0%B1)
    - [Gitに関する本の一覧](#git%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E6%9C%AC%E3%81%AE%E4%B8%80%E8%A6%A7)

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

### YAMLメタデータをドキュメントで表示
[GitHub Pages](http://pages.github.com/)や[Jekyll](http://jekyllrb.com/)のような多くのブログサービスはその投稿にYAMLのメタデータの形式をとっています。Githubはこれらのデータを以下の画像のように見やすく表示してくれます。

![YAML metadata](https://camo.githubusercontent.com/47245aa16728e242f74a9a324ce0d24c0b916075/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f36343035302f313232383236372f65303439643063362d323761302d313165332d396464382d6131636432323539393334342e706e67)

[*YAMLメタデータをドキュメントで表示することに関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1647-viewing-yaml-metadata-in-your-documents)

### 表形式データの表示
Githubは`.csv`や `.tsv` のファイルフォーマットを使用することで表形式データの表示を可能にします。

![Tabular data](https://camo.githubusercontent.com/1b6dd0157ffb45d9939abf14233a0cb13b3b4dfe/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f3238323735392f3937363436322f33323038336463652d303638642d313165332d393262322d3566323863313061353035392e706e67)

[*表形式データの表示に関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1601-see-your-csvs)

### 差分
#### Rendered Prose Diffs
Commits and pull requests including rendered documents supported by GitHub (e.g. Markdown) feature *source* and *rendered* views.

![Source / Rendered view](https://github-images.s3.amazonaws.com/help/repository/rendered_prose_diff.png)

Click the "rendered" button to see the changes as they'll appear in the rendered document. Rendered prose view is handy when you're adding, removing, and editing text:

![Rendered Prose Diffs](https://f.cloud.github.com/assets/17715/2003056/3997edb4-862b-11e3-90be-5e9586edecd7.png)

[*Read more about rendered prose diffs.*](https://github.com/blog/1784-rendered-prose-diffs)

#### 地図の差分
地図の情報を含むcommitやプルリクエストを見る際に、Githubはそれを視覚的にその差分を表示します

[![Diffable Maps](https://f.cloud.github.com/assets/282759/2090660/63f2e45a-8e97-11e3-9d8b-d4c8078b004e.gif)](https://github.com/benbalter/congressional-districts/commit/2233c76ca5bb059582d796f053775d8859198ec5)

[*地図の差分に関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1772-diffable-more-customizable-maps)

#### 差分コンテンツの展開
差分の展開ボタン（*unfold*）を使用すると、クリックするだけで、コンテキストの追加の行を明らかにすることができます。ファイル全体を明らかにしてきたまで展開クリック保つことができ、かつ機能がGitHubには、差分を表示することが可能です。

![Expanding Context in Diffs](https://f.cloud.github.com/assets/22635/1610539/863c1f64-5584-11e3-82bf-151b406a272f.gif)

[*差分コンテンツの展開に関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1705-expanding-context-in-diffs)

#### 差分（Diff・Patch） of Pull Request
URLに `.diff` か `.patch` をURLに追加するこでプルリクエストの差分を見ることができます。

例：

```
https://github.com/tiimgreen/github-cheat-sheet/pull/15
https://github.com/tiimgreen/github-cheat-sheet/pull/15.diff
https://github.com/tiimgreen/github-cheat-sheet/pull/15.patch
```


`.diff`をURLに追加すると以下のようになります：

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

### Frictionと使ってコントリビューターとの衝突（Friction）を減らす
もしも、あなたのプロジェクトを使ってそして開発に貢献して欲しい場合、まずは以下の基本的な質問に答える必要があります。このプロジェクトはなんなのか？・どう使うのか？・どのような場合に使えるのか？・どのように貢献すればいいのか？・どのように開発すればいいのか？・どのように開発すれば自分の新しい機能が既存のものを壊さずにでるのか？

<!-- If you want people to use and contribute to your project, you need to start by answering their most basic questions. What does the project do? How do I use it? How am I allowed to use it? How do I contribute? How do I get up and running in development? How do I make sure my new features didn't break old functionality? -->

[Friction](https://github.com/rafalchmiel/friction)というコマンドラインツールが[基本的なこと](https://github.com/rafalchmiel/friction/wiki).に関して調べてくれます。

例：

[![Friction output](http://i.imgur.com/4EgpWo4.png)](https://github.com/rafalchmiel/friction)

*Friction MRI 2.1.0, MRI 2.0.0, and MRI 1.9.3.　をサポートしています*

### コントリビューティングガイドライン
`CONTRIBUTING` ファイルをレポジトリのルートに追加することによって、協力してくれる方がissueを作くる時やプルリクエストを送る際に際に以下の画像のように`CONTRIBUTING`ファイルへのリンクが表示されます。

![Contributing Guidelines](https://camo.githubusercontent.com/71995d6b0e620a9ef1ded00a04498241c69dd1bf/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f736b697463682f6973737565732d32303132303931332d3136323533392e6a7067)

[*Contributing Guidelinesに関してのより詳しい内容はこちらを参照してください*](https://github.com/blog/1184-contributing-guidelines)

### GitHubに関するサイトなどの情報
| タイトル | リンク |
| ----- | ---- |
| GitHub Explore | https://github.com/explore |
| GitHub Blog | https://github.com/blog |
| GitHub Help | https://help.github.com/ |
| GitHub Training | http://training.github.com/ |
| GitHub Developer | https://developer.github.com/ |

#### GitHub トーク
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

<!-- - Strips trailing whitespace -->
- 末尾のホワイトスペースの削除
- 空白を詰める
- ファイルの最後に空行を追加
<!-- - Collapses newlines -->


<!-- A file must be passed when calling the command, e.g.: -->
ファイルはこのようなコマンドで呼ばれます

例：


```bash
$ git stripspace < README.md
```

[*Git `stripspace` に関してのより詳しい内容はこちらを参照してください。*](http://git-scm.com/docs/git-stripspace)

### プルリクエストをチェックアウト
プルリクエストをローカルにチャックアウトするシたい場合に、以下のコマンドを使ってフェッチすることがきます：

```bash
$ git fetch origin '+refs/pull/*/head:refs/pull/*'
```
そして、プルリクエストをチェックアウトできます：
<!-- then, checkout Pull Request (i.e. 42) using -->

```bash
$ git checkout refs/pull/42
```

他の方法としては、リモートブランチとしてフェッチすることもできます：

```bash
$ git fetch origin '+refs/pull/*/head:refs/remotes/origin/pr/*'
```

そしてこのようにチャックアウトします：

```bash
$ git checkout origin/pr/42
```
.git/configに以下のコードを追加すると自動的にフェッチすることもできます：

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

[*ローカルにプルリクエストをチェックアウトすること関してのより詳しい内容はこちらを参照してください。*](https://help.github.com/articles/checking-out-pull-requests-locally)

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

### ローカルレポジトリを見るためのウェブサーバ
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
<!-- If you type `git comit` you will get this: -->

```bash
$ git comit -m "Message"
# git: 'comit' is not a git command. See 'git --help'.

# Did you mean this?
#   commit
```

`comit` と打っても`commit` を自動的に補完させるためには以下のします：
<!-- To call `commit` when `comit` is typed, just enable auto-correct: -->

```bash
$ git config --global help.autocorrect 1
```

<!-- So now you will get this: -->
すると以下のようになります：

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
| 開発効率をUPする Git逆引き入門 | http://goo.gl/vHb8Sr |
| Pragmatic Version Control Using Git | http://www.pragprog.com/titles/tsgit/pragmatic-version-control-using-git |
| Pro Git | http://git-scm.com/book |
| Git Internals Peepcode | http://peepcode.com/products/git-internals-pdf |
| Git in the Trenches | http://cbx33.github.com/gitt/ |
| Version Control with Git | http://www.amazon.com/Version-Control-Git-collaborative-development/dp/1449316387 |
| Pragmatic Guide to Git | http://www.pragprog.com/titles/pg_git/pragmatic-guide-to-git |
| Git: Version Control for Everyone | http://www.packtpub.com/git-version-control-for-everyone/book |
