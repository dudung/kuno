---
layout: post
author: viridi
title: Setup Jekyll
mathjax: false
ptext: false
x3dom: false
threejs: false
category: butiran
tags: [github]
---
Setup a blog using Jekyll according to a tutorial [[1](#ref1)]


## Instal Jekyll
Assume that Ruby is already installed in a Windows 10 Home Version 1903 (OS build 18362.900), Jekyll can be installed

```batch
L:\>gem install jekyll bundler
```

which gives

```batch
Fetching jekyll-4.1.1.gem
Fetching mercenary-0.4.0.gem
Successfully installed mercenary-0.4.0
Successfully installed jekyll-4.1.1
Parsing documentation for mercenary-0.4.0
Installing ri documentation for mercenary-0.4.0
Parsing documentation for jekyll-4.1.1
Installing ri documentation for jekyll-4.1.1
Done installing documentation for mercenary, jekyll after 30 seconds
Successfully installed bundler-2.1.4
Parsing documentation for bundler-2.1.4
Done installing documentation for bundler after 7 seconds
3 gems installed
```

in the command line window.


## Create Gemfile
To list project's dependencies a `Gemfile` must be created with

```batch
L:\>bundle init
```

which produces

```batch
Writing new Gemfile to L:/home/butiran/docs/Gemfile
```

and this is

```bash
# frozen_string_literal: true

source "https://rubygems.org"

git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }

# gem "rails"
```

the content of `Gemfile`.


## Add Jekyll
Edit the `Gemfile` and add Jekyll as a dependency, which changes

```bash
# frozen_string_literal: true

source "https://rubygems.org"

git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }

# gem "rails"

gem "jekyll"
```

content of the file.


## Create a site
Make a `index.md` file, e.g. with following content

```markdown
# butiran-blog
A blog for butiran
```

which will be the `index.md` of the site.


## Build
Build a site with

```batch
L:\>jekyll build
```

which shows

```batch
Resolving dependencies...
Configuration file: none
            Source: L:/home/butiran/docs
       Destination: L:/home/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.15 seconds.
 Auto-regeneration: disabled. Use --watch to enable.
 ```

in the command prompt.


## Local web server
Using

```batch
L:\>jekyll serve
```

the site will be rebuilt after any change and a local web server through

```batch
https://localhost:4000
```

could be accessed. And in `_site` folder following files

```batch
2020-07-07  11:15 AM    <DIR>          .
2020-07-07  11:15 AM    <DIR>          ..
2020-07-07  11:15 AM             3,928 blog-setup.md
2020-06-02  03:47 AM             2,184 cmd.lnk
2020-07-07  10:39 AM                34 index.md
2020-07-02  03:24 AM                22 README.md
               4 File(s)          6,168 bytes
               2 Dir(s)  66,030,813,184 bytes free
```

are produced.


## Running
Following lines are produced

```batch
Configuration file: none
            Source: L:/home/butiran/docs
       Destination: L:/home/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.146 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'L:/home/butiran/docs'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```

and in a Google Chrome a result in the form of

```
Name              Last modified     Size
Parent Directory  2020/07/07 10:43     -
README.md         2020/07/02 03:24    22
blog-setup.md     2020/07/07 11:09  3531
cmd.lnk           2020/06/02 03:47  2184
index.md          2020/07/07 10:39    34

WEBrick/1.4.2    (Ruby/2.6.6/2020-03-31)
at localhost:4000
```

can be obtained.


## Add wdm
Following the produced instruction, a line

```gem
gem 'wdm', '>= 0.1.0'
```

is added to the `Gemfile` and rebuid the site using

```batch
L:\>jekyll serve
```

and following messages

```batch
Resolving dependencies...
Configuration file: none
            Source: L:/home/butiran/docs
       Destination: L:/home/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.161 seconds.
 Auto-regeneration: enabled for 'L:/home/butiran/docs'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```

are produced. The previous instruction does not show.


## Add jemoji
A line of

```gem
gem "jemoji"
```

is also added to `Gemfile`.


## Gemfile.lock
These lines

```gem
GEM
  remote: https://rubygems.org/
  specs:
    activesupport (6.0.2.2)
      concurrent-ruby (~> 1.0, >= 1.0.2)
      i18n (>= 0.7, < 2)
      minitest (~> 5.1)
      tzinfo (~> 1.1)
      zeitwerk (~> 2.2)
    addressable (2.7.0)
      public_suffix (>= 2.0.2, < 5.0)
    colorator (1.1.0)
    concurrent-ruby (1.1.6)
    em-websocket (0.5.1)
      eventmachine (>= 0.12.9)
      http_parser.rb (~> 0.6.0)
    eventmachine (1.2.7-x64-mingw32)
    ffi (1.12.2-x64-mingw32)
    forwardable-extended (2.6.0)
    gemoji (3.0.1)
    html-pipeline (2.12.3)
      activesupport (>= 2)
      nokogiri (>= 1.4)
    http_parser.rb (0.6.0)
    i18n (1.8.2)
      concurrent-ruby (~> 1.0)
    jekyll (4.1.1)
      addressable (~> 2.4)
      colorator (~> 1.0)
      em-websocket (~> 0.5)
      i18n (~> 1.0)
      jekyll-sass-converter (~> 2.0)
      jekyll-watch (~> 2.0)
      kramdown (~> 2.1)
      kramdown-parser-gfm (~> 1.0)
      liquid (~> 4.0)
      mercenary (~> 0.4.0)
      pathutil (~> 0.9)
      rouge (~> 3.0)
      safe_yaml (~> 1.0)
      terminal-table (~> 1.8)
    jekyll-sass-converter (2.1.0)
      sassc (> 2.0.1, < 3.0)
    jekyll-watch (2.2.1)
      listen (~> 3.0)
    jemoji (0.12.0)
      gemoji (~> 3.0)
      html-pipeline (~> 2.2)
      jekyll (>= 3.0, < 5.0)
    kramdown (2.2.1)
      rexml
    kramdown-parser-gfm (1.1.0)
      kramdown (~> 2.0)
    liquid (4.0.3)
    listen (3.2.1)
      rb-fsevent (~> 0.10, >= 0.10.3)
      rb-inotify (~> 0.9, >= 0.9.10)
    mercenary (0.4.0)
    mini_portile2 (2.4.0)
    minitest (5.14.0)
    nokogiri (1.10.9-x64-mingw32)
      mini_portile2 (~> 2.4.0)
    pathutil (0.16.2)
      forwardable-extended (~> 2.6)
    public_suffix (4.0.4)
    rb-fsevent (0.10.4)
    rb-inotify (0.10.1)
      ffi (~> 1.0)
    rexml (3.2.4)
    rouge (3.18.0)
    safe_yaml (1.0.5)
    sassc (2.3.0-x64-mingw32)
      ffi (~> 1.9)
    terminal-table (1.8.0)
      unicode-display_width (~> 1.1, >= 1.1.1)
    thread_safe (0.3.6)
    tzinfo (1.2.7)
      thread_safe (~> 0.1)
    unicode-display_width (1.7.0)
    wdm (0.1.1)
    zeitwerk (2.3.0)

PLATFORMS
  x64-mingw32

DEPENDENCIES
  jekyll
  jemoji
  wdm (>= 0.1.0)

BUNDLED WITH
   2.1.4
```

are in the `Gemfile.lock`, which is also produced.


## Clean
To clean produced file in `_site` folder

```batch
jekyll clean
```

can be used.


## Note
If the `index.md` is substituted with `index.html` then the last file will be shown instead of the look of a FTP site.

## References
1. <a name="ref1"></a> The core team of volunteers, "Step by Step Tutorial", Jekyll, 2020, 
 url <https://jekyllrb.com/docs/step-by-step/01-setup/> [20200707].