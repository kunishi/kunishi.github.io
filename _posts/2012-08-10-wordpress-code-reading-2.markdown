---
layout: post
title: "WordPressのソースコードリーディング(2)"
date: 2012-08-10 09:38
comments: true
categories: wordpress
---
昨日の続き。

## wp-config-sample.php
https://github.com/WordPress/WordPress/blob/master/wp-config-sample.php

wp-config.phpはこれをコピーして作る。種々のパラメータの設定が中心だが、今は、これらのパラメータの意味はいいだろう。それを除くと、wp-settings.phpをrequire_onceしているだけ。

## wp-settings.php

ここらへんから重要なコードが増えてきてる感じ。

まず、wp-includes/ ディレクトリの load.php, default-constants.php, version.phpをrequire。その後、次の関数を呼び出して設定を行っているが、これらはload.phpの中か? というわけで、load.phpへ寄り道。

* wp_initial_constants()
* wp_check_php_mysql_versions()
* wp_unregister_GLOBALS()
* date_default_timezone_set('UTC') (当該関数がある場合、つまりPHP5以降)
* wp_fix_server_vars()
* wp_favicon_request()
* wp_maintenance()
* timer_start()
* wp_debug_mode()

### wp_initial_constants() (in wp-includes/default-constants.php)
WordPress固有のパラメータの設定。それ以上特筆すべきことはないように思われる。

### wp_check_php_mysql_version() (in wp-includes/load.php)
PHPのバージョン、MySQL extensionのロードの有無、wp-content/db.phpの有無のチェック。必要とされるPHPのバージョンは wp-includes/version.php にある。

関数中で wp_load_translations_early() という関数がエラー処理の前に呼ばれている。同じく load.php の中に定義されている関数で、localizationの設定を、通常のロードシーケンスとは異なるシーケンスで行う場合などに用いる。

### wp_unregister_GLOBALS() (in wp-includes/load.php)
配列GLOBALSに格納されている値（register_globalsがtrueのときに格納される値）をクリアする。ただし、PHPでリザーブされている値（例えば、スーパーグローバル $_GET は実は$GLOBALS['_GET']に格納されている?）と、wp-config.phpで設定されたグローバル変数 table_prefix はクリア対象から除外されている。

### wp_fix_server_vars() (in wp-includes/load.php)
環境によって$_SERVER変数の値が間違っていることがあるので、その修正用関数。

### wp_favicon_request() (in wp-includes/load.php)
/favicon.icoにリクエストが来たら、長さ0のデータを返す? なんでこんな処理をしているのか、よくわからない。保留。

### wp_maintenance() (in wp-includes/load.php)
メンテナンスモードの処理。WordPressのアップグレード時などに使われるらしい。

### timer_start() (in wp-includes/load.php)
グローバル変数 $timestart にこの関数が呼ばれた時刻を格納する。timer_stop()と対にして意味を持つようで、timer_stop()で当該ページが表示されるのにどれくらいの時間がかかるか測定するもののようだ。

### wp_debug_mode() (in wp-includes/load.php)
デバッグモードの設定。今は飛ばしておいてよさそう。
