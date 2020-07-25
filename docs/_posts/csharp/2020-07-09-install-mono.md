---
layout: post
author: viridi
title: Install Mono
date: 2020-07-09 14:35:00 +07
mathjax: false
ptext: false
x3dom: false
threejs: false
category: learn
tags: ["C#", "Mono"]
---
Install Mono at home

## A prologue
..

## System
Windows 10 Home, 2019, Version 1903, OS Build 18362.900. Intel(R) Core(TM) i3-4005U CPU @ 1.70 GHz 1.70 GHz, 4.00 GB RAM, 64-bit Operating System, x64-based processor.

## Download installer
For Windows operating system Mono 32-bit can be downloaded from [[1](#ref1)]. This version is chosen due to availabilty of GTK#.

## Installing
Move the Windows installer package files for mono
```
mono-6.8.0.123-gtksharp-2.12.45-win32-0.msi
```
to separated folder than data and operating system. Click it to start installation. Please read the Mono for Windows (x86) License Agreement. After read it by scrolling down, you can tick
```
(✓) I accept the termns in the License Agreement
```
to enable the Install button. Please wait while the Setup Wizard installs Mono for Windows (x86). Then Validating, Installing, Generating, Copying, Updating, Copying new files.

Completed the Mono for Windows (x86) Setup Wizard. Click the Finish button to exit the Setup Wizard.

## Call mono
After create a shortcut you can
```batch
C:\Program Files (x86)\Mono>mono
Usage is: mono [options] program [program-options]

Development:
    --aot[=<options>]      Compiles the assembly to native code
    --debug[=<options>]    Enable debugging support, use --help-debug for details
    --debugger-agent=options Enable the debugger agent
    --profile[=profiler]   Runs in profiling mode with the specified profiler module
    --trace[=EXPR]         Enable tracing, use --help-trace for details
    --jitmap               Output a jit method map to /tmp/perf-PID.map
    --help-devel           Shows more options available to developers

Runtime:
    --config FILE          Loads FILE as the Mono config
    --verbose, -v          Increases the verbosity level
    --help, -h             Show usage information
    --version, -V          Show version information
    --version=number       Show version number
    --runtime=VERSION      Use the VERSION runtime, instead of autodetecting
    --optimize=OPT         Turns on or off a specific optimization
                           Use --list-opt to get a list of optimizations
    --attach=OPTIONS       Pass OPTIONS to the attach agent in the runtime.
                           Currently the only supported option is 'disable'.
    --llvm, --nollvm       Controls whenever the runtime uses LLVM to compile code.
    --gc=[sgen,boehm]      Select SGen or Boehm GC (runs mono or mono-sgen)
    --mixed-mode           Enable mixed-mode image support.
    --handlers             Install custom handlers, use --help-handlers for details.
    --aot-path=PATH        List of additional directories to search for AOT images.
```
to test the installtion, which seems working.

## Try console Hello World
Using `hello.cs` from [[2](#ref2)]
```c#
using System;

public class HelloWorld
{
    public static void Main(string[] args)
    {
        Console.WriteLine ("Hello Mono World");
    }
}
```
compile it
```batch
csc hello.cs
```
and run the result
```batch
mono hello.exe
```
which produces
```
Hello Mono World
```

## References
1. <a name="ref1"></a>"Download", Mono, url <https://www.mono-project.com/download/stable/#download-win> [20200708].
2. <a name="ref2"></a>"Mono Basics", Mono, url https://www.mono-project.com/docs/getting-started/mono-basics/ [20200708].

