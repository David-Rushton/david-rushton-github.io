---
layout: post
title: cliTools
date: 2018-11-15 22:38:00
--- tags #
- c#
- cliTools
---
# cliTools

## Command Line Arguments

Yesterday I started work on a new project, a C# library that provides argument support for command line apps.  I want to make it easier for cli apps to consume input arguments like this:

```batch
cliapp.exe option --argument1 value1 --argument2 "value 2" --flag1
```

I've got a few ideas for some interesting cli apps, however I don't want to repeatedly deal with writing the plumbing code needed to read values from the command line.

It's very early days, I haven't decided exactly how I will approach this.  So far I've made only 2 choices:

- [Maintainable code is the best code](##Maintainable-Code-is-the-Best-Code).
- [Start at the end](##Start-at-the-End)

## Maintainable Code is the Best Code

I will focus on making the code within this project easy to maintain, change and update.  I will place readability above performance, succinctness & anything else I can think of.

## Start at the End

There are so many different ways I could approach this problem.  To help me make progress, and avoid endlessly staring at the blank page, I've begun writing pseudocode.  By imaging how I will use the finished library I've begun to spec-out the features I will implement.

```c#
// Perhaps something like this:
CliApp cliApp = new CliApp();
cliApp.WelcomeMessage = "Text shown when app first runs."
cliApp.HelpMessage = "Text shown when: /?|-h|--help|no arguments|invalid arguments provided."
```
