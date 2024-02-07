# Markdownによる記述

Sphinxはデフォルトで、reStructuredText (reST)というマークアップ言語で記述しますが、Markdownやその拡張であるMySTでも記述できます。

Markdown（MyST）を使うには、Sphinx拡張の [MyST-Parser](https://myst-parser.readthedocs.io/en/latest/) をインストールします。

```{code-block} bash
---
caption: MyST-Parserのインストール
---

$ python -m pip install myst-parser
```

次に `conf.py` の `extensions` のリストに `'myst_parser'` を追加します。

```{literalinclude} ../sample-doc01/conf.py
---
caption: conf.py
language: python
linenos:
emphasize-lines: 16
---
```

Markdownでテキストファイルを記述します、ここでは `hello.md` というファイルを作成します。

```{code-block} markdown
---
caption: hello.md
---

# はじめてのSphinx

[Markdown](https://daringfireball.net/projects/markdown/)記法にしたがって記述できます。

## リスト

順序なしリスト

- グー
- チョキ
- パー

順序付きリスト

1. ウォード
2. トラウト
3. 大谷

## ブロッククォート

> 引用
>> ネストされた引用
```

`index.rst` に `hello.md` をtoctreeに追加します。toctreeとは複数の文書を構造化するために使われます。toctreeでは、章-節などの複雑な構造をもつ文書を作成できますが、ここではtoctreeに記述したファイルの順番に文書が出力されると覚えておいてください。toctreeにファイルを追加するときに、ファイルの拡張子は記述しません。

```{literalinclude} ../sample-doc01/index.rst
---
caption: index.rst
language: rst
linenos:
emphasize-lines: 13
---
```

HTMLにビルドします、HTMLに `hello.md` の内容が追加されます。

```{code-block} bash
---
caption: HTMLへビルド
---

$ make html
```