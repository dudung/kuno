---
layout: post
author: viridi
title: Configure Jekyll
mathjax: false
ptext: false
x3dom: false
threejs: false
category: butiran
tags: [github]
---
Configure a blog using Jekyll according to a tutorial [[1](#ref1)]


## Configuration file
The `_config.yml` file will be used here instead of '_config.toml' file [[2](#ref1)].


## Exclude some files
A line in `_config.yml` file

```bash
exclude: [cmd.lnk, README.md, setup.md, configure.md]
```

will exclude the listed files in generating `_site` folder. It makes that there is only

```batch
 Directory of L:\_site

2020-07-07  11:55 AM    <DIR>          .
2020-07-07  11:55 AM    <DIR>          ..
2020-07-07  11:55 AM                66 index.html
               1 File(s)             66 bytes
               2 Dir(s)  66,030,813,184 bytes free
```

in the `_site` folder. Notice that the `index.html` file is produced from `index.md`

```md
---

---

# butiran-blog
A blog for butiran
```

by adding a Front Matter to the top of the page.


## Vulnerabilty due to activesupport
According to [dependabot](https://github.com/apps/dependabot) after push the `docs` folder to Github

```
1 activesupport vulnerability found in docs/Gemfile.lock 1 hour ago
Remediation
Upgrade activesupport to version 6.0.3.1 or later. For example:

gem "activesupport", ">= 6.0.3.1"
Always verify the validity and compatibility of suggestions with your codebase.
```

from <https://github.com/dudung/butiran/network/alert/docs/Gemfile.lock/activesupport/open>


## Update activesupport
Add

```gem
gem "activesupport", ">= 6.0.3.1"
```

to the `Gemfile`, build and following lines

```bash
You have requested: (Bundler::GemNotFound)
  activesupport >= 6.0.3.1

The bundle currently has activesupport locked at 6.0.2.2.
Try running `bundle update activesupport`

If you are updating multiple gems in your Gemfile at once,
try passing them all to `bundle update`
```

are obtained. Try

```batch
L:\bundle update activesupport
```

```
Fetching gem metadata from https://rubygems.org/..........
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Using concurrent-ruby 1.1.6
Fetching i18n 1.8.3 (was 1.8.2)
Installing i18n 1.8.3 (was 1.8.2)
Fetching minitest 5.14.1 (was 5.14.0)
Installing minitest 5.14.1 (was 5.14.0)
Using thread_safe 0.3.6
Using tzinfo 1.2.7
Fetching zeitwerk 2.3.1 (was 2.3.0)
Installing zeitwerk 2.3.1 (was 2.3.0)
Fetching activesupport 6.0.3.2 (was 6.0.2.2)
Installing activesupport 6.0.3.2 (was 6.0.2.2)
Using public_suffix 4.0.4
Using addressable 2.7.0
Using bundler 2.1.4
Using colorator 1.1.0
Using eventmachine 1.2.7 (x64-mingw32)
Using http_parser.rb 0.6.0
Using em-websocket 0.5.1
Using ffi 1.12.2 (x64-mingw32)
Using forwardable-extended 2.6.0
Using gemoji 3.0.1
Using mini_portile2 2.4.0
Using nokogiri 1.10.9 (x64-mingw32)
Using html-pipeline 2.12.3
Using sassc 2.3.0 (x64-mingw32)
Using jekyll-sass-converter 2.1.0
Using rb-fsevent 0.10.4
Using rb-inotify 0.10.1
Using listen 3.2.1
Using jekyll-watch 2.2.1
Using rexml 3.2.4
Using kramdown 2.2.1
Using kramdown-parser-gfm 1.1.0
Using liquid 4.0.3
Using mercenary 0.4.0
Using pathutil 0.16.2
Using rouge 3.18.0
Using safe_yaml 1.0.5
Using unicode-display_width 1.7.0
Using terminal-table 1.8.0
Using jekyll 4.1.1
Using jemoji 0.12.0
Using wdm 0.1.1
Bundle updated!
Post-install message from i18n:

HEADS UP! i18n 1.1 changed fallbacks to exclude default locale.
But that may break your application.

If you are upgrading your Rails application from an older version of Rails:

Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

If you are starting a NEW Rails application, you can ignore this notice.

For more info see:
https://github.com/svenfuchs/i18n/releases/tag/v1.1.0
```

and find

```
No open alerts on activesupport were found in docs/Gemfile.lock.
Alerts may have been resolved and deleted by recent pushes to this repository.
```

in url <https://github.com/dudung/butiran/network/alert/docs/Gemfile.lock/activesupport/open> after push the update.

## Note
I still do not understand the lines

```
Please check your Rails app for 'config.i18n.fallbacks = true'.
If you're using I18n (>= 1.1.0) and Rails (< 5.2.2), this should be
'config.i18n.fallbacks = [I18n.default_locale]'.
If not, fallbacks will be broken in your app by I18n 1.1.x.

If you are starting a NEW Rails application, you can ignore this notice.
```

where `rails` is not used and `i18n  == 1.8.3`. 


## References
1. <a name="ref1"></a> The core team of volunteers, "Configuration Options", Jekyll, 2020, 
 url <https://jekyllrb.com/docs/configuration/options/> [20200707].
2. <a name="ref1"></a> The core team of volunteers, "Configuration", Jekyll, 2020, url <https://jekyllrb.com/docs/configuration/> [20200707].