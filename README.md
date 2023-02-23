# git コマンドの勉強
git　コマンドを理解する為、実際にコマンド叩きながら、動きを理解する

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


# 参考資料
- [gitコマンドがgitリポジトリを探す順番](https://qnighy.hatenablog.com/entry/2017/03/11/233134)
