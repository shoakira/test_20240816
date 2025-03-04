# Git 基本操作ガイド

## 1. レポジトリの作り方

### 1.1 新規ローカルレポジトリの作成

新しいプロジェクトを開始する場合、まずはローカルでレポジトリを初期化します。

```bash
# プロジェクト用ディレクトリを作成し、移動
mkdir my_project
cd my_project

# gitレポジトリを初期化
git init
```

### 1.2 既存プロジェクトをレポジトリ化

既存のプロジェクトをgit管理下に置く場合は、プロジェクトディレクトリで以下の操作を行います。

```bash
# プロジェクトディレクトリへ移動
cd existing_project

# gitレポジトリを初期化
git init

# 全ファイルをステージングエリアに追加
git add .

# 最初のコミットを作成
git commit -m "Initial commit"
```

---

## 2. GitHubとの連携

GitHubを使って、リモートでレポジトリを管理する方法です。

### 2.1 GitHubでリモートレポジトリを作成

1. GitHubにログインし、右上の「＋」ボタンから「New repository」を選択します。
2. リポジトリ名や公開/非公開設定、READMEファイルの初期化などを設定して作成します。

### 2.2 ローカルレポジトリにGitHubリモートを追加

ローカルで作成したレポジトリに、GitHubのリモートリポジトリを紐付けます。

```bash
# GitHubリモートリポジトリを追加
git remote add origin https://github.com/username/repository.git
```

### 2.3 ローカルの変更をGitHubへプッシュ

ローカルのコミットをGitHubにアップロードします。

```bash
# 初回プッシュ時には -u オプションでアップストリームを設定
git push -u origin master
```

> **ヒント:** ブランチ名が `master` ではなく `main` になっている場合は、`main` に読み替えてください。

### 2.4 GitHubリポジトリのクローン

既に存在するGitHubリポジトリをローカルにコピーする場合は、以下のコマンドを使用します。

```bash
git clone https://github.com/username/repository.git
```

---

## 3. その他の基本操作

### 3.1 ステージングとコミット

変更したファイルをコミットする基本的な手順です。

```bash
# 変更をステージングエリアに追加
git add <ファイル名>
# またはすべての変更を追加する場合
git add .

# コミットの作成
git commit -m "コミットメッセージ"
```

### 3.2 コミットログの確認

コミット履歴を確認するには、以下のコマンドを使用します。

```bash
git log
```

### 3.3 ブランチの作成と切り替え

新しい機能を開発する際に、ブランチを利用すると便利です。

```bash
# 新しいブランチを作成
git branch new-feature

# ブランチを切り替え
git checkout new-feature
```

### 3.4 マージ

作業が完了したら、ブランチを統合します。

```bash
# masterブランチに切り替え
git checkout master

# new-featureブランチを統合
git merge new-feature
```

### 3.5 リモート更新の取得

リモートリポジトリの最新の変更を取得し、ローカルリポジトリを更新するには、以下のコマンドを使用します。

```bash
git pull origin master
```

---

以上が、gitの基本的な操作方法およびGitHubとの連携方法の概要です。これらのコマンドを覚えることで、効率的にバージョン管理を行うことができます。

