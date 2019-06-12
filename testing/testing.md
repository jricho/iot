# Code Quality #

* It does what it is supposed to do.
* It does not contain defects or problems.
* It is easy to read, maintain, and extend.

> When can I check my code quality?

You can check your code's quality;

* As you write it
* When it's checked into vcs
* When you are running your tests

## Automating code reviews with Static Code Analysis ##

Static code analysis is a way to analyze code without executing it (in opposite to dynamic code analysis). Most of the time code is parsed into an intermediate code representation that can more easily be checked.

Static Code Analysis finds a wide range of issues: code style, code best practices, security, complexity, compatibility etc.

### How to use it ###

* Run tools on your machine

One of the most common ways to apply static code analysis is to run static code analysis tools on top of your code manually or semi-manually. Just run one of the dozens of open source tools on your repo and get a list of all the issues found in your project.

Here is a small selection of great tools for Python - Pylint, Pyflakes, Mypy

* In youe code editor

A lot of linting and static code analysis tools have integrations with editors, that allow you to directly check your code before committing it, e.g VS Code.

* In your Continuous Integration tool

One way to integrate static analysis in your development process is to add tools in your continuous integration pipeline. Most of the tools have plugins that you can easily integrate with the most common continuous integration tools, E.g Jenkins.

## Increase test coverage with Unit Testing ##

A unit test is a scripted code level test designed in Python to verify a small "unit" of functionality.

It is recommended that unit testing and a test matrix be created at a minimum on the package level.

[![Unit testing example](http://img.youtube.com/vi/https://www.youtube.com/watch?v=1Lfv5tUGsn8/0.jpg)](http://www.youtube.com/watch?v=https://www.youtube.com/watch?v=1Lfv5tUGsn8)
