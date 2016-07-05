---
layout: post
title: "Wordpressのソースコードを読む(1)"
date: 2012-08-10 02:57
---
とりあえず読み始めた。

## ソースコードの用意

オリジナルのレポジトリは[wordpress.orgのsubversionレポジトリ](http://core.svn.wordpress.org/trunk/)にある。いまどきsubversionは辛い。

しかし、このレポジトリをGitにしたものが[Githubで公開](https://github.com/WordPress/WordPress)されている。15分ごとにオリジナルのレポジトリと同期するようだ。今回の目的にはこれで充分である。

## index.php
https://github.com/WordPress/WordPress/blob/master/index.php

WP_USE_THEMES を true にしてwp-blog-header.phpをrequireしているだけ。

## wp-blog-header.php
https://github.com/WordPress/WordPress/blob/master/wp-blog-header.php

$wp_did_headerという変数がセットされているかチェックしたり、セットされていなければtrueにしたりしているが、とりあえずこれは保留。

その後、wp-load.phpをrequire_onceし、関数wp()を実行し、template-loader.phpをrequire_once。まずwp-load.phpに行くことにする。

## wp-load.php
https://github.com/WordPress/WordPress/blob/master/wp-load.php

主にwp-config.phpのロード。なければエラーメッセージを出し、wp-config.php自動生成用PHPであるsetup-config.phpへのリンクを示して終了。
