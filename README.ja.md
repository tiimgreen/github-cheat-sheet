# GitHubカンニング・ペーパー [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
これはGitやGitHubの隠された機能やよく知られていない機能の一覧だ。[Zach Holman](https://github.com/holman)によるAloha Ruby Conference 2012での[Git and GitHub Secrets](https://github.com/tiimgreen/github-cheat-sheet)（[スライド](https://github.com/tiimgreen/github-cheat-sheet)）とWDCNZ 2013での[More Git and GitHub Secrets](https://vimeo.com/72955426)（[スライド](https://speakerdeck.com/holman/more-git-and-github-secrets)）の二つのトークを元にしている。

*短縮URL: [`http://git.io/sheet`](http://git.io/sheet)*

*Read this in other languages: [English](README.md), [한국어](README.ko.md), [日本語](README.ja.md), [简体中文](README.zh-cn.md), [正體中文](README.zh-tw.md).*

# 目次
- [GitHub](#github)
  - [空白の無視](#%E7%A9%BA%E7%99%BD%E3%81%AE%E7%84%A1%E8%A6%96)
  - [タブ幅の調節](#%E3%82%BF%E3%83%96%E5%B9%85%E3%81%AE%E8%AA%BF%E7%AF%80)
  - [特定のユーザーによるコミット履歴](#%E7%89%B9%E5%AE%9A%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%82%88%E3%82%8B%E3%82%B3%E3%83%9F%E3%83%83%E3%83%88%E5%B1%A5%E6%AD%B4)
  - [リポジトリのクローン](#%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%81%AE%E3%82%AF%E3%83%AD%E3%83%BC%E3%83%B3)
  - [ブランチ](#%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81)
    - [全ブランチを別のブランチと比較](#%E5%85%A8%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%82%92%E5%88%A5%E3%81%AE%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%81%A8%E6%AF%94%E8%BC%83)
    - [ブランチ同士の比較](#%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E5%90%8C%E5%A3%AB%E3%81%AE%E6%AF%94%E8%BC%83)
    - [フォークされたリポジトリ間でのブランチ比較](#%E3%83%95%E3%82%A9%E3%83%BC%E3%82%AF%E3%81%95%E3%82%8C%E3%81%9F%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E9%96%93%E3%81%A7%E3%81%AE%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E6%AF%94%E8%BC%83)
  - [Gists](#gists)
  - [Git.io](#gitio)
  - [キーボード・ショートカット](#%E3%82%AD%E3%83%BC%E3%83%9C%E3%83%BC%E3%83%89%E3%82%B7%E3%83%A7%E3%83%BC%E3%83%88%E3%82%AB%E3%83%83%E3%83%88)
  - [コードの指定行の強調](#%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E6%8C%87%E5%AE%9A%E8%A1%8C%E3%81%AE%E5%BC%B7%E8%AA%BF)
  - [コミットからissueを閉じる](#%E3%82%B3%E3%83%9F%E3%83%83%E3%83%88%E3%81%8B%E3%82%89issue%E3%82%92%E9%96%89%E3%81%98%E3%82%8B)
  - [issueの相互リンク](#issue%E3%81%AE%E7%9B%B8%E4%BA%92%E3%83%AA%E3%83%B3%E3%82%AF)
  - [コメントのロック](#%E3%82%B3%E3%83%A1%E3%83%B3%E3%83%88%E3%81%AE%E3%83%AD%E3%83%83%E3%82%AF)
  - [pull requestでのCI結果の表示](#pull-request%E3%81%A7%E3%81%AEci%E7%B5%90%E6%9E%9C%E3%81%AE%E8%A1%A8%E7%A4%BA)
  - [絞り込み検索](#%E7%B5%9E%E3%82%8A%E8%BE%BC%E3%81%BF%E6%A4%9C%E7%B4%A2)
  - [Markdownファイルでの構文強調](#markdown%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%A7%E3%81%AE%E6%A7%8B%E6%96%87%E5%BC%B7%E8%AA%BF)
  - [Emoji](#emoji)
  - [画像及びアニメーションGIF](#%E7%94%BB%E5%83%8F%E5%8F%8A%E3%81%B3%E3%82%A2%E3%83%8B%E3%83%A1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3gif)
    - [GitHub Wikiへの画像の添付](#github-wiki%E3%81%B8%E3%81%AE%E7%94%BB%E5%83%8F%E3%81%AE%E6%B7%BB%E4%BB%98)
  - [素早く引用](#%E7%B4%A0%E6%97%A9%E3%81%8F%E5%BC%95%E7%94%A8)
  - [コメントへのクリップボードの画像の追加](#%E3%82%B3%E3%83%A1%E3%83%B3%E3%83%88%E3%81%B8%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%83%97%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E7%94%BB%E5%83%8F%E3%81%AE%E8%BF%BD%E5%8A%A0)
  - [設定済みライセンスの追加](#%E8%A8%AD%E5%AE%9A%E6%B8%88%E3%81%BF%E3%83%A9%E3%82%A4%E3%82%BB%E3%83%B3%E3%82%B9%E3%81%AE%E8%BF%BD%E5%8A%A0)
  - [タスクリスト](#%E3%82%BF%E3%82%B9%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88)
    - [Markdownファイルでのタスクリスト](#markdown%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%A7%E3%81%AE%E3%82%BF%E3%82%B9%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88)
  - [相対リンク](#%E7%9B%B8%E5%AF%BE%E3%83%AA%E3%83%B3%E3%82%AF)
  - [GitHub Pagesでのメタデータとプラグインのサポート](#github-pages%E3%81%A7%E3%81%AE%E3%83%A1%E3%82%BF%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3%E3%81%AE%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88)
  - [文書内のYAMLメタデータ](#%E6%96%87%E6%9B%B8%E5%86%85%E3%81%AEyaml%E3%83%A1%E3%82%BF%E3%83%87%E3%83%BC%E3%82%BF)
  - [表形式のデータ表示](#%E8%A1%A8%E5%BD%A2%E5%BC%8F%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA)
  - [PDF表示](#pdf%E8%A1%A8%E7%A4%BA)
  - [pull requestの取り消し](#pull-request%E3%81%AE%E5%8F%96%E3%82%8A%E6%B6%88%E3%81%97)
  - [差分の表示](#%E5%B7%AE%E5%88%86%E3%81%AE%E8%A1%A8%E7%A4%BA)
    - [レンダリング済みの差分表示](#%E3%83%AC%E3%83%B3%E3%83%80%E3%83%AA%E3%83%B3%E3%82%B0%E6%B8%88%E3%81%BF%E3%81%AE%E5%B7%AE%E5%88%86%E8%A1%A8%E7%A4%BA)
    - [マップ差分の可視化](#%E3%83%9E%E3%83%83%E3%83%97%E5%B7%AE%E5%88%86%E3%81%AE%E5%8F%AF%E8%A6%96%E5%8C%96)
    - [差分表示の前後を表示](#%E5%B7%AE%E5%88%86%E8%A1%A8%E7%A4%BA%E3%81%AE%E5%89%8D%E5%BE%8C%E3%82%92%E8%A1%A8%E7%A4%BA)
    - [pull requestの内容をDIFFまたはPATCH形式で取得](#pull-request%E3%81%AE%E5%86%85%E5%AE%B9%E3%82%92diff%E3%81%BE%E3%81%9F%E3%81%AFpatch%E5%BD%A2%E5%BC%8F%E3%81%A7%E5%8F%96%E5%BE%97)
    - [画像の表示とDIFF](#%E7%94%BB%E5%83%8F%E3%81%AE%E8%A1%A8%E7%A4%BA%E3%81%A8diff)
  - [Hub](#hub)
  - [開発参加のガイドライン](#%E9%96%8B%E7%99%BA%E5%8F%82%E5%8A%A0%E3%81%AE%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3)
  - [Octicons](#octicons)
  - [GitHub情報](#github%E6%83%85%E5%A0%B1)
    - [GitHub Talks](#github-talks)
- [Git](#git)
  - [すべての削除済みファイルをワーキング・ツリーから削除する](#%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E5%89%8A%E9%99%A4%E6%B8%88%E3%81%BF%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E3%83%AF%E3%83%BC%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%84%E3%83%AA%E3%83%BC%E3%81%8B%E3%82%89%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B)
  - [直前のブランチ](#%E7%9B%B4%E5%89%8D%E3%81%AE%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81)
  - [空白の削除](#%E7%A9%BA%E7%99%BD%E3%81%AE%E5%89%8A%E9%99%A4)
  - [SSH公開鍵](#ssh%E5%85%AC%E9%96%8B%E9%8D%B5)
  - [pull requestのチェックアウト](#pull-request%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%82%A2%E3%82%A6%E3%83%88)
  - [空のコミット](#%E7%A9%BA%E3%81%AE%E3%82%B3%E3%83%9F%E3%83%83%E3%83%88)
  - [Gitステータスのスタイリング](#git%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%81%AE%E3%82%B9%E3%82%BF%E3%82%A4%E3%83%AA%E3%83%B3%E3%82%B0)
  - [Gitログのスタイリング](#git%E3%83%AD%E3%82%B0%E3%81%AE%E3%82%B9%E3%82%BF%E3%82%A4%E3%83%AA%E3%83%B3%E3%82%B0)
  - [コミットログの検索](#%E3%82%B3%E3%83%9F%E3%83%83%E3%83%88%E3%83%AD%E3%82%B0%E3%81%AE%E6%A4%9C%E7%B4%A2)
  - [Git Grep](#git-grep)
  - [マージ済みブランチ](#%E3%83%9E%E3%83%BC%E3%82%B8%E6%B8%88%E3%81%BF%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81)
  - [FixupとAutosquash](#fixup%E3%81%A8autosquash)
  - [ローカル・リポジトリを参照するウェブサーバー](#%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%82%92%E5%8F%82%E7%85%A7%E3%81%99%E3%82%8B%E3%82%A6%E3%82%A7%E3%83%96%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC)
  - [Gitの設定](#git%E3%81%AE%E8%A8%AD%E5%AE%9A)
    - [エイリアス](#%E3%82%A8%E3%82%A4%E3%83%AA%E3%82%A2%E3%82%B9)
    - [コマンドの自動修正](#%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%81%AE%E8%87%AA%E5%8B%95%E4%BF%AE%E6%AD%A3)
    - [色設定](#%E8%89%B2%E8%A8%AD%E5%AE%9A)
  - [Git情報](#git%E6%83%85%E5%A0%B1)
    - [Git Books](#git-books)
- [訳注](#%E8%A8%B3%E6%B3%A8)

## GitHub
### 空白の無視
GitHub上で差分ページを表示している時、そのURLに`?w=1`を加えると、空白の変化によるできた差分は表示されなくなり、コード上の変化だけを参照することができる。

![Diff without whitespace](https://camo.githubusercontent.com/797184940defadec00393e6559b835358a863eeb/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f776869746573706163652e706e67)

[*GitHubの秘密についてもっと詳しく*](https://github.com/blog/967-github-secrets)

### タブ幅の調節
差分やファイルを表示している時、URLに`?ts=4`を追加するとタブを空白4つの幅で表示する。デフォルトは8つだ。`ts`に指定した数で表示されるということだ。これはGistやrawファイルを表示している時には適用されないが、[Chrome](https://chrome.google.com/webstore/detail/github-tab-size/ofjbgncegkdemndciafljngjbdpfmbkn)をインストールすることにより、対応することができる。

例えばGoのソースファイルを表示している時、`?ts=4`を追加する前はこのように表示されるが:

![Before, tab space example](http://i.imgur.com/GIT1Fr0.png)

`?ts=4`を追加するとこのように表示される:

![After, tab space example](http://i.imgur.com/70FL4H9.png)

### 特定のユーザーによるコミット履歴
特定のユーザーによるあるリポジトリへのコミット履歴のみを参照したい場合は、`?author={user}`をURLの末尾に付ける。

```
https://github.com/rails/rails/commits/master?author=dhh
```
![DHH commit history](http://i.imgur.com/S7AE29b.png)

[*コミット・ビューの違いについてもっと詳しく*](https://help.github.com/articles/differences-between-commit-views)

### リポジトリのクローン
リポジトリをクローンする時、URLの末尾の`.git`は無くても構わない。

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

[*Gitの`clone`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-clone)

### ブランチ
#### 全ブランチを別のブランチと比較
コミット一覧ボタンの隣から[ブランチ一覧](https://github.com/tiimgreen/github-cheat-sheet/branches)ページに行くと:

```
https://github.com/{user}/{repo}/branches
```

メイン・ブランチにマージされていないブランチの一覧が表示される。

このページからボタンをクリックしてブランチ比較ページへ移動したりブランチを削除することができる。

![Compare branches not merged into master in rails/rails repo - https://github.com/rails/rails/branches](http://i.imgur.com/0FEe30z.png)

#### ブランチ同士の比較
GitHubのブランチ比較は以下のようなURLで提供されている:

```
https://github.com/{user}/{repo}/compare/{range}
```

`{range}`を`master...4-1-stable`に変更する。

例えば:

```
https://github.com/rails/rails/compare/master...4-1-stable
```
![Rails branch compare example](http://i.imgur.com/tIRCOsK.png)

`{range}`には以下のように変更することもできる:

```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```

*日付の形式は`YYYY-MM-DD`だ。*

![Another compare example](http://i.imgur.com/5dtzESz.png)

`diff`や`patch`のビューでもブランチを利用して比較することができる:

```
https://github.com/rails/rails/compare/master...4-1-stable.diff
https://github.com/rails/rails/compare/master...4-1-stable.patch
```

[*時間を指定してのブランチ比較についてもっと詳しく*](https://help.github.com/articles/comparing-commits-across-time)

#### フォークされたリポジトリ間でのブランチ比較
GitHubでフォークされたリポジトリ同士でブランチを比較する場合、以下のようなURLを変更する:

```
https://github.com/user/repo/compare/{foreign-user}:{branch}...{own-branch}
```

例:

```
https://github.com/rails/rails/compare/byroot:master...master
```

![Forked branch compare](http://i.imgur.com/Q1W6qcB.png)

### Gists
[Gists](https://gist.github.com/)は少量のコード群を管理する最適な手段だ。ちゃんとしたリポジトリをいちいち作成する必要はない。

![Gist](http://i.imgur.com/VkKI1LC.png?1)

GistのURLの最後に`.pibb`を付ける([例](https://gist.github.com/hail2u/9477708.pibb))と*HTMLのみ*のバージョンが表示されるので、そのソースは他のウェブサイトに貼り付けるにはもってこいだろう。

簡単なものとはいえ、Gitリポジトリとして機能するため、以下のようにすれば普通のGitリポジトリと同じようにクローンすることができる:

```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/BcFzabp.png)

This means you also can modify and push updates to Gists:

```bash
$ git commit
$ git push
Username for 'https://gist.github.com':
Password for 'https://tiimgreen@gist.github.com':
```

しかしながら、Gistではディレクトリーがサポートされていない。全てのファイルはリポジトリーのルートに置かれている必要がある。

[*Gistの作成についてもっと詳しく*](https://help.github.com/articles/creating-gists)

### Git.io
[Git.io](http://git.io)はGitHubの提供するGitHub専用のシンプルな短縮URLサービスだ。

![Git.io](http://i.imgur.com/6JUfbcG.png?1)

cURLを使って利用することができる:

```bash
$ curl -i http://git.io -F "url=https://github.com/..."
HTTP/1.1 201 Created
Location: http://git.io/abc123

$ curl -i http://git.io/abc123
HTTP/1.1 302 Found
Location: https://github.com/...
```

[*Git.ioについてもっと詳しく*](https://github.com/blog/985-git-io-github-url-shortener)

### キーボード・ショートカット
リポジトリをブラウザーで開いている時は、ショートカットを利用して様々な機能ヘ簡単にアクセスできるようになっている。

 - `t`を押すとファイルの検索インターフェイスが起動する。
 - `w`を押すとブランチ選択インターフェイスが起動する。
 - `s`を押すと現在閲覧しているリポジトリーから検索するフォームにフォーカスが当たる。ここでBackspaceを押し「This repository」という文字列を消すことでGitHub全体からの検索へと切り替えることができる
 - issue画面で`l`を押すとラベルの編集インターフェイスが開かれる。
 - __ファイルを参照している時__（例: `https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`)に`y`を押すと、参照している時の状態で固定されるURLに変更される。つまりそのファイルのコードが後に変化したとしても、そのURLでは今とまったく同じ状態で表示されるということだ。

`?`を押すとそのページで使える全ショートカットが表示されるだろう。

![Keyboard shortcuts](http://i.imgur.com/y5ZfNEm.png)

[*検索機能についてもっと詳しく*](https://help.github.com/articles/search-syntax/)

### コードの指定行の強調
コードのURLの末尾に`#L52`と付けるか行番号をクリックすると、その行が強調表示される。

これは範囲指定も可能だ（例: `#L53-L60`）。こういった範囲を選択するには`shift`を押しながら二つの行をクリックしても良い:

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

### コミットからissueを閉じる
あるコミットでissueを解決した場合、コミットメッセージで`fix/fixes/fixed`や`close/closes/closed`、`resolve/resolves/resolved`に続けてissue番号を指定すると、そのコミットがmasterブランチにpushされると同時に指定issueが閉じられるだろう。

```bash
$ git commit -m "Fix screwup, fixes #12"
```

こうするとissue#12が閉じられ、閉じたissueにはそのコミットへの参照が自動的に追加される。

![Closing Repo](http://i.imgur.com/Uh1gZdx.png)

[*コミット・メッセージからissueを閉じる方法についてもっと詳しく*](https://help.github.com/articles/closing-issues-via-commit-messages)

### issueの相互リンク
同じリポジトリの違うissueへリンクを張り参照させたい場合、`#`に続けてissue番号を指定する。そうすると自動的にリンクが作成されるだろう。

別のリポジトリのissueの場合は`{user}/{repo}#ISSUE_NUMBER`とすれば良い（例: `tiimgreen/toc#12`）。

![Cross-Link Issues](https://camo.githubusercontent.com/447e39ab8d96b553cadc8d31799100190df230a8/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f7265666572656e6365732e706e67)

### コメントのロック
リポジトリのオーナーや共同開発者ならば、pull requestやissueへのコメントをロックできるようになった。

![Lock conversation](https://cloud.githubusercontent.com/assets/2723/3221693/bf54dd44-f00d-11e3-8eb6-bb51e825bc2c.png)

つまりそのプロジェクトの共同開発者ではないユーザーはコメントをすることができないということだ。

![Comments locked](https://cloud.githubusercontent.com/assets/2723/3221775/d6e513b0-f00e-11e3-9721-2131cb37c906.png)

[*コメントのロックについてもっと詳しく*](https://github.com/blog/1847-locking-conversations)

### pull requestでのCI結果の表示
適切に設定を行えばpull requestを受け取るたびに、通常のコミットと同じように[Travis CI](https://travis-ci.org/)がそのpull requestをビルドするだろう。どう設定するかは[Travis CI: Getting started](http://docs.travis-ci.com/user/getting-started/)を読むと良い。

[![Travis CI status](https://cloud.githubusercontent.com/assets/1687642/2700187/3a88838c-c410-11e3-9a46-e65e2a0458cd.png)](https://github.com/octokit/octokit.rb/pull/452)

[*コミット・ステータスAPIについてもっと詳しく*](https://github.com/blog/1227-commit-status-api)

### 絞り込み検索
issueとpull requestの検索インターフェイスでは、絞り込みをかけることが可能だ。

例えば[Railsのリポジトリー](https://github.com/rails/rails/issues)では、以下の様な絞り込み検索により"activerecord"というラベルがついたissueのみを表示することができる:

`is:issue label:activerecord`

逆に"activerecord"というラベルが*ついていない*issueのみを表示することもできる:

`is:issue -label:activerecord`

そして、この絞り込み検索はpull requestに対しても行うことができる:

`is:pr -label:activerecord`

GitHubでは開かれているissueやpull requestのみを表示するタブ、または既に閉じられたそれらのみを表示するタブが用意されているが、絞り込み検索によってマージ済みのpull requestのみを表示することもできる。以下のようなフィルターを使えば良いだろう:

`is:merged`

[*issueの検索についてもっと詳しく*](https://help.github.com/articles/searching-issues)

そしてGitHubはStatus APIの結果を使ってフィルターすることもできるようになった。

Status APIでsuccessが設定されたpull requestのみ:

`status:success`

[*Status APIを使った絞り込み検索についてもっと詳しく*](https://github.com/blog/2014-filter-pull-requests-by-status)

### Markdownファイルでの構文強調
例えばMarkdownファイルでRubyのコードを構文強調したいならば以下のようにする:

    ```ruby
    require 'tabbit'
    table = Tabbit.new('Name', 'Email')
    table.add_row('Tim Green', 'tiimgreen@gmail.com')
    puts table.to_s
    ```

こうすると以下のように表示されることになる:

```ruby
require 'tabbit'
table = Tabbit.new('Name', 'Email')
table.add_row('Tim Green', 'tiimgreen@gmail.com')
puts table.to_s
```

GitHubでは[Linguist](https://github.com/github/linguist)を使って言語を判別し構文強調を行っている。構文強調がサポートされている言語の一覧は[言語定義YAMLファイル](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)を参照すればわかるだろう。

[*GitHub Flavored Markdownについてもっと詳しく*](https://help.github.com/articles/github-flavored-markdown)

### Emoji
Emojiはpull requestやissue、コミット・メッセージ、リポジトリーの概要などで`:name_of_emoji:`と書くと利用できる:

GitHubでサポートされているEmojiの完全なリストは[Emoji cheat sheet for Campfire and GitHub](http://www.emoji-cheat-sheet.com/)か[All-Github-Emoji-Icons](https://github.com/scotch-io/All-Github-Emoji-Icons)で確認できる。
素敵なemojiの検索は[emoji.muan.co](http://emoji.muan.co/)。

GitHubで使われているEmojiのトップ5は以下の通りだ:

1. `:shipit:`
2. `:sparkles:`
3. `:-1:`
4. `:+1:`
5. `:clap:`

### 画像及びアニメーションGIF
画像やアニメーションGIFはコミットのコメントやREADMEなどで利用できる:

```
![Alt Text](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)
```

リポジトリにある画像も直接参照することが出来る:

```
![Alt Text](https://github.com/{user}/{repo}/raw/master/path/to/image.gif)
```

![Peter don't care](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)

あらゆる画像はGitHubでキャッシュされるので、画像のホスティング先が落ちていたとしても変わらず表示されるだろう。

#### GitHub Wikiへの画像の添付
GitHub Wikiで画像を追加する方法がいくつかある。通常のMarkdown記法（前節を参照）はもちろん使える。しかしそれだけではなく、画像の幅と高さを指定する記法も使うことができる:

```markdown
[[ http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif | height = 100px ]]
```

こうすると以下のようになる:

![Just a screenshot](http://i.imgur.com/J5bMf7S.png)

### 素早く引用
issueのスレッドで他の人のコメントを引用してコメントしたい場合、引用したい文章を選択した状態で`r`を押すと、ブロック引用の記法を使ってテキストエリアにコピーされる。

![Quick Quote](http://i.imgur.com/TzpMIOA.png)

[*素早く引用する方法についてもっと詳しく*](https://github.com/blog/1399-quick-quotes)

### コメントへのクリップボードの画像の追加

_(Chrome系のブラウザーのみで動作)_

スクリーンショットをクリップボードに保存(mac: `cmd-ctrl-shift-4`)した後、その画像はコメント投稿フォームで貼り付け(`cmd-v`または`ctrl-v`)ることができ、自動的にGitHubへアップロードされます。

![Pasting Clipboard Image to Comments](https://cloud.githubusercontent.com/assets/39191/5794265/39c9b65a-9f1b-11e4-9bc7-04e41f59ea5f.png)

[*コメントへのクリップボードの画像の追加についてもっと詳しく*](https://help.github.com/articles/issue-attachments)

### 設定済みライセンスの追加
GitHub上でリポジトリを作成する時、あらかじめ設定されているライセンスを追加することもできる:

![Licese](http://i.imgur.com/Chqj4Fg.png)

既に存在するリポジトリであってもウェブ上のインターフェイスからファイルを作成することで追加できる。`LICENSE`というファイル名にした場合、ライセンスを選択するオプションが表示されるのだ:

![License](http://i.imgur.com/fTjQict.png)

`.gitignore`も同じように作成時に追加することも、後で追加することもできる。

[*オープンソース・ライセンスについてもっと詳しく*](https://help.github.com/articles/open-source-licensing)

### タスクリスト
issueやpull requestでは以下のように（空白に注意）書くとチェックボックスを作成することができる:

```
- [ ] Be awesome
- [ ] Prepare dinner
  - [ ] Research recipe
  - [ ] Buy ingredients
  - [ ] Cook recipe
- [ ] Sleep
```

![Task List](http://i.imgur.com/jJBXhsY.png)

これらチェックボックスにチェックが入れられると、同時にMarkdownソースも更新される:

```
- [x] Be awesome
- [ ] Prepare dinner
  - [x] Research recipe
  - [x] Buy ingredients
  - [ ] Cook recipe
- [ ] Sleep
```

[*タスク・リストについてもっと詳しく*](https://help.github.com/articles/writing-on-github#task-lists)

#### Markdownファイルでのタスクリスト
通常のMarkdownファイルでも**読み取り専用**のチェックリストを以下のような記法で追加することができる:

```
- [ ] Mercury
- [x] Venus
- [x] Earth
- [x] Mars
- [ ] Jupiter
```

- [ ] Mercury
- [x] Venus
- [x] Earth
- [x] Mars
- [ ] Jupiter

[*Markdownファイルでのタスクリストについてもっと詳しく*](https://github.com/blog/1825-task-lists-in-all-markdown-documents)

### 相対リンク
Markdownファイルでリポジトリ内のコンテンツへ張る場合、相対リンクを利用することが推奨されている。

```markdown
[Link to a header](#awesome-section)
[Link to a file](docs/readme)
```

絶対リンクはURLの変更（例: リポジトリのリネーム、ユーザー名の変更、プロジェクトのフォーク）により更新される。相対リンクを利用すれば、そのままうまく機能するはずだ。

[*相対リンクについてもっと詳しく*](https://help.github.com/articles/relative-links-in-readmes)

### GitHub Pagesでのメタデータとプラグインのサポート
Jekyllのページや投稿ではリポジトリの情報が`site.github`という名前空間に格納されており、例えば`{{ site.github.project_title }}`などと書けば表示することができる。

また、Jemojiとjekyll-mentionsというプラグインがインストールされているので、[Emoji](#emoji)や[@mentions](https://github.com/blog/821)はJekyllの投稿やページでGitHub.com上と同じように動作する。

[*GitHub Pageでのメタデータとプラグインのサポートについてもっと詳しく*](https://github.com/blog/1797-repository-metadata-and-plugin-support-for-github-pages)

### 文書内のYAMLメタデータ
[Jekyll](http://jekyllrb.com/)を[GitHub Pages](http://pages.github.com/)で利用している場合など、多くのブログではYAML形式のメタデータをその記事の先頭に書く必要がある。GitHubではこういったメタデータを読みやすいように表として表示してくれる:

![YAML metadata](https://camo.githubusercontent.com/47245aa16728e242f74a9a324ce0d24c0b916075/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f36343035302f313232383236372f65303439643063362d323761302d313165332d396464382d6131636432323539393334342e706e67)

[*文書内のYAMLメタデータの表示についてもっと詳しく*](https://github.com/blog/1647-viewing-yaml-metadata-in-your-documents)

### 表形式のデータ表示
GitHubでは`.csv`（カンマ区切り）と`.tsv`（タブ区切り）の形式で書かれた表を整形して表示する機能をサポートしている。

![Tabular data](https://camo.githubusercontent.com/1b6dd0157ffb45d9939abf14233a0cb13b3b4dfe/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f3238323735392f3937363436322f33323038336463652d303638642d313165332d393262322d3566323863313061353035392e706e67)

[*表形式のデータ表示についてもっと詳しく*](https://github.com/blog/1601-see-your-csvs)

### PDF表示
GitHubではPDFの表示をサポートしている:

![PDF](https://cloud.githubusercontent.com/assets/1000669/7492902/f8493160-f42e-11e4-8cea-1cb4f02757e7.png)

[*PDF表示についてもっと詳しく*](https://github.com/blog/1974-pdf-viewing)

### pull requestの取り消し
pull requestをマージした後、意味がなかったことがわかったり、そのpull requestをマージしたのは間違いだったことがわかることもあるだろう。

その取り消しは、pull requestのページに表示されているマージ・コミットの右端にある**Revert**ボタンをクリックすることにより、そのpull requestで行われた変更を取り消すpull requestを作成することによって行うことができる。

![Revert button](https://camo.githubusercontent.com/0d3350caf2bb1cba53123ffeafc00ca702b1b164/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f68656c702f70756c6c5f72657175657374732f7265766572742d70756c6c2d726571756573742d6c696e6b2e706e67)

[*pull requestの取り消しについてもっと詳しく*](https://github.com/blog/1857-introducing-the-revert-button)

### 差分の表示
#### レンダリング済みの差分表示
コミットやpull requestにGitHubでレンダリングされて表示されるもの（例: Markdown）が含まれる場合、その*ソース*と*レンダリング済み*の両方の差分を見ることができる。

![Source / Rendered view](https://github-images.s3.amazonaws.com/help/repository/rendered_prose_diff.png)

レンダリングされた状態での差分を表示したい場合は「Rendered」ボタンをクリックする。レンダリング済みの差分表示では文章の追加や削除、編集がよりわかりやすい:

![Rendered Prose Diffs](https://f.cloud.github.com/assets/17715/2003056/3997edb4-862b-11e3-90be-5e9586edecd7.png)

[*レンダリング済みの差分表示についてもっと詳しく*](https://github.com/blog/1784-rendered-prose-diffs)

#### マップ差分の可視化
コミットやpull requestにジオデータの変更が含まれている場合はいつも、GitHubではそのジオデータの変化を可視化してくれるだろう。

[![Diffable Maps](https://f.cloud.github.com/assets/282759/2090660/63f2e45a-8e97-11e3-9d8b-d4c8078b004e.gif)](https://github.com/benbalter/congressional-districts/commit/2233c76ca5bb059582d796f053775d8859198ec5)

[*マップ差分の可視化についてもっと詳しく*](https://github.com/blog/1772-diffable-more-customizable-maps)

#### 差分表示の前後を表示
差分表示の行番号付近にある*展開*ボタンを使うと、その前後の行をクリックして表示させることができる。*展開*ボタンを押し続けることによってファイル全体を表示することもできるし、またこの機能はあらゆるGitHubの差分表示ビューに用意されている。

![Expanding Context in Diffs](https://f.cloud.github.com/assets/22635/1610539/863c1f64-5584-11e3-82bf-151b406a272f.gif)

[*差分表示の前後を表示についてもっと詳しく*](https://github.com/blog/1705-expanding-context-in-diffs)

#### pull requestの内容をDIFFまたはPATCH形式で取得
pull requestによる差分はそのURLの末尾に`.diff`または`.patch`を追加すると、それぞれの形式で取得することができる。例えば:

```
https://github.com/tiimgreen/github-cheat-sheet/pull/15
https://github.com/tiimgreen/github-cheat-sheet/pull/15.diff
https://github.com/tiimgreen/github-cheat-sheet/pull/15.patch
```

拡張子`.diff`を追加した場合、このようなプレーンテキストで表示されるだろう:

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

#### 画像の表示とDIFF
GitHubは、PNGやJPG、GIF、PSDといった多くの一般的な画像形式の表示をサポートしている。それに加え、様々な方法でこれら画像形式のバージョンごとの差分を比較することもできる。

[![Diffable PSD](https://cloud.githubusercontent.com/assets/2546/3165594/55f2798a-eb56-11e3-92e7-b79ad791a697.gif)](https://github.com/blog/1845-psd-viewing-diffing)

[*画像の表示とDIFFについてもっと詳しく*](https://help.github.com/articles/rendering-and-diffing-images)

### Hub
[Hub](https://github.com/github/hub)はGitのラッパーとして機能するコマンドライン・ツールで、これを利用するとGitHubをコマンドラインからとても簡単に扱えるようになる。

例えば以下のようにしてリポジトリのクローンが行える:

```bash
$ hub clone tiimgreen/toc
```

これが以下のコマンドの代わりというわけだ:

```bash
$ git clone https://github.com/tiimgreen/toc.git
```

[*Hubが提供する便利な機能についてもっと詳しく*](https://github.com/github/hub#commands)

### 開発参加のガイドライン
リポジトリのルートに`CONTRIBUTING`という名前のファイルを置くと、issueやpull requestを作成しようとした時にそれへのリンクが表示されるようになる。

![Contributing Guidelines](https://camo.githubusercontent.com/71995d6b0e620a9ef1ded00a04498241c69dd1bf/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f736b697463682f6973737565732d32303132303931332d3136323533392e6a7067)

[*開発参加のガイドラインについてもっと詳しく*](https://github.com/blog/1184-contributing-guidelines)

### Octicons
GitHubで使われているアイコン（Octicons）はオープンソース化された。

![Octicons](https://og.github.com/octicons/octicons@1200x630.png)

[*GitHubのOcticonsについてもっと詳しく*](https://octicons.github.com)

### GitHub情報
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
### すべての削除済みファイルをワーキング・ツリーから削除する
例えば`/bin/rm`を使って大量のファイルを削除した場合、以下のコマンドを使えばワーキング・ツリー、そしてインデックスからも削除することができ、ファイルごとにそれぞれGitコマンドを実行する必要がなくなる:

```bash
$ git rm $(git ls-files -d)
```

例えば以下のように実行される:

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

### 直前のブランチ
Gitで直前のブランチへ移動するには:

```bash
$ git checkout -
# Switched to branch 'master'

$ git checkout -
# Switched to branch 'next'

$ git checkout -
# Switched to branch 'master'
```

[*Gitのブランチ操作についてもっと詳しく*](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)

### 空白の削除
Gitの`stripspace`コマンドは以下の作業を行う:

- 行末の空白文字の削除
- 空白行の取りまとめ
- ファイル末尾への改行の追加

このコマンドを呼ぶ時はファイルを渡さねばならない。例:

```bash
$ git stripspace < README.md
```

[*Gitの`stripspace`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-stripspace)

### SSH公開鍵
以下のURLにアクセスすることで、SSH公開鍵の一覧をテキスト形式で取得することができる:

```
https://github.com/{user}.keys
```

例: [https://github.com/tiimgreen.keys](https://github.com/tiimgreen.keys)

[*SSH公開鍵についてもっと詳しく*](https://changelog.com/github-exposes-public-ssh-keys-for-its-users/)

### pull requestのチェックアウト
pull requestはGitHubのリポジトリでは特別なブランチであり、様々な方法でローカルに取り込むことができる:

特定のpull requestを取り込み、一時的に`FETCH_HEAD`として保存すると、素早く差分を確認してマージすることが可能だ:

```bash
$ git fetch origin refs/pull/[PR-Number]/head
```

参照仕様を使うとすべてのpull requestをローカル・ブランチとして取り込むことができる:

```bash
$ git fetch origin '+refs/pull/*/head:refs/remotes/origin/pr/*'
```

リポジトリの`.git/config`に以下の行を追加すれば自動的にpull requestを落とすようにもできるだろう:

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

フォークされてから送られてきたpull requestに対しては、そのpull requestを参照するリモート・ブランチから直接ローカル・ブランチとしてチェックアウトすると便利だろう:

```bash
$ git checkout pr/42 pr-42
```

もしくは様々なリポジトリで作業をするのなら、代わりにグローバルのGit設定で行うことにより、pull requestの取得をグローバルに設定すると良いだろう。

```bash
git config --global --add remote.origin.fetch "+refs/pull/*/head:refs/remotes/origin/pr/*"
```

こうすると以下の様な短いコマンドを利用することが可能になる:

```bash
git fetch origin
```

```bash
git checkout pr/42
```

[*pull requestのチェックアウトについてもっと詳しく*](https://help.github.com/articles/checking-out-pull-requests-locally)

### 空のコミット
`--allow-empty`オプションを付けると、コードの変化がなくてもコミットを作成することができる:

```bash
$ git commit -m "Big-ass commit" --allow-empty
```

この機能の使い方（便利なもの）としては以下のようなものが挙げられる:

 - 新たな機能や大きな変更を事前に通知する時
 - コード上に現れないような変更をプロジェクトに加えた時
 - リポジトリを利用して誰かと連絡を取りたい時
 - リポジトリへの最初のコミットをやり直しできるようにしたい時: `git commit -m "init repo" --allow-empty`.

### Gitステータスのスタイリング
普通に実行すると:

```bash
$ git status
```

このように表示されるが:

![git status](http://i.imgur.com/qjPyvXb.png)

`-sb`を追加することによって:

```bash
$ git status -sb
```

このように表示することもできる:

![git status -sb](http://i.imgur.com/K0OY3nm.png)

[*Gitの`status`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-status)

### Gitログのスタイリング
以下のように実行すると:

```bash
$ git log --all --graph --pretty=format:'%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
```

このように表示される:

![git log --all --graph --pretty=format:'%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative](http://i.imgur.com/58eOtkW.png)

この設定は[Palesz](http://stackoverflow.com/users/88355/palesz)が考えたものだ。

*これは[後述の手順](#%E3%82%A8%E3%82%A4%E3%83%AA%E3%82%A2%E3%82%B9)に従ってエイリアスへ追加することもできる。*

[*Gitの`log`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-log)

### コミットログの検索
指定した文字列を今までのコミット・メッセージから検索して、もっとも新しいものを表示することができる。

```bash
$ git show :/query
```

`query`を検索したい文字列（大文字と小文字を区別する）で置き換えると、最新のコミットがそのコミットにおける差分と同時に表示される。

```bash
$ git show :/typo
```
![git show :/query](http://i.imgur.com/icaGiNt.png)

注: 終了するには`q`を押す。

### Git Grep
Git Grepは指定したパターンに一致する行の一覧を返してくれる。

実行すると:

```bash
$ git grep aliases
```

*aliases*という文字を含むファイルを全て表示することだろう。

![git grep aliases](http://i.imgur.com/DL2zpQ9.png)

注: 終了するには`q`を押す。

複数のフラグを組み合わせることで、より高度な検索を行うことができる。例えば:

 * `-e` 次のパラメーターをパターンとする (例: regex)
 * `--and`、`--or`と`--not` 複数のパターンを組み合わせる

以下のようにして使う:

```bash
$ git grep -e pattern --and -e anotherpattern
```

[*Gitの`grep`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-grep)

### マージ済みブランチ
以下のように実行すると:

```bash
$ git branch --merged
```

現在のブランチに既にマージされたブランチの一覧が表示される。

逆に:

```bash
$ git branch --no-merged
```

こうするとまだマージされていないブランチが表示されるだろう。

[*Gitの`branch`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-branch)

### FixupとAutosquash
これまでのコミット(HEADの直前でなくても構わない)、例えば`abcde`というチェックサムのコミットで何か問題を見つけた場合、以下の様なコマンドで問題の修正を行うことができる:

```bash
$ git commit --fixup=abcde
$ git rebase abcde^ --autosquash -i
```

[*Gitの`commit`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-commit)
[*Gitの`rebase`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-rebase)

### ローカル・リポジトリを参照するウェブサーバー
Gitの`instaweb`コマンドを利用すると、自分の作業リポジトリを`gitweb`で参照することができる。このコマンドは`gitweb`とウェブサーバーをセットアップしてローカル・リポジトリをブラウザーで開けるようにする簡単なスクリプトだ。

```bash
$ git instaweb
```

以下のようなページが開かれる:

![Git instaweb](http://i.imgur.com/Dxekmqc.png)

[*Gitの`instaweb`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-instaweb)

### Gitの設定
`.gitconfig`とはあらゆる設定が書き込まれるファイルだ。

#### エイリアス
エイリアスはGitの呼び出し方を自分で好きなように定義できるヘルパー機能だ。例えば`git a`で`git add --all`を実行するようにすることができる。

エイリアスを追加するには`~/.gitconfig`を開き、以下のような形式で記述していく:

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

またはコマンドラインからも設定できる:

```bash
$ git config --global alias.new_alias git_function
```

例:

```bash
$ git config --global alias.cm commit
```

注: エイリアスが複数のコマンドからなる場合はクオートで括る必要がある:

```bash
$ git config --global alias.ac 'add -A . && commit'
```

おすすめの設定を挙げておこう:

| エイリアス | コマンド | 設定方法 |
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

#### コマンドの自動修正
多分今は`git comit`とタイプした場合、以下のような出力を得ることだろう:

```bash
$ git comit -m "Message"
# git: 'comit' is not a git command. See 'git --help'.

# Did you mean this?
#   commit
```

これを`comit`とタイプした時に`commit`を実行させたい場合、自動修正を有効にすれば良い:

```bash
$ git config --global help.autocorrect 1
```

すると以下のような出力を得るようになるだろう:

```bash
$ git comit -m "Message"
# WARNING: You called a Git command named 'comit', which does not exist.
# Continuing under the assumption that you meant 'commit'
# in 0.1 seconds automatically...
```

#### 色設定
Gitの出力をカラフルにするには以下のような設定を加えると良い:

```bash
$ git config --global color.ui 1
```

[*Gitの`config`コマンドについてもっと詳しく*](http://git-scm.com/docs/git-config)

### Git情報
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
| GitHub Training Kit | http://training.github.com/kit |
| Git Visualization Playground | http://onlywei.github.io/explain-git-with-d3/#freeplay |

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

## 訳注
これは[GitHub Cheat Sheet](https://github.com/tiimgreen/github-cheat-sheet)の日本語訳である。
