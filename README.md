# Python プロジェクトのテンプレートリポジトリ

このリポジトリは Python の開発プロジェクトで使用するテンプレートリポジトリです。  
想定している開発環境は

- Visual Studio Code
- Python 3.13 (ライブラリは Pipenv で管理)
  - formatter は拡張機能の[autopep8](https://marketplace.visualstudio.com/items?itemName=ms-python.autopep8)を使用
  - linter は拡張機能の[Flake8](https://marketplace.visualstudio.com/items?itemName=ms-python.flake8)を使用

となります。

# セットアップ手順

このテンプレートを使用して Python のソースコードを初めて実行するまでの手順は以下の通りです。

1. テンプレートからリポジトリを作成する

2. 作成したリポジトリをローカル PC にクローンする

```bash
git clone {作成したリポジトリのURL}
cd {作成したリポジトリのフォルダ名}
```

3. `pipenv`を pip インストールする (インストール済みの場合は不要)

\*`pipenv`自体はグローバルにインストールしますが、  
この Python プロジェクトで使用する依存ライブラリの管理は`pipenv`によってリポジトリ内のフォルダ上に保存されていきます。

```bash
pip install pipenv
```

4. `setup.sh`のシェルスクリプトを実行する

- 例: `bash`で実行する場合

```bash
bash setup.sh
```

5. pipenv から`main.py`を実行する

```bash
pipenv run main
```

`main.py`を実行後、以下のようなメッセージが表示されれば成功 👍 です。

```
Success to create python project from template, Nice Job!!

Now, this project has below file/directory in root.
====================================================
setup.sh
.editorconfig
README.md
Pipfile
.gitignore
.venv
.git
.vscode
main.py
Pipfile.lock
====================================================
```
