---
layout: post
author: viridi
title: Ruby and Jekyll at the office
date: 2020-07-08 14:35:00 +07
mathjax: false
ptext: false
x3dom: false
threejs: false
category: butiran
tags: ["github"]
---
Install Ruby and Jekyll at the office

## A prologue
In previous post [[1](#ref1)] we assumed that Ruby is already installed on the system. Now, it will be first installed and then followed by Jekyll setup.

## System
Windows 7 Professional, 2009, Service Pack 1. Intel(R) Core(TM) i7 CPU 870 @2.93 GHz 2.93 GHz, 8.00 GB RAM, 32 bit Operating System.

## Install Ruby
Open RubyInstaller for Windows page [[2](#ref2)], and download x86 (32-bit) version of Ruby 2.6.x [[2](#ref2)]. Save it in a folder sepeaated from data and operating system
```batch
rubyinstaller-devkit-2.6.6-1-x86.exe 2020-07-08 09:11 Application 127,961 KB
```
Execute it and agree with the license
```batch
Copyright (c) 2007-2019 RubyInstaller Team.
All rights reserved.

Except:

  Ruby is copyrighted free software by Yukihiro Matsumoto.
  http://www.ruby-lang.org/en/LICENSE.txt

  3rd party libraries (OpenSSL, ZLib, MSYS2, etc.)

This software is distributed under the terms of the Modified BSD License.
..
```
to proceed and install it on
```batch
C:\Ruby26
```
with all options checked
```batch
(✓) Add Ruby executable to your PATH
(✓) Associate .rb and .rbw files with Ruby installation
(✓) Use UTF-8 as default externa encoding
```
and continue with also all checked
```batch
(✓) Ruby-2.6.6 base files                    70.6 MB
(✓) MSYS2 development toolchain 2020-04-02  870.1 MB
```
which requires total space about 941.8 MB in the hard drive. Proceed and files extraction is performing. A window comes up with messages
```batch
Completing the Ruby 2.6.6.-1-x86 with MSYS2 Setup Wizard

Setup has finished installing Ruby 2.6.6-1-x86 with MSYS2 on your computer. The application may be launched by selecting the installed shortcuts.

Click Finish to exit Setup.
```
Check the option
```batch
(✓) Run 'ridk install' to setup MSYS2 and development toolchain. MSYS2 is required to install gems with C extensions.
```
and finish. Since I am not sure about the following
```batch
1 - MSYS2 base installation
2 - MSYS2 system update (optional)
3 - MSYS2 and MINGW development toolchain

Which components shall be installed? If unsure press ENTER [1,3]
```
I just follow the instruction. And one of some of the messages are
```batch
..
==> ERROR: A specified local key could not be updated from a keyserver
..
MSYS2 seems to be properly installed
Install MSYS2 and MINGW development toolchain ...
..
Install MSYS2 and MINGW development toolchain succeeded
..
Which components shall be installed? If unsure press ENTER []
```
and again simply follow the instruction. Then find a shortcut
```batch
Start Command Prompt with Ruby.lnk
```
Change the name and run it. In the command prompt you can do
```batch
D:\>ruby --version
ruby 2.6.6p146 (2020-03-31 revision 67876) [i386-mingw32]
```
to check the Ruby version. It seems that the installation is successful.

## Check requirements for Jekyll
Do following steps as suggested [[4](#ref4)]
```batch
D:\>ruby -v
ruby 2.6.6p146 (2020-03-31 revision 67876) [i386-mingw32]

D:\>gem -v
3.0.3

D:\>gcc -v
Built by Equation Solution <http://www.Equation.com>.
Using built-in specs.
COLLECT_GCC=gcc
COLLECT_LTO_WRAPPER=c:/gcc/bin/../libexec/gcc/i686-pc-mingw32/4.5.2/lto-wrapper.
exe
Target: i686-pc-mingw32
Thread model: win32
gcc version 4.5.2 (GCC)

D:\>g++ -v
Built by Equation Solution <http://www.Equation.com>.
Using built-in specs.
COLLECT_GCC=g++
COLLECT_LTO_WRAPPER=c:/gcc/bin/../libexec/gcc/i686-pc-mingw32/4.5.2/lto-wrapper.
exe
Target: i686-pc-mingw32
Thread model: win32
gcc version 4.5.2 (GCC)

D:\>make -v
GNU Make 3.82
Built for i686-pc-mingw32
This program is built by Equation Solution <http://www.Equation.com>
for Windows.
Copyright (C) 2010  Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
```
and it seems to meet the requirements .

## Setup Jekyll
We will choose to install Jekyll via RubyInstaller [[5](#ref5)] using
```batch
D:\>gem install jekyll bundler
```
and following lines will be produced
```batch
Fetching colorator-1.1.0.gem
Fetching em-websocket-0.5.1.gem
Fetching eventmachine-1.2.7-x86-mingw32.gem
Fetching addressable-2.7.0.gem
Fetching http_parser.rb-0.6.0.gem
Fetching public_suffix-4.0.5.gem
Fetching concurrent-ruby-1.1.6.gem
Fetching i18n-1.8.3.gem
Fetching ffi-1.13.1-x86-mingw32.gem
Fetching sassc-2.4.0.gem
Fetching jekyll-sass-converter-2.1.0.gem
Fetching rb-fsevent-0.10.4.gem
Fetching rb-inotify-0.10.1.gem
Fetching listen-3.2.1.gem
Fetching jekyll-watch-2.2.1.gem
Fetching kramdown-2.3.0.gem
Fetching kramdown-parser-gfm-1.1.0.gem
Fetching liquid-4.0.3.gem
Fetching mercenary-0.4.0.gem
Fetching forwardable-extended-2.6.0.gem
Fetching pathutil-0.16.2.gem
Fetching rouge-3.20.0.gem
Fetching safe_yaml-1.0.5.gem
Fetching unicode-display_width-1.7.0.gem
Fetching jekyll-4.1.1.gem
Fetching terminal-table-1.8.0.gem
Successfully installed public_suffix-4.0.5
Successfully installed addressable-2.7.0
Successfully installed colorator-1.1.0
Temporarily enhancing PATH for MSYS/MINGW...
Building native extensions. This could take a while...
Successfully installed http_parser.rb-0.6.0
Successfully installed eventmachine-1.2.7-x86-mingw32
Successfully installed em-websocket-0.5.1
Successfully installed concurrent-ruby-1.1.6

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

Successfully installed i18n-1.8.3
Successfully installed ffi-1.13.1-x86-mingw32
Building native extensions. This could take a while...
Successfully installed sassc-2.4.0
Successfully installed jekyll-sass-converter-2.1.0
Successfully installed rb-fsevent-0.10.4
Successfully installed rb-inotify-0.10.1
Successfully installed listen-3.2.1
Successfully installed jekyll-watch-2.2.1
Successfully installed kramdown-2.3.0
Successfully installed kramdown-parser-gfm-1.1.0
Successfully installed liquid-4.0.3
Successfully installed mercenary-0.4.0
Successfully installed forwardable-extended-2.6.0
Successfully installed pathutil-0.16.2
Successfully installed rouge-3.20.0
Successfully installed safe_yaml-1.0.5
Successfully installed unicode-display_width-1.7.0
Successfully installed terminal-table-1.8.0
Successfully installed jekyll-4.1.1
Parsing documentation for public_suffix-4.0.5
Installing ri documentation for public_suffix-4.0.5
Parsing documentation for addressable-2.7.0
Installing ri documentation for addressable-2.7.0
Parsing documentation for colorator-1.1.0
Installing ri documentation for colorator-1.1.0
Parsing documentation for http_parser.rb-0.6.0
unknown encoding name "chunked\r\n\r\n25" for ext/ruby_http_parser/vendor/http-parser-java/tools/parse_tests.rb, skipping
Installing ri documentation for http_parser.rb-0.6.0
Parsing documentation for eventmachine-1.2.7-x86-mingw32
Installing ri documentation for eventmachine-1.2.7-x86-mingw32
Parsing documentation for em-websocket-0.5.1
Installing ri documentation for em-websocket-0.5.1
Parsing documentation for concurrent-ruby-1.1.6
Installing ri documentation for concurrent-ruby-1.1.6
Parsing documentation for i18n-1.8.3
Installing ri documentation for i18n-1.8.3
Parsing documentation for ffi-1.13.1-x86-mingw32
Installing ri documentation for ffi-1.13.1-x86-mingw32
Parsing documentation for sassc-2.4.0
Installing ri documentation for sassc-2.4.0
Parsing documentation for jekyll-sass-converter-2.1.0
Installing ri documentation for jekyll-sass-converter-2.1.0
Parsing documentation for rb-fsevent-0.10.4
Installing ri documentation for rb-fsevent-0.10.4
Parsing documentation for rb-inotify-0.10.1
Installing ri documentation for rb-inotify-0.10.1
Parsing documentation for listen-3.2.1
Installing ri documentation for listen-3.2.1
Parsing documentation for jekyll-watch-2.2.1
Installing ri documentation for jekyll-watch-2.2.1
Parsing documentation for kramdown-2.3.0
Installing ri documentation for kramdown-2.3.0
Parsing documentation for kramdown-parser-gfm-1.1.0
Installing ri documentation for kramdown-parser-gfm-1.1.0
Parsing documentation for liquid-4.0.3
Installing ri documentation for liquid-4.0.3
Parsing documentation for mercenary-0.4.0
Installing ri documentation for mercenary-0.4.0
Parsing documentation for forwardable-extended-2.6.0
Installing ri documentation for forwardable-extended-2.6.0
Parsing documentation for pathutil-0.16.2
Installing ri documentation for pathutil-0.16.2
Parsing documentation for rouge-3.20.0
Installing ri documentation for rouge-3.20.0
Parsing documentation for safe_yaml-1.0.5
Installing ri documentation for safe_yaml-1.0.5
Parsing documentation for unicode-display_width-1.7.0
Installing ri documentation for unicode-display_width-1.7.0
Parsing documentation for terminal-table-1.8.0
Installing ri documentation for terminal-table-1.8.0
Parsing documentation for jekyll-4.1.1
Installing ri documentation for jekyll-4.1.1
Done installing documentation for public_suffix, addressable, colorator, http_parser.rb, eventmachine, em-websocket, concurrent-ruby, i18n, ffi, sassc, jekyll-sass-converter, rb-fsevent, rb-inotify, listen, jekyll-watch, kramdown, kramdown-parser-gfm, liquid, mercenary, forwardable-extended, pathutil, rouge, safe_yaml, unicode-display_width, terminal-table, jekyll after 49 seconds
Fetching bundler-2.1.4.gem
Successfully installed bundler-2.1.4
Parsing documentation for bundler-2.1.4
Installing ri documentation for bundler-2.1.4
Done installing documentation for bundler after 9 seconds
27 gems installed
```
and follow by
```batch
D:\>jekyll -v
```
will produce
```batch
Resolving dependencies...
Traceback (most recent call last):
        19: from C:/Ruby26/bin/jekyll:23:in `<main>'
        18: from C:/Ruby26/bin/jekyll:23:in `load'
        17: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/exe/jekyll:11:in `<top (required)>'
        16: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/plugin_manager.rb:52:in `require_from_bundler'
        15: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler.rb:149:in `setup'
        14: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/runtime.rb:20:in `setup'
        13: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/runtime.rb:101:in `block in definition_method'
        12: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:226:in `requested_specs'
        11: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:237:in `specs_for'
        10: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:170:in `specs'
         9: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:258:in `resolve'
         8: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/resolver.rb:22:in `resolve'
         7: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/resolver.rb:50:in `start'
         6: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/vendor/molinillo/lib/molinillo/resolver.rb:43:in `resolve'
         5: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/vendor/molinillo/lib/molinillo/resolution.rb:182:in `resolve'
         4: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/vendor/molinillo/lib/molinillo/resolution.rb:257:in `process_topmost_state'
         3: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/vendor/molinillo/lib/molinillo/resolution.rb:308:in `unwind_for_conflict'
         2: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/vendor/molinillo/lib/molinillo/resolution.rb:308:in `tap'
         1: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/vendor/molinillo/lib/molinillo/resolution.rb:310:in `block in unwind_for_conflict'

C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/vendor/molinillo/lib/molinillo/resolution.rb:328:in `raise_error_unless_state': Unable to satisfy the following requirements: (Bundler::Molinillo::VersionConflict)

- `nokogiri (= 1.10.9) x64-mingw32` required by `Gemfile.lock`
- `nokogiri (>= 1.4)` required by `html-pipeline (2.12.3)`
- `nokogiri (>= 1.4) x86-mingw32` required by `html-pipeline (2.12.3)`
        13: from C:/Ruby26/bin/jekyll:23:in `<main>'
        12: from C:/Ruby26/bin/jekyll:23:in `load'
        11: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/exe/jekyll:11:in `<top (required)>'
        10: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/plugin_manager.rb:52:in `require_from_bundler'
         9: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler.rb:149:in `setup'
         8: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/runtime.rb:20:in `setup'
         7: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/runtime.rb:101:in `block in definition_method'
         6: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:226:in `requested_specs'
         5: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:237:in `specs_for'
         4: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:170:in `specs'
         3: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:258:in `resolve'
         2: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/resolver.rb:22:in `resolve'
         1: from C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/resolver.rb:45:in `start'
C:/Ruby26/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/resolver.rb:59:in `rescue in start': Bundler could not find compatible versions for gem "nokogiri":
 (Bundler::VersionConflict)
  In snapshot (Gemfile.lock):
    nokogiri (= 1.10.9)

  In Gemfile:
    jemoji x86-mingw32 was resolved to 0.12.0, which depends on
      html-pipeline (~> 2.2) was resolved to 2.12.3, which depends on
        nokogiri (>= 1.4) x86-mingw32

Running `bundle update` will rebuild your snapshot from scratch, using only
the gems in your Gemfile, which may resolve the conflict.
```

## Update bundle
Follow the previous instruction
```batch
D:\>bundle update
```
and get the following lines
```batch
Fetching gem metadata from https://rubygems.org/...........
Fetching gem metadata from https://rubygems.org/..
Resolving dependencies....
Using concurrent-ruby 1.1.6
Using i18n 1.8.3
Fetching minitest 5.14.1
Installing minitest 5.14.1
Fetching thread_safe 0.3.6
Installing thread_safe 0.3.6
Fetching tzinfo 1.2.7
Installing tzinfo 1.2.7
Fetching zeitwerk 2.3.1
Installing zeitwerk 2.3.1
Fetching activesupport 6.0.3.2
Installing activesupport 6.0.3.2
Using public_suffix 4.0.5 (was 4.0.4)
Using addressable 2.7.0
Using bundler 2.1.4
Using colorator 1.1.0
Using eventmachine 1.2.7 (x86-mingw32)
Using http_parser.rb 0.6.0
Using em-websocket 0.5.1
Using ffi 1.13.1 (x86-mingw32) (was 1.12.2)
Using forwardable-extended 2.6.0
Fetching gemoji 3.0.1
Installing gemoji 3.0.1
Fetching mini_portile2 2.4.0
Installing mini_portile2 2.4.0
Fetching nokogiri 1.10.10 (x86-mingw32) (was 1.10.9)
Installing nokogiri 1.10.10 (x86-mingw32) (was 1.10.9)
Fetching html-pipeline 2.13.0 (was 2.12.3)
Installing html-pipeline 2.13.0 (was 2.12.3)
Using sassc 2.4.0 (was 2.3.0)
Using jekyll-sass-converter 2.1.0
Using rb-fsevent 0.10.4
Using rb-inotify 0.10.1
Using listen 3.2.1
Using jekyll-watch 2.2.1
Fetching rexml 3.2.4
Installing rexml 3.2.4
Using kramdown 2.3.0 (was 2.2.1)
Using kramdown-parser-gfm 1.1.0
Using liquid 4.0.3
Using mercenary 0.4.0
Using pathutil 0.16.2
Using rouge 3.20.0 (was 3.18.0)
Using safe_yaml 1.0.5
Using unicode-display_width 1.7.0
Using terminal-table 1.8.0
Using jekyll 4.1.1
Fetching jemoji 0.12.0
Installing jemoji 0.12.0
Fetching wdm 0.1.1
Installing wdm 0.1.1 with native extensions
Bundle updated!
Post-install message from nokogiri:
Nokogiri is built with the packaged libraries: libxml2-2.9.10, libxslt-1.1.34, zlib-1.2.11, libiconv-1.15.
Post-install message from html-pipeline:
-------------------------------------------------
Thank you for installing html-pipeline!
You must bundle Filter gem dependencies.
See html-pipeline README.md for more details.
https://github.com/jch/html-pipeline#dependencies
-------------------------------------------------
```
and again
```batch
D:\>jekyll -v
```
will produce
```batch
jekyll 4.1.1
```
which shows that it should be installed properly.

## Test local web server
On the command prompt just do
```batch
D:\>jekyll serve
```
will produce
```batch
Configuration file: D:/github/butiran/docs/_config.yml
            Source: D:/github/butiran/docs
       Destination: D:/github/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 3.2 seconds.
 Auto-regeneration: enabled for 'D:/github/butiran/docs'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
[2020-07-08 14:17:26] ERROR `/favicon.ico' not found.
```
and `http://localhost:4000/` in Google Chrome is working.

## Note
This post is finished at about 14:35 and 14:35:00 is put on the front matter, where there is a predefined variable `date` for posts [[6](#ref6)].

## References
1. <a name="ref1"></a> Sparisoma Viridi, "Setup Jekyll", 7 Jul 2020, url <https://dudung.github.io/butiran/butiran/2020/07/07/setup-jekyll.html> [20200708].
2. <a name="ref#2"></a>url <https://rubyinstaller.org/downloads/> [20200708].
3. <a name="ref#3"></a>url <https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-2.6.6-1/rubyinstaller-devkit-2.6.6-1-x86.exe> [20200708].
4. <a name="ref#4"></a>The core team of volunteers, "Installation", url <https://jekyllrb.com/docs/installation/> {20200708].
5. <a name="ref#5"></a>The core team of volunteers, "Jekyll on Windows", url <https://jekyllrb.com/docs/installation/windows/> {20200708].
6. <a name="ref#6"></a>The core team of volunteers, "Front Matter", url <https://jekyllrb.com/docs/front-matter/> {20200708].
