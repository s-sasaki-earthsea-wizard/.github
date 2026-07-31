# プロジェクト名
プロジェクト名を書いてください。

## 概要
プロジェクトの概要を書いてください。

## 開発環境
開発環境について書きます。以下が例です。

- OS: Ubuntu-18.04 (AWS EC2 instance xrdp01-gui)
- Python: 3.8.6

## インストール方法
インストール方法を書いてください。
以下のようなコマンドを書くなどすると手順がわかりやすくなるでしょう。

```
make install
```

## 使い方
実行方法やチュートリアルを書いてください。
必要に応じてスクリーンショットや動画を使ってください。

## バックアップ対象
このプロジェクトを NAS 上に置く場合、S3 Glacier Deep Archive への
バックアップ対象をプロジェクトルートのマーカーファイルで宣言します。

| ファイル | 意味 |
|---|---|
| `.awsignore` | バックアップから除外するもの（再取得可能なデータ、再計算可能な中間生成物） |
| `.awsarchive` | このディレクトリを tar 1個にまとめる（小さいファイルが大量にある場合） |

雛形は [AWSIGNORE_TEMPLATE](.github/AWSIGNORE_TEMPLATE) と
[AWSARCHIVE_TEMPLATE](.github/AWSARCHIVE_TEMPLATE) にあります。

**宣言しない場合、プロジェクト全体がバックアップされます。**
Deep Archive は一度書き込むと 180 日分の保存料金が確定するため、
再取得できるデータや再計算できる中間生成物は `.awsignore` に書いてください。

マーカーファイルを git で追跡したくない場合は、`.gitignore` ではなく
`.git/info/exclude` に追加してください（リポジトリ共有の設定を汚さないため）。

## その他
必要なことがあれば書いてください。

_____

# Project name
Write the name of the project.

## Overview
Write an overview of the project.

## Development environment
Write about the development environment. The following is an example.

- OS: Ubuntu-18.04 (AWS EC2 instance xrdp01-gui)
- Python: 3.8.6

## Installation
Write down the installation procedure.
Commands will be useful to make clear as:

```
make install
```

## Usage
Write a running procedure or tutorial.
Use screenshots and videos if necessary.

## Backup scope
If this project lives on the NAS, declare what reaches S3 Glacier Deep Archive
using marker files at the project root.

| File | Meaning |
|---|---|
| `.awsignore` | What to exclude (re-obtainable data, recomputable intermediates) |
| `.awsarchive` | Send this directory as a single tar object (many small files) |

Templates: [AWSIGNORE_TEMPLATE](.github/AWSIGNORE_TEMPLATE),
[AWSARCHIVE_TEMPLATE](.github/AWSARCHIVE_TEMPLATE).

**Without either marker, the whole project is backed up.**
Every object written to Deep Archive commits to 180 days of storage charges,
so anything that can be downloaded again or recomputed belongs in `.awsignore`.

To keep the markers out of git, add them to `.git/info/exclude` rather than
`.gitignore`, which would alter the shared repository configuration.

## Others
Anything else, please write here.
