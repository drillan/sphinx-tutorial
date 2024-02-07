# はじめてのSphinx

## Sphinxとは

SphinxはテキストからHTMLやLaTeX（PDF）、EPUBなどのドキュメントに出力するツールです。豊富な拡張機能が提供されており、APIドキュメントの自動作成など、技術者向けのマニュアル作成などに適しています。

## インストール

まずはプロジェクトのディレクトリ（フォルダ）を作成します。

```{code-block} bash
---
caption: ディレクトリの作成
---

$ mkdir sphinx-sample
$ cd sphinx-sample
```

ここではPythonの仮想環境を利用して、Sphinxをインストールします。pythonコマンドは必要に応じてpython3に置き換えてください。

```{code-block} bash
---
caption: 仮想環境の作成とアクティブ化（Linux/macOS）
---

$ python -m venv .venv
$ source .venv/bin/activate
```

```{code-block} powershell
---
caption: 仮想環境の作成とアクティブ化（Windows）
---

> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser -Force
> py -m venv .venv
> source .venv\Scripts\activate.ps1
```

次にSphinxをインストールします。

```{code-block} bash
---
caption: Sphinxのインストール
---

$ python -m pip install sphinx
```

## プロジェクトの作成

`sphinx-quickstart` コマンドを使い、いくつかの質問に入力することでプロジェクトを作成します。ここでは、「プロジェクト名」と「著者名」に任意の文字列を入力し、ほかはデフォルトで進みます。

```{code-block} bash
---
caption: プロジェクトの作成
---

$ sphinx-quickstart                                                                                                                                   ✔  
Sphinx 7.2.6 クイックスタートユーティリティへようこそ。

以下の設定値を入力してください（Enter キーのみ押した場合、
かっこで囲まれた値をデフォルト値として受け入れます）。

選択されたルートパス: .

Sphinx 出力用のビルドディレクトリを配置する方法は2つあります。
ルートパス内にある "_build" ディレクトリを使うか、
ルートパス内に "source" と "build" ディレクトリを分ける方法です。
> ソースディレクトリとビルドディレクトリを分ける（y / n） [n]: 

プロジェクト名は、ビルドされたドキュメントのいくつかの場所にあります。
> プロジェクト名: sample
> 著者名（複数可）: your_name
> プロジェクトのリリース []: 

ドキュメントを英語以外の言語で書く場合は、
 言語コードで言語を選択できます。Sphinx は生成したテキストをその言語に翻訳します。

サポートされているコードのリストについては、
https://www.sphinx-doc.org/en/master/usage/configuration.html#confval-language を参照してください。
> プロジェクトの言語 [en]: 

ファイル sphinx-tutorial/docs/sample-doc01/conf.py を作成しています。
ファイル sphinx-tutorial/docs/sample-doc01/index.rst を作成しています。
ファイル sphinx-tutorial/docs/sample-doc01/Makefile を作成しています。
ファイル sphinx-tutorial/docs/sample-doc01/make.bat を作成しています。

終了：初期ディレクトリ構造が作成されました。

マスターファイル sphinx-tutorial/docs/sample-doc01/index.rst を作成して
他のドキュメントソースファイルを作成します。次のように Makefile を使ってドキュメントを作成します。
 make builder
"builder" はサポートされているビルダーの 1 つです。 例: html, latex, または linkcheck。

```

## HTMLへビルド

`make html` コマンドでHTMLファイルにビルドします。

```{code-block} bash
---
caption: HTMLへビルド
---

$ make html
```

`_build/html` ディレクトリの `index.html` をブラウザで開くと、生成されたHTMLが確認できます。