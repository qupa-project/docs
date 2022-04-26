# Installation

There are only three main requirements to install uniview.
	#. Clang++ v12 or greater
	#. Having NPM installed
	#. NodeJS v14 or greater


## Checking Prerequisites

Checking Clang Install
	To check you have the correct version of clang installed, simply run the command:
```
clang++ --version
```


Checking NPM install
```
npm -v
```

Checking Node install
```
node -v
```


## Installing Uniview

Simply run:
```
npm install -g @qupa/uniview
```

This will install uniview, bind the compile command, and pre-build the standard libraries.

### Installing IDE Tools  
There is a VSCode extension called ``Uniview Language`` which is the offical VSCode extension for the language.



## Checking Installation
```
uvc --version
```