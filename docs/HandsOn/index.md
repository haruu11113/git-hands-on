class: center, middle

# HandsOn



---
# Agenda

1. Gitのinstall
2. (init, status)
3. (add, commit)
4. Githubでリポジトリ作成
5. (pull, stash)
6. reset
7. config
8. (checkout, branch, merge)
9. log, tig
10. .gitignoreについて
11. GitKraken, Sourcetreeについて



---
# 1. Gitのinstall
## brewを使う場合
```terminal
~ $ brew install git
```
## installerを使う場合
[Binary installer](https://git-scm.com/download/mac)



---
# 1. Gitのinstall(configの設定)
```terminal
~ $ git config --global user.name "GitHubに登録したユーザ名"
~ $ git config --global user.email "GitHubに登録したemail"
```

## インストールしたけど動かない
(zshの場合)
```terminal
~ $ echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.zshenv
~ $ source ~/.zshenv
```



---
# 2. ローカルリポジトリの作成(init, status)
ローカルリポジトリ用ディレクトリの作成
```terminal
~ $ mkdir gitHandsOn
~ $ cd gitHandsOn
gitHandsOn $ ls
> .   ..
```



---
# 2. ローカルリポジトリの作成
## init
ローカルリポジトリの作成
```terminal
gitHandsOn $ git init
> Initialized empty Git repository in /Users/namaenamae/work/gitHandsOn/.git/
```

.gitディレクトリが出来てたらOK
```terminal
gitHandsOn $ ls -a
> .   ..   .git
```



---
# 2. ローカルリポジトリの作成
gitHandsOnディレクトリにmember.mdを作成  
普段使っているテキストエディタで作成してok  
1行目にあだ名を書く  
->member.md
```member.md
haruu11113
```



---
# 2. ローカルリポジトリの作成
member.mdが作成されているか確認
```terminal
gitHandsOn $ ls -a
> .   ..   .git  member.md

gitHandsOn $ cat member.md
> haruu11113
```

※ cat fileName：ファイルの内容がプリントされる



---
# 2. ローカルリポジトリの作成
## status
```terminal
gitHandsOn $ git status
> On branch master
> No commits yet
> Untracked files:
>   (use "git add <file>..." to include in what will be committed)
>         member.md
```
※ 赤文字のファイルが新たに作成されたファイル



---
# 3. コミットする(add, commit)
## add
```terminal
gitHandsOn $ git add member.md
gitHandsOn $ g stat
> On branch master
> No commits yet
> Changes to be committed:
>  (use "git rm --cached <file>..." to unstage)
> 	new file:   member.md
```
※ 緑文字のファイルがadd(ステージング)されたファイル


### tips
```terminal
$ git add fileName
$ git add -A (<-変更のある全ファイルをaddしたい場合)
$ git add -p (<-ファイルの行ごとにaddするかを決めたい場合)
```



---
# 3. コミットする
## commit
※ addしたファイル(変更)がコミットされる
```terminal
gitHandsOn $ git commit -m 'feat: memberを追記した'
> [master (root-commit) 39d3a58] feat: memberを追記した
> 1 file changed, 1 insertion(+)
 create mode 100644 member.md
```

### tips
```terminal
$ git commit -m 'コミットメッセージ'
```



---
# 4. Githubでリポジトリ作成 下記記事にそってgitHandsOnと言うリモートリポジトリを作成してください  ※ 「4,github上で新規レポジトリを作成」まで行ってください  
### [Qiita : Githubに新規リポジトリを追加](https://qiita.com/sodaihirai/items/caf8d39d314fa53db4db#4github%E4%B8%8A%E3%81%A7%E6%96%B0%E8%A6%8F%E3%83%AC%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%82%92%E4%BD%9C%E6%88%90)



---
# 5. リモートリポジトリの設定(push, pull, stash)
## remote add
下記記事にそってローカルリポジトリにリモートリポジトリの情報を設定します  
「5, githubのリモートリポジトリ情報をローカルリポジトリに追加する」を行ます  
```terminal
gitHandsOn $ git remote add origin リモートリポジトリの情報
gitHandsOn $ git remote add origin https://github.com/haruu11113/gitHandsOn.git
            (僕の場合)
```

### [Qiita : Githubに新規リポジトリを追加](https://qiita.com/sodaihirai/items/caf8d39d314fa53db4db#4github%E4%B8%8A%E3%81%A7%E6%96%B0%E8%A6%8F%E3%83%AC%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%82%92%E4%BD%9C%E6%88%90)  



---
# 5. リモートリポジトリの設定
## push
```terminal
gitHandsOn $ git push origin main
> fatal: The current branch main has no upstream branch.
> To push the current branch and set the remote as upstream, use
>     git push --set-upstream origin main

gitHandsOn $ git push --set-upstream origin main
> Branch 'main' set up to track remote branch 'main' from 'origin'.
> Everything up-to-date
```
githubを開いてpushが出来たか確認してみましょう

### tips
```terminal
$ git push リモートリポジトリ名 ブランチ名
```



---
# 7. config

```terminal
gitHandsOn $ git config --local --list
gitHandsOn $ git config --global --list
```



---
# 8. ブランチを切り替える(branch, checkout)
## branch
ローカルリポジトリのブランチ一覧
```terminal
gitHandsOn $ git branch
> * main
```

ローカル＆リモートリポジトリのブランチ一覧
```terminal
gitHandsOn $ git branch -a
> * main
>   remotes/origin/main
```



---
# 8. ブランチを切り替える
## checkout
新しいブランチの作成 & ブランチを切り替える
```terminal
githandson $ git checkout -b harrudesuyo
> switched to a new branch 'harrudesuyo'
```

ブランチが切り替わってるかの確認
```terminal
gitHandsOn $ git branch -a
> * harrudesuyo
>   main
>   remotes/origin/main
```



---
# 8. ブランチを切り替える
## checkout
member.mdを修正する  
普段使っているテキストエディタで作成してok  
2行目に今日の日付を書き足す  
```terminal
gitHandsOn $ cat member.md
> haruu11113
> 2021/04/07
```

## 終わったらadd + commitをしてください



---
# 8. ブランチを切り替える
## checkout
### tips
```terminal
$ git checkout ブランチ名 (<-ブランチを切り替える)
$ git checkout -b 新規ブランチ名 (<-新規ブランチ作成&ブランチを切り替える)
$ git checkout origin リモートのブランチ名
(<-リモートリポジトリにあるブランチをローカルリポジトリに作成 & 切り替える)
```



---
# 8. マージする
## merge
mainブランチにharrudesuyoブランチをマージする
ブランチをmain切り替える
```terminal
githandson $ git checkout main
> Switched to branch 'main'
> Your branch is up to date with 'origin/main'.
```

mainブランチでは今日の日付が書かれてない
```terminal
gitHandsOn $ cat member.md
> haruu11113
```



---
# 8. マージする
## merge
```terminal
githandson $ git merge harrudesuyo
> Updating 39d3a58..75bad31
> Fast-forward
>  member.md | 1 +
>  1 file changed, 1 insertion(+)
```

マージする事で、日付を書き足した変更がmainブランチでも反映される
```terminal
gitHandsOn $ cat member.md
> haruu11113
> 2021/04/07
```



---
# 9. log, tig
## log
ローカルリポジトリのコミットの履歴が見れる
```terminal
githandson $ git log
> commit 39d3a58f32b5303e09b7a6229d528019bdbaf886 (HEAD -> main, origin/master, origin/main, hraudesuyo)
> Author: haruu11113 <haruu11113@gmail.com>
> Date:   Wed Apr 7 17:29:47 2021 +0900
> 
>     feat: memberを追記したw
```



---
# 9. log, tig
## tig
ローカルリポジトリのコミットの履歴が見れる
これは僕がおすすめのツール(コマンド)です  
#### how to install
```terminal
$ brew install tig
```

#### how to use
[Qiita : 超絶便利なGitクライアントのtigのすすめ](https://qiita.com/vivid_muimui/items/7e7a740e6537749de0c0)

#### docs
https://jonas.github.io/tig/



---
# 10. 実際に使ってみよう
## clone
```terminal
$ cd ~
$ git clone git@github.com:haruu11113/gitHandsOn_team.git 
$ cd gitHandsOn_team
```

どんなファイルがあるか確認
```terminal
gitHandsOn_team $ ls
> .   ..   .git  .gitignore   member.md
gitHandsOn_team $ cat member.md
> メンバー一覧
> haruu11113
```

---
# 10. 実際に使ってみよう
member.mdの自分のあだ名を追加してpushまでしよう。
- 自分の名前のブランチを作成&ブランチの切り替え
- member.mdに自分のあだ名を追加
- コミット
- mainブランチに切り替え
- pull
- mainブランチに先ほど作成したブランチをmerge
- push



---
# 10. .gitignoreについて
.gitignoreを用いる事で、リポジトリに追加しないフォルダ・ファイルを指定できます。
```terminal
gitHandsOn_team $ cat .gitignore
> 
```
書き方はこちらを参照  
[[Git] .gitignoreの仕様詳解](https://qiita.com/anqooqie/items/110957797b3d5280c44f)




---
# 10. .gitignoreについて
global ignoreに.DS_Storeを追記する
普段使っているテキストエディタで作成してok  
1行目に.DS_Storeを追記する

```terminal
~ $ cat .config/git/ignore
> .DS_Store
```

### tips  
global ignore(~/.config/git/ignore)は、そのpc上の全てのローカルリポジトリについて、ignore設定ができます。そのため、そのPC特有(mac特有)のファイルをignoreする時に使います。  
local igrene(リポジトリ/.gitignore)は、そのリポジトリ特有のファイルについてignoreします。例えば、djangoのdbファイルやnodeのnode_modulesなどです。  
local ignoreは大抵の場合使われるフレームワークにより何を記載すべきかが決まります。そのため、ネット上にテンプレートなども豊富です。必要に応じて利用してみて下さい。  



---
# 11. GitKraken, Sourcetreeについて
GitKrakenやSourcetreeは、gitをGUI（グラフィカルユーザーインターフェース）で操作する事が出来るアプリケーションです。
(個人的にエンジニアとして働く予定なら、コマンドを覚えておいて損はないと思います)

[Sourcetree](https://www.sourcetreeapp.com), [GitKraken](https://www.gitkraken.com), [GitHub desktop](https://desktop.github.com)

### vscode でgit
vscode上でも、コマンドを使わずにgitを操作する事ができます  
[VSCodeでのGitの基本操作まとめ](https://qiita.com/y-tsutsu/items/2ba96b16b220fb5913be)

### GUI or CUI
gitをGUIで使うかCUIで使うかは、議論がある模様。  
https://aizine.ai/git-gui-1212/
