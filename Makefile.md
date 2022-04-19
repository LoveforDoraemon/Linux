# Makefile

[TOC]

## Intro

* `Makefile` is essential when developing in Linux (Windows can automacally generate makefile)
* You can put the library files to be linked in the makefile and formulate the corresponding rules and order
* When you modify source file, `make` will only recompile modified file which saves time

## Variable



## Grammar

### Basic

```makefile
targets:prerequisites[;command]
	command
	
# tagets: object file,executable file,label
# prerequisites: dependent file, multiple or none
# command: any shell command(one line per command)

# example
test:test.py
	gcc -o test test.c
```

### Advanced

```makefile
# main.c lib.h lib1.c lib2.c to get main
main:main.o lib1.o lib2.o
	gcc main.o lib1.o lib2.o -o main
main.o:main.c lib.h
	gcc -c main.c -o main.o
lib1.o:lib1.c lib.h
	gcc -c lib1.c -o lib1.o
lib2.o:lib2.c lib.h
	gcc -c lib2.c -o lib2.o
.PHONY:clean
clean:
	rm -rf *.o test
	
# The program will automatically check if one of files is 
# modified or existed
# The main taget in this makefile is "main"
# 'Clean' is aphony target to clean object files and  taget file (you have to type 'make clean' to execute this)
```

## Wildcard

| Wildcard | Function                      |
| -------- | ----------------------------- |
| *        | match 0 or any character      |
| ?        | match any 1 char              |
| [a]      | match specified char          |
| $@       | all taget files               |
| $^       | all dependent files           |
| $<       | the first dependent files     |
| $?       | all refreshed dependent files |

```makefile
# example
test:*.c
	gcc -o $@ $^

# notice: wildcard can't be applied directly in variable 
# reference(instead try wildcard function)
VAR=$(wildcard *.c)
test:$(VAR)
	gcc -o $@ $^
```



