class: center, middle
# Introduction

---
class: left, middle
# Agenda

### 1. コンテンツ一覧
### 2. ゴール
### 3. 資料利用者の前提
### 4. 資料について
### 5. GitHubのアカウント作成

---
# コンテンツ一覧
このリポジトリでは2種類のスライドがあります。

#### 1. __(座学)__ Git, GitHubの勉強スライド
#### 2. __(ハンズオン)__ Git, GitHubを実際に使ってみる

※ スライドを作成する事にこだわらず、代替可能な外部資料があればそれを使いたいと思います  
※ 良さげな外部資料一覧を作成しようと思います

---
# ゴール
#### - Git, GitHubの利用方法を知る
#### - Git, GitHubを用い複数人で共同開発方法を知る
#### - Git, GitHubを個人開発で利用できる

---
# 資料利用者の前提
#### - Git, GitHubが何かを知らない
#### - 複数人での共同開発の中でGit, GitHubを使った事がない
#### - Githubアカウントを作成済み
#### - macを使ってる(-> win, linux向け資料はそのうち作る)

---
# 資料について


---
# macにGitをインストールする

```
brew install git
```

[Download for macOS](https://git-scm.com/download/mac)

---
# GitHubのアカウント作成
この記事が良さげ。この記事で下記2つが出来る。
- GitHubアカウントの作成
- 2段階認証の設定
- ssh鍵の設定

[Qiita | 【2019年1月現在】GitHubアカウント作成方法](https://qiita.com/okumurakengo/items/848f7177765cf25fcde0)  
[Qiita | GitHubでssh接続する手順~公開鍵・秘密鍵の生成から~](https://qiita.com/shizuma/items/2b2f873a0034839e47ce)

---
# git config (しなくてもok)
pc上でgitを使う場合、[local, global, system]という3種類の設定がある。  

### 現在設定されている物を確認する
```
$ cd ~

$ git config --local --list
$ git config --global --list
$ git config --system --list
```

---
# git config global
### 実際に設定をしてみる
```
$ git config --global user.name "GitHubで設定したユーザ名(github.com/ユーザ名)"

$ git config --global user.email GitHubで設定したメールアドレス
```
※これはpc上で全て同じGitHubアカウントを使う場合の設定 
※複数のGitHubアカウントを使いたい場合は、上記設定をした上でlocalの設定も変更する必要あり

---
# git config global (しなくてもok)
### global設定はどこに有るのか 

```
(現在推奨)
~/.config/git/config
~/.config/git/ignore

(昔は下記だった？) ~/.gitconfig ~/. gitignore_global
```

~/.config/git/config

``` ~/.config/git/config
.DS_Store
```

※この二つのファイルはgithubで管理するのがおすすめ  
->[ようこそdotfilesの世界へ](https://qiita.com/yutkat/items/c6c7584d9795799ee164)

---
# git config local (しなくてもok)
### local設定はどこに有るのか

```
./.git/config
```
参考資料  
[git docs](https://git-scm.com/book/ja/v2/%E4%BD%BF%E3%81%84%E5%A7%8B%E3%82%81%E3%82%8B-%E6%9C%80%E5%88%9D%E3%81%AEGit%E3%81%AE%E6%A7%8B%E6%88%90)

