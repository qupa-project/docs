---
title: Installation
description: Setup and Installation
hide:
  - footer
---

# Installation

There are only three main requirements to install uniview.

- Clang++ v12 or greater
- Have NPM installed
- NodeJS v14 or greater


## Checking Prerequisites

Checking Clang Install
	To check you have the correct version of clang installed, simply run the command:
```bash
clang++ --version
```


Checking NPM install
```bash
npm -v
```

Checking Node install
```bash
node -v
```


## Installing Uniview

Simply run:
```sh
npm install -g @qupa/uniview
```

This will install uniview, bind the compile command, and pre-build the standard libraries.

### Installing IDE Tools  
There is a VSCode extension called ``Uniview Language`` which is the official VSCode extension for the language.



## Checking Installation
```sh
uvc --version
```