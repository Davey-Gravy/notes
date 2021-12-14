Output of command into a variable
```shell
daveygravy@LAPTOP-NEAEKAOU:~/scriptingPractice$ foo=$(pwd)
daveygravy@LAPTOP-NEAEKAOU:~/scriptingPractice$ echo "We are in $foo"
We are in /home/daveygravy/scriptingPractice
```
#### Using curly braces
```shell
convert image.png image.jpg
convert image.{png,jpg}
```
```
touch foo{,1,2,3}
```
#### Find folders

```
find . -name src -type d
```
From the current working directory, find directories with the name src

```
find . -path '**/test/*.py' -type f
```

From the current working directory, find python files in the `test` subdirectory

tags: #shellscripting #computerscience #programming