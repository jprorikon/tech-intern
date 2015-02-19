Git簡易マニュアル
=================

Git Clientのインストール
------------------------

### Linux

Debian, Ubuntuの場合

```
$ sudo apt-get install git
```

RHEL, CentOS, Fedoraの場合

```
$ sudo yum install git
```

### Windows

Git for Windowsをインストール

- 参考: http://opcdiary.net/?page_id=27065

もしくはGUI対応のGit ClientであるSourceTreeをインストール

- http://sourcetreeapp.com/ にアクセスし、'Download SourceTree Free'のボタンからSourceTreeのインストーラをダウンロードし、インストールを実施

### Mac

Git OS X Installer、またはMacPortsを利用してインストール

- Git OS X Installerを使う場合
  -  http://sourceforge.net/projects/git-osx-installer/
- MacPortsを使う場合

```
$ sudo port install git-core +svn +doc +bash_completion +gitweb
```

もしくはGUI対応のGit ClientであるSourceTreeをインストール

- http://sourcetreeapp.com/ にアクセスし、'Download SourceTree Free'のボタンからSourceTreeのインストーラをダウンロードし、インストールを実施


Git Clientの初期設定
--------------------

### Gitコマンドの場合

コミットログに残すユーザ名とメールアドレスを設定

```
$ git config --global user.name "<ユーザ名(英語)>"
$ git config --global user.email "<メールアドレス>"
```

### SourceTreeの場合

1. SourceTreeを起動
2. 利用許諾契約書を確認し、ライセンスに同意して続行
3. バージョン管理システムが自動的にダウンロードされる
4. 「グローバル無視設定ファイルを作成しますか?」 のダイアログでYesを選択
5. 「アカウントを追加」で自身のGitHubアカウントを登録
6. 「初めてのリポジトリをクローン」をスキップ
7. 「SSHキーを読み込みますか」でNoを選択 (GitHubに鍵を登録済みの場合はYesを選択し、鍵ファイルを選択)
8. ツール > オプションを開き、全般タブ内のデフォルトユーザー情報欄のフルネーム(英語)、Eメールアドレスを設定
9. ツール > オプションを開き、Gitタブ内のグローバル無視リスト右側にある「ファイルを編集」を選択し、末尾に「*.stackdump」を追記して保存

Gitの操作
---------

### 1. GitHubにインターンシップ用リポジトリを新規作成

- GitHubにログインし、トップページ右側にある「+ New Repository」のボタンを選択
- Repository name にリポジトリ名(今回作成するアプリの名前等)を入力し、Initialize this repository with a READMEにチェックを入れて「Create Repository」ボタンを実行

### 2. PC側にインターンシップ用リポジトリをClone

Gitコマンドの場合

```
$ git clone https://github.com/<your_account_name>/<your_repository_name>.git
```

SourceTreeの場合

1. 上部のメニューから「新規/クローンを作成する」を選択
2. 元のパス/URLの右にある地球儀のマークを選択し、ホストされたリポジトリの一覧から先ほど作成したリポジトリを選択
3. 作業用のフォルダをデフォルト以外の場所にしたい場合は、保存先のパスとして作業用のフォルダを選択
4. クローンのボタンを実行

### 3. クローンされたディレクトリ上にソースコードが置かれるように開発作業を行う (ファイルの追加・更新)

### 4. 変更内容のきりの良い単位ごとに、変更内容をGitのローカルリポジトリへCommitする

注意: Password, API Key等の公開すべきでない情報が含まれているファイルはCommit対象として選択しないこと

Gitコマンドの場合

```
$ git status # (現在の状態を確認)
$ git add <追加したいファイル>
$ git commit -m "変更内容を説明するコミットメッセージ"
```

SourceTreeの場合

1. 「作業ツリーのファイル」に表示されているファイルの中から必要なファイルにチェックを入れ、「Indexにステージしたファイル」に移動したことを確認
2. 上部のメニューから「コミット」を選択
3. 入力欄に変更内容を説明するコミットメッセージを入力し、「コミット」ボタンを実行

### 5. コミットした変更内容をローカルからGitHubへPushする

Gitコマンドの場合

```
$ git push orgin master
```

SourceTreeの場合

1. 上部のメニューから「プッシュ」を選択
2. プッシュ先リポジトリを確認し、問題なければ「OK」を選択


### 6. 3に戻り、開発、Commit、Pushを繰り返す


参考
----

- [git - 簡単ガイド](http://rogerdudler.github.io/git-guide/index.ja.html)
- [Gitを使いこなすための20のコマンド](http://sourceforge.jp/magazine/09/03/16/0831212)
- [使い始める Git](http://qiita.com/icoxfog417/items/617094c6f9018149f41f)
- [SourceTreeから始めるGit](http://qiita.com/icoxfog417/items/a650768dfc91b0f0df05)
