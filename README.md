# my vscode settings

私のVSCodeの設定はこれだ！

2020/12/17現在、`1.51.1` を使用中。

<!-- TOC -->

- [1. 最初にやること](#1-最初にやること)
    - [1.1. やることリスト](#11-やることリスト)
    - [1.2. 必須](#12-必須)
    - [1.3. お好み](#13-お好み)
- [2. Git](#2-git)
    - [2.1. インストール](#21-インストール)
    - [2.2. 鍵ペアの設定](#22-鍵ペアの設定)
    - [2.3. clone 動作確認](#23-clone-動作確認)
- [3. スニペット](#3-スニペット)
- [4. Extension](#4-extension)
- [5. 便利コマンド](#5-便利コマンド)

<!-- /TOC -->

## 1. 最初にやること

### 1.1. やることリスト

[VSCode のオススメ拡張機能 24 選 (と Tips をいくつか) - Qiita](https://qiita.com/sensuikan1973/items/74cf5383c02dbcd82234)

上記記事で紹介されている機能の多くをいつも入れています。以下にリストします。  
チェックを入れているものは個人的には必須の機能で、いつも入れるようにしています。

- [x] vscode-icons
- [x] GitLens
- [x] Prettier
- [ ] Git History
  - [x] Git Graph
    - 私は Git History ではなく Git Graph にしてる
    - 左下にボタンが増えるので使いやすい(Git Hisotry は右上にボタンが増える)からであり、機能的な比較はしてない
- [x] Bracket Pair Colorizer
- [ ] Settings Sync
  - 職場だと UPLOAD は NG なので入れてない
- [ ] REST Client
  - 試験で必要な場合は入れていた
- [x] Bookmarks
- [ ] PlantUML
  - Draw.io で描くことが増えているので入れてない
- [x] TODO Highlight
  - 以下設定を追加して`CARE:`に色が付くようにしている

```json
    "todohighlight.keywords": [
        "CARE:",
    ],
    "todohighlight.defaultStyle": {
        "backgroundColor": "#00ff7f",
        "color": "#000000",
    },
```

- [ ] Japanese Language Pack
- [ ] Path Autocomplete
  - 入れているのだが、イマイチ恩恵を感じていないかも
    - [x] Path Intellisense
- [x] Rainbow CSV
- [x] Partial Diff
- [x] Duplicate action
- [ ] GitHub Pull Requests
  - 頻繁にPRを作ることが最近なく入れてない。GHEでも使えるのかな？
- [ ] gitignore
- [ ] Todo +
- [x] Output Colorizer
  - [x] Log File Highlighter も。
- [ ] proto3
- [ ] Bash Debug
- [x] Trailing Spaces
- [ ] Regex Previewer
- [ ] Add jsdoc comments
- 設定などの Tips
  - [x] インデントの強調
    - `highlightActiveIndentGuide`
  - [ ] 「code」コマンドのインストール
    - 最近はこれしなくてもcodeコマンド使えそう
  - [ ] 最終行に改行を自動挿入
  - [ ] 制御文字の表示
    - `editor.renderControlCharacters`
  - [ ] 折り返し表示
    - ショートカット `Alt z`
  - [ ] エディタレイアウトの保持
    - `workbench.editor.closeEmptyGroups`
  - [x] ターミナルで選択したテキストを自動コピーする
    - `terminal.integrated.copyOnSelection`
  - [ ] 起動時に無題ファイルを開く
  - [ ] CPU 使用の軽減
  - [ ] 不要な行の削除
  - [x] 階層リンク(パンくずリスト)の表示
    - `breadcrumbs.enabled`
  - [ ] 直近閉じたタブを開き直す
    - ショートカット `Ctrl Shift t`
  - [ ] コードの自動フォーマット (Prettier 以外)
  - [ ] ショートカットを使う
    - ショートカット `Shift Alt f`
  - [ ] VSCode の設定を使う
- [ ] フォーカスの移動ショートカット
- [ ] バーの色をプロジェクトごとに変える
- [ ] ターミナルを全画面表示する
- [ ] 定義にジャンプ & 元の位置に戻る
- [ ] ファイル名検索
- [ ] 修正プログラムをコマンドで選択する
- [ ] エディタのグループ移動
- [x] 書式設定なしでテキストをコピーする
  - `editor.copyWithSyntaxHighlighting`

### 1.2. 必須

以下を実施します。

- `editor.mouseWheelZoom`
- `Font Family`
  - 初期設定は`Consolas, 'Courier New', monospace`となっている。
    - とりあえず、`monospace` にしておけば、等幅なので使えそう
      - これは`MS Gothic` と同じかなあ
  - [Visual Studio Codeで等幅フォントを使う - minus9d's diary](https://minus9d.hatenablog.com/entry/2018/12/22/111047)
    - 最近のWindows10は、モリサワの `BIZ UDゴシック` が最初から入っている
      - これも良い
    - 等幅のチェック用テーブル

| あいうえお |  abcdefg   |
| ---------- | ---------- |
| abcdefg    | あいうえお |

- `Editor: Render Whitespace` を `all`
- `Terminal › Integrated: Scrollback`
  - 1000 は少ない。1000000 にしてみている。

### 1.3. お好み

お好みで以下を実施します。

- `editor.minimap.enabled` を false
- `Editor: Quick Suggestions` を true
  - 補完が有効になる？
    - 単語補完ではなく文章全体が一致している場合の補完となることが多くあまり役立たない。
    - 秀丸エディタの単語補完のような動きを期待していると期待はずれ。
  - 私は `Accept Suggestion On Enter` を off にしている。Tab で決定となる。

- エディタの着目箇所の背景色がやや暗いため、明るくするために以下の`workbench.colorCustomizations`を追加
  - 設定項目
    - 現在行
    - 選択文字列、及び選択文字列と一致する文字列
  - #FFFFFF の後ろの数字(アルファ値)をお好みで大きくするとハイライトが明るくなります。
  - メリット
    - 現在行(カーソル位置)の視認性 UP
    - 文字列選択により一致する文字列の視認性 UP

```json
    "workbench.colorCustomizations": {
        "editor.selectionBackground": "#FFFFFF75",
        "editor.selectionHighlightBackground": "#FFFFFF55",
        "editor.lineHighlightBackground": "#FFFFFF35"
    }
```

- markdown編集時のスニペットを有効にする
  - これで ctrl space を押さなくても候補が出る
  - 後述の date を日付に変換するスニペットも date と入力後 ctrl space を押さずに、Tab で変換できるので便利

```json
    "[markdown]":  {
        "editor.quickSuggestions": true,
        "editor.snippetSuggestions": "top"
    }
```

## 2. Git

### 2.1. インストール

インストールしていない場合は SOURCE CONTROL にその旨が表示される。  
ダウンロードリンクも表示されるのでそこからインストールする。

[Git for Windows](https://git-scm.com/download/win)

### 2.2. 鍵ペアの設定

鍵ペアを作成し、公開鍵を GitHub に登録、秘密鍵を.ssh ディレクトリに格納しておきます。

### 2.3. clone 動作確認

コマンドで clone できることを確認しておきます。

```sh
cd /path/to/save-dir
git clone repo-url
```

F1 -> git clone -> リポジトリ URL を入力 -> 保存先ディレクトリを指定 -> Open

Windowsでは恐らく初cloneは失敗すると思われる、以下参照。

- [VSCode から Git のリモートにアクセスできないときの対処方法（Windows 10） - Qiita](https://qiita.com/y-tsutsu/items/ec984831e6c8262d3ff7)
- [OpenSSH for Windows の使用方法 - Qiita](https://qiita.com/akiakishitai/items/9e661a126b9c6ae24a56)
  - 恐らくVSCodeがパスワードの入力を待っていてダイアログも出さない場合に、例えば push ボタンを押してもずっとくるくるしてる動きとなる
  - この設定によりそれが解消する

```sh
git config --global core.sshCommand "C:/Windows/System32/OpenSSH/ssh.exe"

# OpenSSH Authentication Agent を起動

# 鍵を登録
ssh-add
```

## 3. スニペット

date を日付に変換する。常時作業ログを書きながら作業しているので必須。

```json
	"date": {
		"prefix": "date",
		"body": "$CURRENT_YEAR/$CURRENT_MONTH/$CURRENT_DATE $CURRENT_HOUR:$CURRENT_MINUTE"
	}
```

## 4. Extension

いつも入れているもの

- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
- [indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow)
- [Markdown TOC](https://marketplace.visualstudio.com/items?itemName=AlanWalk.markdown-toc)
  - 改行設定が必要
    - [【VSCode】Markdown で書いたブログに目次を付ける！（Markdown TOC） | Developers.IO](https://dev.classmethod.jp/articles/vscode-markdown-toc-for-blog/)
      - `Files: Eol` を `auto` から 改行に変える
  - `Markdown-toc: Depth From` を`2`にする
- [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
- [Replace Rules](https://marketplace.visualstudio.com/items?itemName=bhughes339.replacerules)
  - 私のルールは以下

```json
    "replacerules.rules": {
        "Sorround code": {
            "find": "(.*)",
            "replace": "```log\n$1\n```",
            "flags" : "gms"
        },
        "Remove blank lines": {
            "find": "^\\n",
            "replace": ""
        },
        "Remove trailing and leading whitespace": {
            "find": "^\\s*(.*?)\\s*$",
            "replace": "$1"
        },
    },
    "replacerules.rulesets": {
        "Remove lots of stuff": {
            "rules": [
                "Remove trailing and leading whitespace",
                "Remove blank lines"
            ]
        }
    },
```

- [Draw.io Integration](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio)
  - [VSCode で Draw.io が使えるようになったらしい！ - Qiita](https://qiita.com/riku-shiru/items/5ab7c5aecdfea323ec4e)
  - `xxx.drawio.svg` という画像ファイル名にしておくとこのExtensionに紐づく
- [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)

他、必要に応じて以下

- ms-python.python
- ms-vsliveshare.vsliveshare

## 5. 便利コマンド

インストールしているextensionの一覧

```sh
code --list-extensions
```

