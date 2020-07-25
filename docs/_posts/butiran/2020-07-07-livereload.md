---
layout: post
author: viridi
title: Livereload
mathjax: false
ptext: false
x3dom: false
threejs: false
category: butiran
tags: [github]
---
Set Ruby to reload automatically while editing file in local web server


## Using livereload flag
Now we can use

```batch
jekyll serve --livereload
```

from the beginning of year 2018 [[1](#ref1)], that unfortunately produces

```batch
Configuration file: L:/home/butiran/docs/_config.yml
            Source: L:/home/butiran/docs
       Destination: L:/home/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.748 seconds.
 Auto-regeneration: enabled for 'L:/home/butiran/docs'
Unable to load the EventMachine C extension; To use the pure-ruby reactor, require 'em/pure_ruby'
                    ------------------------------------------------
      Jekyll 4.1.1   Please append `--trace` to the `serve` command
                     for any additional information or backtrace.
                    ------------------------------------------------
```

and does not work.


## Modify eventmachine
Instead of installing eventmachine, try to modify first the `eventmachine.rb` file by adding

```ruby
require 'em/pure_ruby'
```

to the first line of code does work [[2](#ref1)], where the file is located at `C:\Ruby24-x64\lib\ruby\gems\2.4.0\gems\eventmachine-1.2.5-x64-mingw32\lib` for Windows. And after that following messages


```batch
Configuration file: L:/home/butiran/docs/_config.yml
            Source: L:/home/butiran/docs
       Destination: L:/home/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.751 seconds.
 Auto-regeneration: enabled for 'L:/home/butiran/docs'
LiveReload address: http://127.0.0.1:35729
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.```

are produced. Some error messages are produces

```batch
Configuration file: L:/home/butiran/docs/_config.yml
            Source: L:/home/butiran/docs
       Destination: L:/home/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.7 seconds.
 Auto-regeneration: enabled for 'L:/home/butiran/docs'
LiveReload address: http://127.0.0.1:35729
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
#<Thread:0x00000000079dbb90@C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/commands/serve/live_reload_reactor.rb:41 run> terminated with exception (report_on_exception is true):
Traceback (most recent call last):
        7: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/commands/serve/live_reload_reactor.rb:44:in `block in start'
        6: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/eventmachine.rb:196:in `run'
        5: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:144:in `run_machine'
        4: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:547:in `run'
        3: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:547:in `loop'
        2: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:553:in `block in run'
        1: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:595:in `crank_selectables'
C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:595:in `select': An operation was attempted on something that is not a socket. (Errno::ENOTSOCK)
                    ------------------------------------------------
      Jekyll 4.1.1   Please append `--trace` to the `serve` command
                     for any additional information or backtrace.
                    ------------------------------------------------
#<Thread:0x0000000007bd2db8@C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/commands/serve.rb:283 aborting> terminated with exception (report_on_exception is true):
Traceback (most recent call last):
        7: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/commands/serve.rb:283:in `block in boot_or_detach'
        6: from C:/Ruby26-x64/lib/ruby/2.6.0/webrick/server.rb:157:in `start'
        5: from C:/Ruby26-x64/lib/ruby/2.6.0/webrick/server.rb:32:in `start'
        4: from C:/Ruby26-x64/lib/ruby/2.6.0/webrick/server.rb:211:in `block in start'
        3: from C:/Ruby26-x64/lib/ruby/2.6.0/webrick/server.rb:204:in `ensure in block in start'
        2: from C:/Ruby26-x64/lib/ruby/2.6.0/webrick/server.rb:341:in `cleanup_shutdown_pipe'
        1: from C:/Ruby26-x64/lib/ruby/2.6.0/webrick/server.rb:341:in `each'
C:/Ruby26-x64/lib/ruby/2.6.0/webrick/server.rb:341:in `close': Bad file descriptor (Errno::EBADF)
```

Restrore the `eventmachine.rb` and try another solution.


## Uninstall eventmachine
Try another suggestion [[3](#ref1)]

```batch
gem uninstall eventmachine
```

```batch
You have requested to uninstall the gem:
        eventmachine-1.2.7-x64-mingw32

em-websocket-0.5.1 depends on eventmachine (>= 0.12.9)
If you remove this gem, these dependencies will not be met.
Continue with Uninstall? [yN]  y
Successfully uninstalled eventmachine-1.2.7-x64-mingw32
```

following by

```batch
bundle install
```

and produces

```batch
Fetching gem metadata from https://rubygems.org/.........
Using concurrent-ruby 1.1.6
Using i18n 1.8.3
Using minitest 5.14.1
Using thread_safe 0.3.6
Using tzinfo 1.2.7
Using zeitwerk 2.3.1
Using activesupport 6.0.3.2
Using public_suffix 4.0.4
Using addressable 2.7.0
Using bundler 2.1.4
Using colorator 1.1.0
Fetching eventmachine 1.2.7 (x64-mingw32)
Installing eventmachine 1.2.7 (x64-mingw32)
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
Bundle complete! 4 Gemfile dependencies, 39 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
```

and

```batch
Configuration file: L:/home/butiran/docs/_config.yml
            Source: L:/home/butiran/docs
       Destination: L:/home/butiran/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.567 seconds.
 Auto-regeneration: enabled for 'L:/home/butiran/docs'
LiveReload address: http://127.0.0.1:35729
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
      Regenerating: 1 file(s) changed at 2020-07-07 15:00:00
                    index.md
#<Thread:0x000000000791dbe0@C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/commands/serve/live_reload_reactor.rb:41 run> terminated with exception (report_on_exception is true):
Traceback (most recent call last):
        7: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/commands/serve/live_reload_reactor.rb:44:in `block in start'
        6: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/eventmachine.rb:197:in `run'
        5: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:144:in `run_machine'
        4: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:547:in `run'
        3: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:547:in `loop'
        2: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:553:in `block in run'
        1: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:595:in `crank_selectables'
C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:595:in `select': An operation was attempted on something that is not a socket. (Errno::ENOTSOCK)
        7: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/jekyll-4.1.1/lib/jekyll/commands/serve/live_reload_reactor.rb:44:in `block in start'
        6: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/eventmachine.rb:197:in `run'
        5: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:144:in `run_machine'
        4: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:562:in `run'
        3: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:559:in `ensure in run'
        2: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:559:in `each'
        1: from C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:559:in `block in run'
C:/Ruby26-x64/lib/ruby/gems/2.6.0/gems/eventmachine-1.2.7-x64-mingw32/lib/em/pure_ruby.rb:559:in `close': Bad file descriptor (Errno::EBADF)
                    ------------------------------------------------
      Jekyll 4.1.1   Please append `--trace` to the `serve` command
                     for any additional information or backtrace.
                    ------------------------------------------------
```

still does not work.

## Note
Leave it right now and refresh it manually while editing.


## References
1. <a name="ref1"></a> url <https://stackoverflow.com/a/50866532/9475509>.
2. <a name="ref2"></a> url <https://stackoverflow.com/a/53080143/9475509>.
3. <a name="ref3"></a> url <https://stackoverflow.com/a/30683018/9475509>.