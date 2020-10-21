# Septre Template

## About
複数のStackを一括管理するSeptreとCFnのTemplateを生成するツールtroposphereを用いた
CFn管理ツールです。

## Setup
```shell
# Pipenvでライブラリを行っているので、Pipfile.lockを元に仮想環境を作成し、ライブラリをインストール。
pipenv install

# 仮想環境に入る
pipenv shell

# 仮想環境から出る
exit
```


## Directory Description
```jsx
.
├── Pipfile・・・Pipenvの仮想環境がプロジェクトの依存関係を管理するために使用するファイル
├── Pipfile.lock・・・実際にインストールしたライブラリのバージョンが書かれたファイル
├── README.md
├── config・・・CFnのテンプレートで使用する変数が書かれたyamlファイルを保存するディレクトリ
│   ├── ap-northeast-1・・・リージョンごとに変数がかかれたyamlファイルを保存する
│   └── config.yamlテンプレート共通の変数が書かれたyamlファイル
├── template・・・各CFnのテンプレートを生成するPythonスクリプトが格納されているディレクトリ
│   └── base.py・・・抽象化クラスのPythonスクリプト
├── var・・・変数が書かれたyamlファイルを保存するディレクトリ
│   └── sample.yaml・・・テンプレート共通の変数が書かれたyamlファイル
```

## Commands

```jsx
# Create New Stacks
sceptre --var-file vars/sample.yaml create ap-northeast-1

# Update Stacks
sceptre --var-file vars/sample.yaml update ap-northeast-1

# Create ChangeSet
sceptre --var-file vars/sample.yaml update -c ap-northeast-1

# List Outputs
sceptre --output yaml --var-file vars/dev.yaml list outputs ap-northeast-1
```

## 各種ドキュメント

- troposphere Documentation

[https://troposphere.readthedocs.io/en/latest/](https://troposphere.readthedocs.io/en/latest/)

- Septre Documentation

[https://sceptre.cloudreach.com/2.4.0/](https://sceptre.cloudreach.com/2.4.0/)

