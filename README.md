# git-hands-on
This repository is for git hands-on in the lab.

# 1. 概要
## このリポジトリにあるコンテンツ
1. __(座学)__ git, GitHubの勉強資料
2. __(ハンズオン)__ git, GitHubのを実際に使ってみる

※ スライドを作成する事にこだわらず、大体可能な外部資料があればそれを使う。

※ 良さげな外部資料一覧も作成する。

## 資料利用者が達成出来るゴール
- git, GitHubの利用方法を知る
- git, GitHubを用い複数人で共同開発方法を知る
- git, GitHubを個人開発で利用できる

## 資料利用者の前提
- git, GitHubが何かを知らない
- 複数人での共同開発の中でgit, GitHubを使った事がない
- githubアカウントを作成済み(-> 良さげな外部資料探す)
- macを使ってる(-> win, linux向け資料はそのうち作る)

# 2. 座学でやる事
## 概要
各項目についてスライドで学習する。スライドの作成にこだわらず、良さげな外部資料があればそれを使う。
## やりたい事
### Lv. 初級(Beginner)
- gitとは(~バージョン管理とは, バージョン管理のデファクトスタンダードは？~)
- GitHub/GitLabとは
## Lv. 中級(Intermediate)
- コミットについて(~コミットサイズ, コミットメッセージ~)
- issue, branchとは (~共同開発におけるgit-flowの活用~)

## Lv. 上級(Advanced)
- マージ/プルリクエストとは
- コードレビューとは

# 3. ハンズオンでやる事
## 概要
実際にgitを使う時の流れに沿ってコマンドを打っていく感じ？

## やりたい事(コマンド)
- gitのinstall, 設定
- pull
- init
- status
- add (-p)
- commit
- stash (save, -u, pop, list)
- reset
- config --local --edit
- config --global --edit
- checkout (-b)
- branch (-a, -D)
- merge
- .gitignoreについて
- Githubでリポジトリ作成
- GitKraken, Sourcetreeについて

# 4. ファイル構成
```
./
|
|-README
|-LICENSE
|-docs/
    |
    |-index.html(remarkでスライドになってます。)
    |-introduction.md(index.htmlの本文はここに書いて)
```

# 5. 参考になりそうな資料置き場
- [アンド・ディ社内勉強会GitHub](https://www.and-d.co.jp/wp-content/uploads/2020/02/アンド・ディ社内勉強会GitHub.pdf)
- [社内Git勉強会](https://qiita.com/rynkjm/items/5a6578c7b2b5f8698e6d)
- [【スライドあり】初学者向けgit勉強会を開催しました](https://www.infiniteloop.co.jp/blog/2016/02/torikore-git-1/)
- [ドットインストール : git入門](https://dotinstall.com/lessons/basic_git)
- [Progate: 【Mac】Gitの環境構築をしよう！](https://prog-8.com/docs/git-env)
- [brainpadpr/git-hands-on](https://speakerdeck.com/brainpadpr/git-hands-on)
# LICENSE
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[LICENSE](https://github.com/haruu11113/git-hands-on/blob/main/LICENSE)
