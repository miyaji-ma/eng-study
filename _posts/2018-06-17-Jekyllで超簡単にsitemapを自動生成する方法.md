---
layout: post
title: Jekyllで超簡単にsitemapを自動生成する方法
date: 2018-06-17 16:25 +0900
---

Jekyllでsitemapを自動生成する方法をご紹介です。以下の通り変更することで、サイトルートにsitemap.xmlが生成されます。これでSEO対策もバッチリですね。

## インストール
まずはお手持ちのJekyllプロジェクトフォルダに移動して、jekyll-sitemapをインストールします。
{% highlight bash %}
gem install jekyll-sitemap
{% endhighlight %}

## ソース修正
`Gemfile`と`_config.yml`を次の通り修正します。
{% highlight diff %}
diff --git a/Gemfile b/Gemfile
index 377544d..4131cc8 100644
--- a/Gemfile
+++ b/Gemfile
@@ -29,3 +29,4 @@ gem "tzinfo-data", platforms: [:mingw, :mswin, :x64_mingw, :jruby]
 gem "wdm", "~> 0.1.0" if Gem.win_platform?
 
 gem 'jekyll-compose', group: [:jekyll_plugins]
+gem 'jekyll-sitemap'

diff --git a/_config.yml b/_config.yml
index 2b9b954..9adbe75 100644
--- a/_config.yml
+++ b/_config.yml
@@ -29,6 +29,8 @@ markdown: kramdown
 theme: minima
 plugins:
   - jekyll-feed
+  - jekyll-sitemap
+
 
 # Exclude from processing.
 # The following items will not be processed, by default. Create a custom list
{% endhighlight %}

以上でサイトルートにsitemap.xmlが生成されます。Google Search Consoleに食べさせてあげるなどしてSEO対策しましょう。
