---
layout: post
author: viridi
title: Update public-suffix from RubyGems
date: 2020-07-11 17:07:00 +07
mathjax: false
ptext: false
x3dom: false
threejs: false
category: butiran
tags: ["ruby", "gems"]
---
Update public-suffix at home

## A prologue
I have to different Ruby installation, where x64 at home and x86 at the office. The former was installed three days ago [[1](#ref1)], while the later is much older.

## Error message
At home following lines are produced
```batch
L:\home\butiran\docs>ruby --version
ruby 2.6.6p146 (2020-03-31 revision 67876) [x64-mingw32]

L:\home\butiran\docs>jekyll --version
Traceback (most recent call last):
        12: from C:/Ruby26-x64/bin/jekyll:23:in `<main>'
        11: from C:/Ruby26-x64/bin/jekyll:23:in `load'
        10: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/exe/jekyll:11:in `<top (required)>'
         9: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/plugin_manager.rb:52:in `require_from_bundler'
         8: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler.rb:149:in `setup'
         7: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/runtime.rb:20:in `setup'
         6: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/runtime.rb:101:in `block in definition_method'
         5: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:226:in `requested_specs'
         4: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:237:in `specs_for'
         3: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:170:in `specs'
         2: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/spec_set.rb:80:in `materialize'
         1: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/spec_set.rb:80:in `map!'
C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/spec_set.rb:86:in `block in materialize': Could not find public_suffix-4.0.5 in any of the sources (Bundler::GemNotFound)
```

## Installed package
From `C:\Ruby26-x64\lib\ruby\gems\2.6.0\gems`
```bash
$ ls p*
pathutil-0.16.2:
Gemfile  lib/  LICENSE  Rakefile

power_assert-1.1.3:
bin/  COPYING  LEGAL  power_assert.gemspec  README.rdoc
BSDL  Gemfile  lib/   Rakefile

public_suffix-4.0.4:
2.0-Upgrade.md  data/    LICENSE.txt            README.md
bin/            Gemfile  public_suffix.gemspec  SECURITY.md
CHANGELOG.md    lib/     Rakefile               test/
```
which show `public_suffix-4.0.4`, while it requires `public_suffix-4.0.5` from the previous error message.

## Update Gems packages
Do suggestion [[2](#ref2)] but modify it to version `4.0.5`
```batch
gem install public_suffix --version 4.0.5
```
And following lines
```batch
Fetching public_suffix-4.0.5.gem
Successfully installed public_suffix-4.0.5
Parsing documentation for public_suffix-4.0.5
Installing ri documentation for public_suffix-4.0.5
Done installing documentation for public_suffix after 5 seconds
1 gem installed
```
come up. But another error arise
```
L:\home\butiran\docs>jekyll --version
Traceback (most recent call last):
        12: from C:/Ruby26-x64/bin/jekyll:23:in `<main>'
        11: from C:/Ruby26-x64/bin/jekyll:23:in `load'
        10: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/exe/jekyll:11:in `<top (required)>'
         9: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/plugin_manager.rb:52:in `require_from_bundler'
         8: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler.rb:149:in `setup'
         7: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/runtime.rb:20:in `setup'
         6: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/runtime.rb:101:in `block in definition_method'
         5: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:226:in `requested_specs'
         4: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:237:in `specs_for'
         3: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/definition.rb:170:in `specs'
         2: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/spec_set.rb:80:in `materialize'
         1: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/spec_set.rb:80:in `map!'
C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/bundler-2.1.4/lib/bundler/spec_set.rb:86:in `block in materialize': Could not find ffi-1.13.1-x64-mingw32 in any of the sources (Bundler::GemNotFound)
```
Repeat the last two setps and these are the process
```
L:\>gem install ffi --version 1.13.1
Fetching ffi-1.13.1-x64-mingw32.gem
Successfully installed ffi-1.13.1-x64-mingw32
Parsing documentation for ffi-1.13.1-x64-mingw32
Installing ri documentation for ffi-1.13.1-x64-mingw32
Done installing documentation for ffi after 10 seconds
1 gem installed

L:\>gem install nokogiri --version 1.10.10
Fetching nokogiri-1.10.10-x64-mingw32.gem
Nokogiri is built with the packaged libraries: libxml2-2.9.10, libxslt-1.1.34, zlib-1.2.11, libiconv-1.15.
Successfully installed nokogiri-1.10.10-x64-mingw32
Parsing documentation for nokogiri-1.10.10-x64-mingw32
Installing ri documentation for nokogiri-1.10.10-x64-mingw32
Done installing documentation for nokogiri after 29 seconds
1 gem installed

L:\>gem install html-pipeline --version 2.13.0
Fetching html-pipeline-2.13.0.gem
-------------------------------------------------
Thank you for installing html-pipeline!
You must bundle Filter gem dependencies.
See html-pipeline README.md for more details.
https://github.com/jch/html-pipeline#dependencies
-------------------------------------------------
Successfully installed html-pipeline-2.13.0
Parsing documentation for html-pipeline-2.13.0
Installing ri documentation for html-pipeline-2.13.0
Done installing documentation for html-pipeline after 5 seconds
1 gem installed

L:\>gem install sassc --version 2.4.0
Fetching sassc-2.4.0-x64-mingw32.gem
Successfully installed sassc-2.4.0-x64-mingw32
Parsing documentation for sassc-2.4.0-x64-mingw32
Installing ri documentation for sassc-2.4.0-x64-mingw32
Done installing documentation for sassc after 9 seconds
1 gem installed

L:\>gem install kramdown --version 2.3.0
Fetching kramdown-2.3.0.gem
Successfully installed kramdown-2.3.0
Parsing documentation for kramdown-2.3.0
Installing ri documentation for kramdown-2.3.0
Done installing documentation for kramdown after 12 seconds
1 gem installed
```
and try another way after find the requirement of `rouge-3.20.0`, 
```batch
L:\>bundle update rouge
Fetching gem metadata from https://rubygems.org/..........
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Using concurrent-ruby 1.1.6
Using i18n 1.8.3
Using minitest 5.14.1
Using thread_safe 0.3.6
Using tzinfo 1.2.7
Using zeitwerk 2.3.1
Using activesupport 6.0.3.2
Using public_suffix 4.0.5
Using addressable 2.7.0
Using bundler 2.1.4
Using colorator 1.1.0
Using eventmachine 1.2.7 (x64-mingw32)
Using http_parser.rb 0.6.0
Using em-websocket 0.5.1
Using ffi 1.13.1 (x64-mingw32)
Using forwardable-extended 2.6.0
Using gemoji 3.0.1
Using mini_portile2 2.4.0
Using nokogiri 1.10.10 (x64-mingw32)
Using html-pipeline 2.13.0
Using sassc 2.4.0 (x64-mingw32)
Using jekyll-sass-converter 2.1.0
Using rb-fsevent 0.10.4
Using rb-inotify 0.10.1
Using listen 3.2.1
Using jekyll-watch 2.2.1
Using rexml 3.2.4
Using kramdown 2.3.0
Using kramdown-parser-gfm 1.1.0
Using liquid 4.0.3
Using mercenary 0.4.0
Using pathutil 0.16.2
Fetching rouge 3.20.0
Installing rouge 3.20.0
Using safe_yaml 1.0.5
Using unicode-display_width 1.7.0
Using terminal-table 1.8.0
Using jekyll 4.1.1
Using jemoji 0.12.0
Using wdm 0.1.1
Bundler attempted to update rouge but its version stayed the same
Bundle updated!
```
And
```batch
>jekyll --version
jekyll 4.1.1

L:\home\butiran\docs>jekyll serve
Configuration file: L:/home/butiran/docs/_config.yml
            Source: L:/home/butiran/docs
       Destination: L:/home/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 12.478 seconds.
 Auto-regeneration: enabled for 'L:/home/butiran/docs'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```
It seems that updating with bundler is better [[3](#ref3)].
```batch
L:\home\butiran\docs>bundle update
Fetching gem metadata from https://rubygems.org/..........
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies..........
Using concurrent-ruby 1.1.6
Using i18n 1.8.3
Using minitest 5.14.1
Using thread_safe 0.3.6
Using tzinfo 1.2.7
Using zeitwerk 2.3.1
Using activesupport 6.0.3.2
Using public_suffix 4.0.5
Using addressable 2.7.0
Using bundler 2.1.4
Using colorator 1.1.0
Using eventmachine 1.2.7 (x64-mingw32)
Using http_parser.rb 0.6.0
Using em-websocket 0.5.1
Using ffi 1.13.1 (x64-mingw32)
Using forwardable-extended 2.6.0
Using gemoji 3.0.1
Using mini_portile2 2.4.0
Using nokogiri 1.10.10 (x64-mingw32)
Using html-pipeline 2.13.0
Using sassc 2.4.0 (x64-mingw32)
Using jekyll-sass-converter 2.1.0
Using rb-fsevent 0.10.4
Using rb-inotify 0.10.1
Using listen 3.2.1
Using jekyll-watch 2.2.1
Using rexml 3.2.4
Using kramdown 2.3.0
Using kramdown-parser-gfm 1.1.0
Using liquid 4.0.3
Using mercenary 0.4.0
Using pathutil 0.16.2
Using rouge 3.20.0
Using safe_yaml 1.0.5
Using unicode-display_width 1.7.0
Using terminal-table 1.8.0
Using jekyll 4.1.1
Using jemoji 0.12.0
Using wdm 0.1.1
Bundle updated!
```

## Clean unused Gems packages
Try to see unused packages
```batch
L:\>bundle clean --dry-run
Would have removed activesupport (6.0.2.2)
Would have removed bundler (1.17.2)
Would have removed did_you_mean (1.3.0)
Would have removed ffi-1.12.2-x64 (mingw32)
Would have removed html-pipeline (2.12.3)
Would have removed i18n (1.8.2)
Would have removed irb (1.0.0)
Would have removed jekyll (4.0.0)
Would have removed jekyll-feed (0.13.0)
Would have removed jekyll-seo-tag (2.6.1)
Would have removed kramdown (2.2.1)
Would have removed mercenary (0.3.6)
Would have removed minima (2.5.1)
Would have removed minitest (5.11.3)
Would have removed minitest (5.14.0)
Would have removed net-telnet (0.2.0)
Would have removed nokogiri-1.10.9-x64 (mingw32)
Would have removed power_assert (1.1.3)
Would have removed public_suffix (4.0.4)
Would have removed rake (12.3.3)
Would have removed rdoc (6.1.2)
Would have removed rouge (3.18.0)
Would have removed sassc-2.3.0-x64 (mingw32)
Would have removed test-unit (3.2.9)
Would have removed tzinfo-data (1.2020.1)
Would have removed xmlrpc (0.3.0)
Would have removed zeitwerk (2.3.0)
```
and continue clean it
```batch
L:\>bundle clean
Cleaning all the gems on your system is dangerous! If you're sure you want to
remove every system gem not in this bundle, run `bundle clean --force`.

L:\>bundle clean --force
Removing activesupport (6.0.2.2)
Removing bundler (1.17.2)
Removing did_you_mean (1.3.0)
Removing ffi-1.12.2-x64 (mingw32)
Removing html-pipeline (2.12.3)
Removing i18n (1.8.2)
Removing irb (1.0.0)
Removing jekyll (4.0.0)
Removing jekyll-feed (0.13.0)
Removing jekyll-seo-tag (2.6.1)
Removing kramdown (2.2.1)
Removing mercenary (0.3.6)
Removing minima (2.5.1)
Removing minitest (5.11.3)
Removing minitest (5.14.0)
Removing net-telnet (0.2.0)
Removing nokogiri-1.10.9-x64 (mingw32)
Removing power_assert (1.1.3)
Removing public_suffix (4.0.4)
Removing rake (12.3.3)
Removing rdoc (6.1.2)
Removing rouge (3.18.0)
Removing sassc-2.3.0-x64 (mingw32)
Removing test-unit (3.2.9)
Removing tzinfo-data (1.2020.1)
Removing xmlrpc (0.3.0)
Removing zeitwerk (2.3.0)
```
as suggested  [[4](#ref4)].

## Lock the packages
According to  [[5](#ref5)]
```batch
bundle install
```
following by
```batch
L:\>bundle exec jekyll serve
```
can restricts your Ruby environment to only use gems set in the `Gemfile`.

## Note
Honestly, I still confuse with this Ruby, Gems, and bundle, but try it again and again :smiley:. End at 1946.

## References
1. <a name="ref1"></a>Sparisoma Viridi, "Ruby and Jekyll at the office", 08-Jul-2020, url <https://dudung.github.io/butiran/butiran/2020/07/08/ruby-and-jekyll.html> [20200711].
2. <a name="ref1"></a>, ashmaroli, "Answer to 'Could not find public_suffix-3.0.1 in any of the sources (Bundler::GemNotFound)'", 18-Mar-2018, url <https://talk.jekyllrb.com/t/could-not-find-public-suffix-3-0-1-in-any-of-the-sources-bundler-gemnotfound/1603> [20200711].
3. <a name="ref3"></a>-, "bundle update", url https://bundler.io/v1.2/man/bundle-update.1.html#:~:text=Update%20the%20gems%20specified%20(all,the%20version%20of%20a%20gem. [20200711].
4. <a name="ref4"></a>-, "bundle clean", url <https://bundler.io/man/bundle-clean.1.html> [20200711].
5. <a name="ref5"></a>-, "Deployment", url <https://jekyllrb.com/docs/step-by-step/10-deployment/> [20200711].
