# GitHub秘笈 [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
Git 和 Github 秘笈，靈感來自於 [Zach Holman](https://github.com/holman) 在 2012 年 Aloha Ruby Conference 和 2013 年 WDCNZ 上所做的演講：[Git and GitHub Secrets](http://www.confreaks.com/videos/1229-aloharuby2012-git-and-github-secrets)([slides](https://speakerdeck.com/holman/git-and-github-secrets)) 和 [More Git and GitHub Secrets](https://vimeo.com/72955426)([slides](https://speakerdeck.com/holman/more-git-and-github-secrets))。

*其他語言版本: [English](README.md), [한국어](README.ko.md), [日本語](README.ja.md), [簡體中文](README.zh-cn.md), [正體中文](README.zh-tw.md).*

# 目錄
  - [GitHub](#github)
    - [不比較空白字串](#不比較空白字串)
    - [調整 Tab 字串所代表的空格數](#調整-tab-字串所代表的空格數)
    - [查看某個使用者的 Commit 歷史](#查看某個使用者的-commit-歷史)
    - [倉庫複製](#倉庫複製)
    - [分支](#分支)
      - [將某個分支與其他所有分支進行比對](#將某個分支與其他所有分支進行比對)
      - [比較分支](#比較分支)
      - [比較不同派生庫的分支](#比較不同派生庫的分支)
    - [Gists](#gists)
    - [Git.io](#gitio)
    - [鍵盤快捷鍵](#鍵盤快捷鍵)
    - [整行高亮](#整行高亮)
    - [用 Commit 訊息關閉 Issue](#用-commit-訊息關閉-issue)
    - [連接其他倉庫的 Issue](#連接其他倉庫的-issue)
    - [鎖定項目對話功能](#鎖定項目對話功能)
    - [設置 CI 對每條 Pull Request 都進行構建](#設置-ci-對每條-pull-request-都進行構建)
    - [Markdown 文件語法高亮](#markdown-文件語法高亮)
    - [表情符號](#表情符號)
    - [圖片 / GIF 動畫](#圖片--gif-動畫)
      - [在 GitHub Wiki 中引用圖片](#在-github-wiki-中引用圖片)
    - [快速引用](#快速引用)
    - [複製貼上剪貼板中的圖片到評論](#複製貼上剪貼板中的圖片到評論)
    - [快速添加許可證文件](#快速添加許可證文件)
    - [任務列表](#任務列表)
      - [Markdown 文件中的任務列表](#markdown-文件中的任務列表)
    - [相對連接](#相對連接)
    - [GitHub Pages 的中繼資料與插件支持](#github-pages-的中繼資料與插件支持)
    - [查看 YAML 格式的中繼資料](#查看-yaml-格式的中繼資料)
    - [渲染表格數據](#渲染表格數據)
    - [撤銷 Pull Request](#撤銷-pull-request)
    - [Diffs](#diffs)
      - [可渲染文件的Diffs](#可渲染文件的diffs)
      - [可比較的地圖數據](#可比較的地圖數據)
      - [在 Diff 中展開查看更多的上下文](#在-diff-中展開查看更多的上下文)
      - [獲取 Pull Request 的 diff 或 patch 文件](#獲取-pull-request-的-diff-或-patch-文件)
      - [顯示圖片以及比較圖片](#顯示圖片以及比較圖片)
    - [Hub](#hub)
    - [貢獻者指南](#貢獻者指南)
    - [Octicons](#octicons)
    - [GitHub 資源](#github-資源)
      - [GitHub 相關演講視頻](#github-相關演講視頻)
  - [Git](#git)
    - [從工作區去除大量已刪除文件](#從工作區去除大量已刪除文件)
    - [上一個分支](#上一個分支)
    - [去除空白](#去除空白)
    - [SSH 金鑰](#ssh-金鑰)
    - [檢出 Pull Requests](#檢出-pull-requests)
    - [沒有任何改動的提交](#沒有任何改動的提交)
    - [美化 Git Status](#美化-git-status)
    - [美化 Git Log](#美化-git-log)
    - [Git 查詢](#git-查詢)
    - [Git Grep](#git-grep)
    - [合併分支](#合併分支)
    - [修復有問題的提交以及自動合併](#修復有問題的提交以及自動合併)
    - [以網站方式查看本地倉庫](#以網站方式查看本地倉庫)
    - [Git 設置](#git-設置)
      - [Git 命令自定義別名](#git-命令自定義別名)
      - [自動更正](#自動更正)
      - [顏色輸出](#顏色輸出)
    - [Git 資源](#git-資源)
      - [Git 參考書籍](#git-參考書籍)

## GitHub
### 不比較空白字串

在任意 diff 頁面的 UR L後加上 `?w=1`，可以去掉那些隻是空白字串的改動，使你能更專註於代碼改動。

![Diff without whitespace](https://camo.githubusercontent.com/797184940defadec00393e6559b835358a863eeb/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f776869746573706163652e706e67)

[*詳見 GitHub secrets.*](https://github.com/blog/967-github-secrets)

### 調整 Tab 字串所代表的空格數
在 diff 或文件的 URL 後面加上 `?ts=4` ，這樣當顯示 tab 字串的長度時就會是 4 個空格的長度，不再是默認的 8 個空格。 `ts` 後面的數字還可以根據你個人的偏好進行修改。這個技巧不適用於 Gists，或者以 Raw 格式查看文件， 但有瀏覽器擴展插件可以幫你自動調整: [Chrome 擴展](https://chrome.google.com/webstore/detail/github-tab-size/ofjbgncegkdemndciafljngjbdpfmbkn)。

下面以一個 Go 語言原始碼為例，看看在 URL 裡添加 `?ts=4` 參數的效果。添加前：

![Before, tab space example](http://i.imgur.com/GIT1Fr0.png)

... 添加後的樣子：

![After, tab space example](http://i.imgur.com/70FL4H9.png)

### 查看使用者的全部 Commit 歷史
在 Commits 頁面 URL 後加上 `?author={user}` 查看使用者全部的提交。

```
https://github.com/rails/rails/commits/master?author=dhh
```

![DHH commit history](http://i.imgur.com/S7AE29b.png)

[*深入了解提交視圖之間的區別*](https://help.github.com/articles/differences-between-commit-views)

### 倉庫複製
當複製倉庫時可以不要那個`.git`後綴。

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

[*更多對 Git `clone` 命令的介紹.*](http://git-scm.com/docs/git-clone)

### 分支
#### 將某個分支與其他所有分支進行比對

當你查看某個倉庫的分支（Branches）頁面（緊挨著 Commits 連接）時

```
https://github.com/{user}/{repo}/branches
```
你會看到一個包含所有未合併的分支的列表。

在這裡你可以訪問分支比較頁面或刪除某個分支。

![Compare branches not merged into master in rails/rails repo - https://github.com/rails/rails/branches](http://i.imgur.com/0FEe30z.png)

#### 比較分支

如果要在 GitHub 上直接比較兩個分支，可以使用如下形式的 URL ：

```
https://github.com/{user}/{repo}/compare/{range}
```

其中 `{range} = master...4-1-stable`

例如：

```
https://github.com/rails/rails/compare/master...4-1-stable
```

![Rails branch compare example](http://i.imgur.com/tIRCOsK.png)

`{range}` 參數還可以使用下面的形式:

```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```

*日期格式 `YYYY-DD-MM`*

![Another compare example](http://i.imgur.com/5dtzESz.png)

在 `diff` 和 `patch` 頁面裡也可以比較分支：

```
https://github.com/rails/rails/compare/master...4-1-stable.diff
https://github.com/rails/rails/compare/master...4-1-stable.patch
```

[*了解更多關於基於時間的 Commit 比較.*](https://help.github.com/articles/comparing-commits-across-time)

#### 比較不同派生庫的分支

想要對派生倉庫（Forked Repository）之間的分支進行比較，可以使用如下的 URL：

```
https://github.com/user/repo/compare/{foreign-user}:{branch}...{own-branch}
```

例如：

```
https://github.com/rails/rails/compare/byroot:master...master
```

![Forked branch compare](http://i.imgur.com/Q1W6qcB.png)

### Gists

[Gists](https://gist.github.com/) 方便我們管理代碼片段，不必使用功能齊全的倉庫。

![Gist](http://i.imgur.com/VkKI1LC.png?1)

Gist 的 URL 後加上 `.pibb`（[像這樣](https://gist.github.com/tiimgreen/10545817.pibb)）可以得到便於嵌入到其他網站 的 HTML 代碼。

Gists 可以像任何標準倉庫一樣被複製。

```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/BcFzabp.png)

這意味著你可以像 Github 倉庫一樣修改和更新 Gists :

```bash
$ git commit
$ git push
Username for 'https://gist.github.com':
Password for 'https://tiimgreen@gist.github.com':
```

但是， Gists 不支持目錄。所有文件都必須添加在倉庫的根目錄下。
[*進一步了解如何建立 Gists.*](https://help.github.com/articles/creating-gists)

### Git.io
[Git.io](http://git.io)是 Github 的短網址服務。

![Git.io](http://i.imgur.com/6JUfbcG.png?1)

你可以通過 Curl 命令以普通 HTTP 協議使用它：

```bash
$ curl -i http://git.io -F "url=https://github.com/..."
HTTP/1.1 201 Created
Location: http://git.io/abc123

$ curl -i http://git.io/abc123
HTTP/1.1 302 Found
Location: https://github.com/...
```

[*進一步了解 Git.io.*](https://github.com/blog/985-git-io-github-url-shortener)

### 鍵盤快捷鍵

在倉庫頁面上提供了快捷鍵方便快速導航。

 - 按 `t` 鍵打開一個文件瀏覽器。
 - 按 `w` 鍵打開分支選擇菜單。
 - 按 `s` 鍵聚焦游標到當前倉庫的搜索框。此時按刪除鍵就會從搜索當前倉庫切換到搜索整個 Github 網站。
 - 按 `l` 鍵編輯 Issue 列表頁的標籤。
 - **查看文件內容時**（如：`https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`），按 `y` 鍵將會凍結這個頁面，這樣就算代碼被修改了也不會影響你當前看到的。

按`?`查看當前頁面支持的快捷鍵列表：

![Keyboard shortcuts](http://i.imgur.com/y5ZfNEm.png)

[*進一步了解可用的搜索語法.*](https://help.github.com/articles/search-syntax/)

### 整行高亮

在代碼文件地址 URL 後加上`#L52`或者單擊行號 52 都會將第 52 行代碼高亮顯示。

多行高亮也可以，比如用`#L53-L60`選擇範圍，或者按住 `shift` 鍵，然後再點擊選擇的兩行。

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![整行高亮](http://i.imgur.com/8AhjrCz.png)

### 用 Commit 訊息關閉 Issue

如果某個提交修復了一個 Issue，當提交到 master 分支時，提交訊息裡可以使用 `fix/fixes/fixed`, `close/closes/closed` 或者 `resolve/resolves/resolved` 等關鍵詞，後面再跟上 Issue 號，這樣就會關閉這個 Issue 。

```bash
$ git commit -m "Fix screwup, fixes #12"
```

這將會關閉 Issue #12，並且在 Issue 討論列表裡關聯引用這次提交。

![Closing Repo](http://i.imgur.com/Uh1gZdx.png)

[*進一步了解通過提交訊息關閉 Issue.*](https://help.github.com/articles/closing-issues-via-commit-messages)

### 連接其他倉庫的 Issue
如果你想引用到同一個倉庫中的一個 Issue，隻需使用井號 `#` 加上 Issue 號，這樣就會自動建立到此 Issue 的連接。

要連接到其他倉庫的 Issue ，就使用`{user}/{repo}#ISSUE_NUMBER`的方式，例如`tiimgreen/toc#12`。

![Cross-Link Issues](https://camo.githubusercontent.com/447e39ab8d96b553cadc8d31799100190df230a8/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f7265666572656e6365732e706e67)

### 鎖定項目對話功能
現在倉庫的管理員和合作者可以將 Pull Requests 和 Issue 的評論功能關閉。

![Lock conversation](https://cloud.githubusercontent.com/assets/2723/3221693/bf54dd44-f00d-11e3-8eb6-bb51e825bc2c.png)

這樣，不是項目合作者的使用者就不能在這個項目上使用評論功能。

![Comments locked](https://cloud.githubusercontent.com/assets/2723/3221775/d6e513b0-f00e-11e3-9721-2131cb37c906.png)

[*進一步了解對話鎖定功能.*](https://github.com/blog/1847-locking-conversations)

### 設置 CI 對每條 Pull Request 都進行構建
如果設置正確，[Travis CI](https://travis-ci.org/) 會為每個你收到的 Pull Request 執行構建，就像每次提交也會觸發構建一樣。想了解更多關於 Travis CI 的訊息，請參考 [Travis CI入門](http://docs.travis-ci.com/user/getting-started/)。

[![Travis CI status](https://cloud.githubusercontent.com/assets/1687642/2700187/3a88838c-c410-11e3-9a46-e65e2a0458cd.png)](https://github.com/octokit/octokit.rb/pull/452)

[*進一步了解提交狀態 API.*](https://github.com/blog/1227-commit-status-api)

### Markdown 文件語法高亮
例如，可以像下面這樣在你的 Markdown 文件裡為 Ruby 代碼添加語法高亮：

    ```ruby
    require 'tabbit'
    table = Tabbit.new('Name', 'Email')
    table.add_row('Tim Green', 'tiimgreen@gmail.com')
    puts table.to_s
    ```

效果如下：

```ruby
require 'tabbit'
table = Tabbit.new('Name', 'Email')
table.add_row('Tim Green', 'tiimgreen@gmail.com')
puts table.to_s
```

Github使用 [Linguist](https://github.com/github/linguist) 做語言識別和語法高亮。你可以仔細閱讀 [languages YAML file](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)，了解有哪些可用的關鍵字。

[*進一步了解 GitHub Flavored Markdown.*](https://help.github.com/articles/github-flavored-markdown)

### 表情符號

可以在 Pull Requests, Issues, 提交消息, Markdown 文件裡加入表情符號。使用方法 `:name_of_emoji:`

```
:smile:
```
將輸出一個笑臉：

:smile:

Github 支持的完整表情符號號列表詳見[emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com/) 或 [scotch-io/All-Github-Emoji-Icons](https://github.com/scotch-io/All-Github-Emoji-Icons)。

Github 上使用最多的5個表情符號號是：

1. `:shipit:`
2. `:sparkles:`
3. `:-1:`
4. `:+1:`
5. `:clap:`

### 圖片 / GIF 動畫
註解和README等文件裡也可以使用圖片和 GIF 動畫：

```
![Alt Text](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)
```

倉庫中的圖片可以被直接引用：

```
![Alt Text](https://github.com/{user}/{repo}/raw/master/path/to/image.gif)
```

![Peter don't care](http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif)

所有圖片都緩存在 Github，不用擔心你的網站不能訪問時就看不到圖片了。

#### 在 GitHub Wiki 中引用圖片
有多種方法可以在 Wiki 頁面裡嵌入圖片。既可以像上一條裡那樣使用標準的 Markdown 語法，也可以像下面這樣指定圖片的高度或寬度：

```markdown
[[ http://www.sheawong.com/wp-content/uploads/2013/08/keephatin.gif | height = 100px ]]
```
結果：

![Just a screenshot](http://i.imgur.com/J5bMf7S.png)

### 快速引用
在主題評論中引用之前某個人所說的，只需選中文件，然後按 `r` 鍵，想要的就會以引用的形式複製到你的輸入框裡。

![Quick Quote](https://f.cloud.github.com/assets/296432/124483/b0fa6204-6ef0-11e2-83c3-256c37fa7abc.gif)

[*進一步了解快速引用.*](https://github.com/blog/1399-quick-quotes)

### 複製貼上剪貼板中的圖片到評論

_（僅適用於 Chrome 瀏覽器）_

當截屏圖片複製到剪貼板後（mac 上用 `cmd-ctrl-shift-4`），你可以用(`cmd-v / ctrl-v`)把圖片複製貼上到評論框裡，然後它就會自動上傳到 Github。

![Pasting Clipboard Image to Comments](https://cloud.githubusercontent.com/assets/39191/5794265/39c9b65a-9f1b-11e4-9bc7-04e41f59ea5f.png)

[*進一步了解在 issue 中使用附件*](https://help.github.com/articles/issue-attachments)


### 快速添加許可證文件
建立一個倉庫時，Github會為你提供一個預設的軟體授權條款：

![License](http://i.imgur.com/Chqj4Fg.png)

對於已有的倉庫，可以通過 web 界面建立文件來添加軟體授權條款。輸入`LICENSE`作為文件名後，同樣可以從預設的列表中選擇一個作為模板。

![License](http://i.imgur.com/fTjQict.png)

這個技巧也適用於 `.gitignore` 文件。

[*進一步了解開源許可證*](https://help.github.com/articles/open-source-licensing)

### 任務列表
Issues 和 Pull requests 裡可以添加複選框，語法如下（註意空白符）：

```
- [ ] Be awesome
- [ ] Prepare dinner
  - [ ] Research recipe
  - [ ] Buy ingredients
  - [ ] Cook recipe
- [ ] Sleep
```

![Task List](http://i.imgur.com/jJBXhsY.png)

當項目被選中時，它對應的 Markdown 原始碼也被更新了：

```
- [x] Be awesome
- [ ] Prepare dinner
  - [x] Research recipe
  - [x] Buy ingredients
  - [ ] Cook recipe
- [ ] Sleep
```

[*進一步了解任務列表.*](https://help.github.com/articles/writing-on-github#task-lists)

#### Markdown 文件中的任務列表

在完全符合Markdown語法的文件中可以使用以下語法加入一個**只讀**的任務列表


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

[*進一步了解 Markdown 文件中的任務列表*](https://github.com/blog/1825-task-lists-in-all-markdown-documents)

### 相對連接
Markdown文件裡連接到內部內容時推薦使用相對連接。

```markdown
[Link to a header](#awesome-section)
[Link to a file](docs/readme)
```
絕對連接會在 URL 改變時（例如重新命名倉庫、使用者名稱改變，建立分支項目）被更新。使用相對連接能夠保證你的文件不受此影響。

[*進一步了解相對連接.*](https://help.github.com/articles/relative-links-in-readmes)

### GitHub Pages 的中繼資料與插件支持
在 Jekyll 頁面和文章裡，倉庫訊息可在 `site.github` 命名空間下找到，也可以顯示出來，例如，使用 `{{ site.github.project_title }}`顯示項目標題。

Jemoji 和 jekyll-mentions 插件為你的 Jekyll 文章和頁面增加了[emoji](#emojis)和[@mentions](https://github.com/blog/821)功能。

[*了解更多 GitHub Pages 的中繼資料和插件支持.*](https://github.com/blog/1797-repository-metadata-and-plugin-support-for-github-pages)

### 查看 YAML 格式的中繼資料
許多博客網站，比如基於 [Jekyll](http://jekyllrb.com/)的[GitHub Pages](http://pages.github.com/) ，都依賴於一些文章頭部的 YAML 格式的中繼資料。 Github 會將其渲染成一個水平表格，方便閱讀。

![YAML metadata](https://camo.githubusercontent.com/47245aa16728e242f74a9a324ce0d24c0b916075/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f36343035302f313232383236372f65303439643063362d323761302d313165332d396464382d6131636432323539393334342e706e67)

[*進一步了解 在文件裡查看 YAML 中繼資料.*](https://github.com/blog/1647-viewing-yaml-metadata-in-your-documents)

### 渲染表格數據

GitHub 支持將 `.csv` (逗號分隔)和 `.tsv` (定位點分隔)格式的文件渲染成表格數據。

![Tabular data](https://camo.githubusercontent.com/1b6dd0157ffb45d9939abf14233a0cb13b3b4dfe/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f3238323735392f3937363436322f33323038336463652d303638642d313165332d393262322d3566323863313061353035392e706e67)

[*進一步了解渲染表格數據.*](https://github.com/blog/1601-see-your-csvs)

### 撤銷 Pull Request
合併一個 Pull Request 之後，你可能會反悔：要麼是這次 Pull Request 沒什麼用處，要麼是還不到合併的時候。

此時可以通過 Pull Request 中的 Revert 按鈕來撤銷一個已合併的 Pull Request 中的 commit。按下按鈕後將自動生成一個進行逆操作的 Pull Request。

![Revert button](https://camo.githubusercontent.com/0d3350caf2bb1cba53123ffeafc00ca702b1b164/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f68656c702f70756c6c5f72657175657374732f7265766572742d70756c6c2d726571756573742d6c696e6b2e706e67)

[*進一步了解「撤銷」按鈕](https://github.com/blog/1857-introducing-the-revert-button)

### Diffs
#### 可渲染文件的Diffs

Commit 和 Pull Request 裡包含有 Github 支持的可渲染文件（比如 Markdown）會提供*source* 和 *rendered* 兩個視圖功能。

![Source / Rendered view](https://github-images.s3.amazonaws.com/help/repository/rendered_prose_diff.png)

點擊 "rendered" 按鈕，看看改動在渲染後的顯示效果。當你添加、刪除或修改文件時，渲染純文件視圖非常方便。

![Rendered Prose Diffs](https://f.cloud.github.com/assets/17715/2003056/3997edb4-862b-11e3-90be-5e9586edecd7.png)

[*進一步了解渲染純文件視圖Diffs.*](https://github.com/blog/1784-rendered-prose-diffs)

#### 可比較的地圖數據
當你在GitHub上查看一個包含地理數據的 commit 或 pull request時，Github 將以可視化的方式比對版本之間的差異。

[![Diffable Maps](https://f.cloud.github.com/assets/282759/2090660/63f2e45a-8e97-11e3-9d8b-d4c8078b004e.gif)](https://github.com/benbalter/congressional-districts/commit/2233c76ca5bb059582d796f053775d8859198ec5)

[*進一步了解可比較的地圖數據.*](https://github.com/blog/1772-diffable-more-customizable-maps)

#### 在 Diff 中展開查看更多的上下文
你可以通過點擊 diff 邊欄裡的 *unfold* 按鈕來多顯示幾行上下文。你可以一直點擊 *unfold* 按鈕直到顯示了文件的全部內容。這個功能在所有 GitHub 的 diff 功能中都可以使用。

![Expanding Context in Diffs](https://f.cloud.github.com/assets/22635/1610539/863c1f64-5584-11e3-82bf-151b406a272f.gif)

[*進一步了解展開 Diff 上下文.*](https://github.com/blog/1705-expanding-context-in-diffs)

#### 獲取 Pull Request 的 diff 或 patch 文件
在 Pull Request 的 URL 後面加上 `.diff` 或 `.patch` 的擴展名就可以得到它的 diff 或 patch 文件，例如：

```
https://github.com/tiimgreen/github-cheat-sheet/pull/15
https://github.com/tiimgreen/github-cheat-sheet/pull/15.diff
https://github.com/tiimgreen/github-cheat-sheet/pull/15.patch
```
`.diff` 擴展會使用普通文件格式顯示如下內容：

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
#### 顯示圖片以及比較圖片
GitHub 可以顯示包括 PNG、JPG、GIF、PSD 在內的多種圖片格式並提供了幾種方式來比較這些格式的圖片文件版本間的不同。

[![Diffable PSD](https://cloud.githubusercontent.com/assets/2546/3165594/55f2798a-eb56-11e3-92e7-b79ad791a697.gif)](https://github.com/blog/1845-psd-viewing-diffing)

[*查看更多關於圖片顯示和比較*](https://help.github.com/articles/rendering-and-diffing-images)

### Hub
[Hub](https://github.com/github/hub) 是一個對 Git 進行了封裝的命令行工具，可以幫助你更方便的使用 Github。

例如可以像下面這樣進行複製：

```bash
$ hub clone tiimgreen/toc
```

[*查看更多 Hub 提供的超酷命令.*](https://github.com/github/hub#commands)

### 貢獻者指南

在倉庫的根目錄添加一個名為 `CONTRIBUTING` 的文件後，貢獻者在新建 Issue 或 Pull Request 時會看到一個指向這個文件的連接。

![Contributing Guidelines](https://camo.githubusercontent.com/71995d6b0e620a9ef1ded00a04498241c69dd1bf/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f736b697463682f6973737565732d32303132303931332d3136323533392e6a7067)

[*進一步了解貢獻者指南.*](https://github.com/blog/1184-contributing-guidelines)

### Octicons
GitHubs 圖標庫 (Octicons) 現已開源。

![Octicons](https://og.github.com/octicons/octicons@1200x630.png)

[*進一步了解 GitHub 圖標庫*](https://octicons.github.com)

### GitHub 資源
| 內容 | 連接 |
| ----- | ---- |
| 探索 GitHub | https://github.com/explore |
| GitHub 博客 | https://github.com/blog |
| GitHub 幫助 | https://help.github.com/ |
| GitHub 培訓 | http://training.github.com/ |
| GitHub 開發者 | https://developer.github.com/ |

#### GitHub 相關演講視頻
| 內容 | 連接 |
| ----- | ---- |
| How GitHub Uses GitHub to Build GitHub | https://www.youtube.com/watch?v=qyz3jkOBbQY |
| Introduction to Git with Scott Chacon of GitHub | https://www.youtube.com/watch?v=ZDR433b0HJY |
| How GitHub No Longer Works | https://www.youtube.com/watch?v=gXD1ITW7iZI |
| Git and GitHub Secrets | https://www.youtube.com/watch?v=Foz9yvMkvlA |
| More Git and GitHub Secrets | https://www.youtube.com/watch?v=p50xsL-iVgU |

## Git
### 從工作區去除大量已刪除文件
當用 `/bin/rm` 命令刪除了大量文件之後，你可以用下面一條命令從工作區和索引中去除這些文件，以免一個一個的刪除：

```bash
$ git rm $(git ls-files -d)
```

例如:

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

### 上一個分支
快速檢出上一個分支：

```bash
$ git checkout -
# Switched to branch 'master'

$ git checkout -
# Switched to branch 'next'

$ git checkout -
# Switched to branch 'master'
```

[*進一步了解 Git 分支.*](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)

### 去除空白

Git Stripspace 命令可以:

- 去掉行尾空白符
- 多個空行壓縮成一行
- 必要時在文件末尾增加一個空行

使用此命令時必須傳入一個文件，像這樣：

```bash
$ git stripspace < README.md
```

[*進一步了解 Git `stripspace` 命令.*](http://git-scm.com/docs/git-stripspace)

### SSH 金鑰

您可以藉由下面網址得到全部公開的 ssh 金鑰:

```
https://github.com/{user}.keys
```

範例：[https://github.com/tiimgreen.keys](https://github.com/tiimgreen.keys)

[*更多詳細 SSH 金鑰資訊...*](https://changelog.com/github-exposes-public-ssh-keys-for-its-users/)


### 檢出 Pull Requests

對 Github 倉庫來說，Pull Request 是種特殊分支， 可以通過以下多種方式取到本地：

取出某個特定的 Pull Request 並臨時作為本地的 `FETCH_HEAD` 中以便進行快速查看更改( diff )以及合併( merge )：

```bash
$ git fetch origin refs/pull/[PR-Number]/head
```

通過 refspec 獲取所有的 Pull Request 為本地分支：

```bash
$ git fetch origin '+refs/pull/*/head:refs/remotes/origin/pr/*'
```

或在倉庫的 `.git/config` 中加入下列設置來自動獲取遠程倉庫中的 Pull Request
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

對基於派生庫的 Pull Request，可以通過先 `checkout` 代表此 Pull Request 的遠端分支再由此分支建立一個本地分支：

```bash
$ git checkout pr/42 pr-42
```

操作多個倉庫的時候，可以在 Git 中設置獲取 Pull Request 的全局選項。

```bash
git config --global --add remote.origin.fetch "+refs/pull/*/head:refs/remotes/origin/pr/*"
```

此時可以在任意倉庫中使用以下命令：

```bash
 git fetch origin
```

```bash
git checkout pr/42
```


[*進一步了解如何本地檢出 pull request.*](https://help.github.com/articles/checking-out-pull-requests-locally)

### 沒有任何改動的提交
可以使用`--allow-empty`選項強製建立一個沒有任何改動的提交：

```bash
$ git commit -m "Big-ass commit" --allow-empty
```

這樣做在如下幾種情況下是有意義的：

 - 標記新的工作或一個新功能的開始。
 - 記錄對項目的跟代碼無關的改動。
 - 跟使用你倉庫的其他人交流。
 - 作為倉庫的第一次提交，因為第一次提交後不能被 rebase： `git commit -m "init repo" --allow-empty`.

### 美化 Git Status
在命令行輸入如下命令:

```bash
$ git status
```

可以看到:

![git status](http://i.imgur.com/qjPyvXb.png)

加上`-sb`選項:

```bash
$ git status -sb
```

這會得到:

![git status -sb](http://i.imgur.com/K0OY3nm.png)

[*進一步了解 Git `status` 命令.*](http://git-scm.com/docs/git-status)

### 美化 Git Log
輸入如下命令:

```bash
$ git log --all --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
```

可以看到:

![git log --all --graph --pretty=format:'%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative](http://i.imgur.com/58eOtkW.png)

這要歸功於 [Palesz](http://stackoverflow.com/users/88355/palesz) 在 stackoverflow 的回答。

*這個命令可以被用作別名，詳細做法見[這裡](#git%E5%91%BD%E4%BB%A4%E8%87%AA%E5%AE%9A%E4%B9%89%E5%88%AB%E5%90%8D)。*

[*進一步了解 Git `log` 命令.*](http://git-scm.com/docs/git-log)

### Git 查詢
Git 查詢運行你在之前的所有提交訊息裡進行搜索，找到其中和搜索條件相匹配的最近的一條。

```bash
$ git show :/query
```

這裡 `query` （區別大小寫）是你想要搜索的詞語， 這條命令會找到包含這個詞語的最後那個提交並顯示變動詳情。

```bash
$ git show :/typo
```
![git show :/query](http://i.imgur.com/icaGiNt.png)

* 按 `q` 鍵退出命令。*

### Git Grep

Git Grep 將顯示匹配字串的行號。

執行:

```bash
$ git grep aliases
```
會找出檔案內有出現 *aliases* 字串。

![git grep aliases](http://i.imgur.com/DL2zpQ9.png)

* 按 `q` 結束搜尋*

你也可以使用多重 flags 來達到進階搜尋。範例:

 * `-e` 下一個搜尋匹配條件 (e.g. regex)
 * `--and`, `--or` and `--not` 合併多重匹配字串.

使用如下：
```bash
 $ git grep -e pattern --and -e anotherpattern
```

[*更多詳細 Git `grep` 指令介紹*](http://git-scm.com/docs/git-grep)

### 合併分支

輸入命令:

```bash
$ git branch --merged
```

這會顯示所有已經合併到你當前分支的分支列表。

相反地：

```bash
$ git branch --no-merged
```

會顯示所有還沒有合併到你當前分支的分支列表。

[*進一步了解 Git `branch` 命令.*](http://git-scm.com/docs/git-branch)

### 修復有問題的提交以及自動合併
如果上一個或多個提交包含了錯誤，可以在你修復問題後使用下列命令處理（假設要修復的提交版本是`abcde`）：
```bash
$ git commit --fixup=abcde
$ git rebase abcde^ --autosquash -i
```
[*進一步了解 Git `commit` 命令.*](http://git-scm.com/docs/git-commit)
[*進一步了解 Git `rebase` 命令.*](http://git-scm.com/docs/git-rebase)

### 以網站方式查看本地倉庫
使用 Git 的 `instaweb` 可以立即在 `gitweb` 中瀏覽你的工作倉庫。這個命令是個簡單的腳本，設置了 `gitweb` 和用來瀏覽本地倉庫的Web服務器。*（譯者註：默認需要lighttpd支持）*

```bash
$ git instaweb
```

執行後打開：

![Git instaweb](http://i.imgur.com/Dxekmqc.png)

[*進一步了解 Git `instaweb` 命令.*](http://git-scm.com/docs/git-instaweb)

### Git 設置
所有 Git 設置都保存在你的 `.gitconfig` 文件中。

#### Git 命令自定義別名
別名用來幫助你定義自己的 git 命令。比如你可以定義 `git a` 來運行 `git add --all`。

要添加一個別名， 一種方法是打開 `~/.gitconfig` 文件並添加如下內容：

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

...或者在命令行裡鍵入：

```bash
$ git config --global alias.new_alias git_function
```

例如：

```bash
$ git config --global alias.cm commit
```

指向多個命令的別名可以用引號來定義：

```bash
$ git config --global alias.ac 'add -A . && commit'
```

下面列出了一些有用的別名：

| 別名 Alias | 命令 Command | 如何設置 What to Type |
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

#### 自動更正
如果鍵入 `git comit` 你會看到如下輸出：

```bash
$ git comit -m "Message"
# git: 'comit' is not a git command. See 'git --help'.

# Did you mean this?
#   commit
```

為了在鍵入 `comit` 調用 `commit`命令，隻需啟用自動糾錯功能：

```bash
$ git config --global help.autocorrect 1
```

現在你就會看到：

```bash
$ git comit -m "Message"
# WARNING: You called a Git command named 'comit', which does not exist.
# Continuing under the assumption that you meant 'commit'
# in 0.1 seconds automatically...
```

#### 顏色輸出
要在你的 Git 命令輸出裡加上顏色的話，可以用如下命令：

```bash
$ git config --global color.ui 1
```

[*進一步了解 Git `config` 命令.*](http://git-scm.com/docs/git-config)

### Git 資源
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

#### Git 參考書籍
| Title | Link |
| ----- | ---- |
| Pragmatic Version Control Using Git | http://www.pragprog.com/titles/tsgit/pragmatic-version-control-using-git |
| Pro Git | http://git-scm.com/book |
| Git Internals Pluralsight | https://github.com/pluralsight/git-internals-pdf |
| Git in the Trenches | http://cbx33.github.com/gitt/ |
| Version Control with Git | http://www.amazon.com/Version-Control-Git-collaborative-development/dp/1449316387 |
| Pragmatic Guide to Git | http://www.pragprog.com/titles/pg_git/pragmatic-guide-to-git |
| Git: Version Control for Everyone | http://www.packtpub.com/git-version-control-for-everyone/book |
