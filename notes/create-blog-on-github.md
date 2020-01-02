### create a repository on Github
create a repository called vk2gpz.github.io 

### get Octopress soruce.
```git clone git@github.com:imathis/octopress.git vk2gpz.github.io```

### deploy setting for GitHub
```
cd vk2gpz.github.io

# bundlerが入っていない人向け、bundlerのインストール
sudo gem install bundler

# Gemfileに書かれたgemをインストール
bundle install --path vendor/bundle --jobs=4

bundle exec rake install

# GitHub Pagesに表示するための設定
bundle exec rake setup_github_pages
Enter the read/write url for your repository: git@github.com: username/username.github.com.git
Repository url: #<= githubのリポジトリを登録< span>

bundle exec rake install
```

### octopress confing _config.yml
```
url:                # RSSに記載するためのブログURL
title:              # HTMLのヘッダとタイトルタグに使うブログのタイトル
subtitle:           # HTMLのヘッダ部分に表示するブログのサブタイトル
author:             # コピーライトやメタタグなどに使うブログの著者情報
simple_search:      # ブログ内の検索機能におけるサーチエンジン
description:        # デフォルトのメタタグ内descriptionの内容
date_format:        # 日付のフォーマット(Ruby's date strftime syntax)
subscribe_rss:      # ブログのRSSのURL(デフォルトは /atom.xml)
subscribe_email:    # e-mailを使ったブログの購読のためのURL
category_feeds:     # カテゴリ単位でのRSSを許可するか？ (デフォルトはfalse)
email:              # RSSのためのメールアドレス(必要な場合のみ)
```

### crete a post
You might need
```
bundle exec rake install
```
then

```
bundle exec rake new_post
Enter a title for your post: #<= postのタイトルを聞かれるので入力< span>
```
this will yield a file ```source/_post/YYYY-MM-DD-title.Markdown```

### To review
execute ```rake preview```
then access ```http://localhost:4000/```

