## Overview
* computers good at doing repetitive tasks
	* learn how to use the computer efficiently
## The Shell
* interact with computer without GUI
* spaces separate arguments
###  Environment variables
``` bash
$PATH
```
* shows paths where the shell searches for programs to use
* absolute vs. relative paths
	* absolute -> start from root to desired directory
	```bash
	/home/daveygravy/blazi
	```
	* relative  -> start from current directory
	* use whichever is shorter

## Commands
### Flags and Options
Commands have optional arguments:
* flags
	*	dash followed by a letter e.g. `-l`
*	options
	*	two dashes followed by a word, take a value e.g. `--ignore=PATTERN`
### Streams
Change where input and output streams of program are pointed
* `< file`
	* program input is contents of `file`
* `> file` 
	* direct program output into `file`
* `|` 
	* redirect stream into another program
### Root User
* Linux/Mac equivalent of Windows Adminstrator
* "superuser"

tags: #computerscience #programming 