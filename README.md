# git コマンドの勉強
gitコマンドを理解する為、実際にコマンド叩きながら、動きを理解する

# git hubにソースを反映させる為に行う手順
## git init
```sh
# 空のGitリポジトリを作成、もしくは既存のリポジトリを再初期化
git init
```

## git add
```sh
# 全てのファイルを追加する
git add -A

# ステージエリアにファイルを追加する
git add ファイルパス
# 更新があった全てのファイルを対象にする
git add -u
```
- [git addコマンドの使い方！ステージエリアにファイルを追加する！](https://codelikes.com/git-add/)

## git commit
```sh
# コミットすると、ローカルのリポジトリに履歴として記録される(ローカルに記録されているだけの状態)
git commit -m "first commit"

# 履歴の確認が可能(コミットには、識別番号が付与されている)
git log
# –amendオプションで、コミットメッセージの修正が可能
git commit --amend
# [--amend]オプションと[-m]オプションの組み合わせで、その場でコミットメッセージの修正が可能。
git commit --amend -m "コミットのテストです！"
```
- [git commitコマンドの使い方！-mオプションなど解説！](https://codelikes.com/git-commit/)

## git branch -M <ブランチ名>
```sh
# ブランチ名をmasterからmainに強制的に変更する
git branch -M main
```
- [git branch コマンドの -m と -M オプションの違い](https://www.curict.com/item/58/58909e5.html)


## git remote add
```sh
# リモートリポジトリを追加するコマンド
git remote add <リモートレポジトリ名> <URL>

# git hubの場合は下記のコマンドとなる
git@github.com:git hubアカウント名/リモートのディレクトリー名.git
# リモートレポジトリの確認
git remote -v
```
- [リモートレポジトリ(origin)を変更・削除・上書き・追加する方法](https://prograshi.com/general/git/git-remote-commands/)

## git push
```sh
# リモートリポジトリにソースコードが共有された状態になる
git push -u origin main
```

# ローカル環境で行うgitコマンド一覧

##  git branch
```sh
# ブランチを作成
git branch newBranch

# ブランチリスト確認
git branch
# ブランチの切り替え
git checkout <ブランチ名>
```

## git merge
```sh
# git branchで現在適用されているブランチを確認する
git branch
* main
  test-branch

 # git checkoutでマージ元のブランチに移動する
git branch main

# 現在のブランチに対して、マージしたいブランチを指定する
# 取り込み元のブランチに移動した後、取り込みたいブランチ名を指定する
git merge <取り込みたいブランチ名>
# 例　git merge　test-branch
```
- [Git のブランチ機能 - ブランチとマージの基本](https://git-scm.com/book/ja/v2/Git-%E3%81%AE%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E6%A9%9F%E8%83%BD-%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%81%A8%E3%83%9E%E3%83%BC%E3%82%B8%E3%81%AE%E5%9F%BA%E6%9C%AC)

## リモートのブランチを削除する
```sh
git push <remote> --delete <branch>
# 例： git push origin --delete fix/authentication

git push <remote> :<branch>
# 例: git push origin :fix/authentication
```
- [Git ブランチを削除する方法 (ローカル、リモート)](https://www.freecodecamp.org/japanese/news/how-to-delete-a-git-branch-both-locally-and-remotely/#:~:text=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%81%AE%E5%89%8A%E9%99%A4%E3%81%AF%20git,branch%3E%20%E3%81%A7%E5%AE%9F%E8%A1%8C%E3%81%97%E3%81%BE%E3%81%99%E3%80%82&text=%2Dd%20%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AF%E3%80%81%E5%89%8A%E9%99%A4%E5%AF%BE%E8%B1%A1,D%20%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%BE%E3%81%99%E3%80%82)
- [【Git入門】git mergeの使い方！コマンドでブランチをマージする](https://codelikes.com/git-merge/)

## git rebase
```sh
# git rebaseは、コミット履歴を移動したり修正、削除したりするコマンド
# 分かり易く説明すると枝分かれの枝を根本からポッキっと追って、本流にくっつけるイメージ

# 操作方法
# 取り込むブランチに移動する
git branch
* main
  feature

# featureブランチに移動
git checkout feature

# mainブランチに、featureブランチのコミット履歴を挿入する。その際、featureブランチの存在は消滅する
git rebase <とってきたいコミットを持つブランチ名>
# 例　git rebase main
```
- [Git のブランチ機能 - リベース](https://git-scm.com/book/ja/v2/Git-%E3%81%AE%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E6%A9%9F%E8%83%BD-%E3%83%AA%E3%83%99%E3%83%BC%E3%82%B9)

# リモート環境 or githubで行うgit操作一覧
## Pull Request
- [GitHubのDraft Pull Request の活用方法](https://developer.so-tech.co.jp/entry/2022/09/14/120000)

# 参考資料
- [gitコマンドがgitリポジトリを探す順番](https://qnighy.hatenablog.com/entry/2017/03/11/233134)
- [GithubでのWeb上からのマージの仕方3種とその使いどころ](https://qiita.com/ko-he-8/items/94e872f2154829c868df)
- [あなたはmerge派？rebase派？綺麗なGitログで実感したメリット](https://style.biglobe.co.jp/entry/2022/03/22/090000)
- [【Git】git-flowを知ろう！　利用時のルールについて](https://cloudsmith.co.jp/blog/efficient/2020/08/1534208.html)

