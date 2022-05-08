# Bash
[TOC]
## intro

- Bash is an open GNU project

```bash
$ cat /etc/shells  #supported shells
$ which bash       #absolute path of bash
```

- Generally the first line of a bash file (called shebang):

```bash
#! /bin/bash
```

## special symbols

### `'' and ""`:

- '' means it's a str, no variable substitution will happen for '$'

## variable

### basis

- case sensitive
- no space besides "="
- reference needs "$"
- Bash will auto determine the datatype

### built-in variables

| name    | meanings                   |
| ------- | -------------------------- |
| BASH    | BASH=/user/bin/bash        |
| COLUMNS | lins-numbers on the screen |
| HOME    | HOME=/home/doraemon        |

`set`command can get this

### command-line parameters

| name | meanings                                           |
| ---- | -------------------------------------------------- |
| $0   | name of the script                                 |
| $1-9 | 1-9 parameters                                     |
| $#   | numbers of parameters                              |
| $*   | all parameters stored as one string                |
| $@   | parameters stored as a list                        |
| $?   | PID                                                |
| $$   | nearest command exit state(0 for normal situation) |
| $!   | backstage process ID                               |

```bash
#! /bin/bash
parameter_list=("$@")
echo ${parameter[0]}
```

### command substitution

`` or ()

```bash
#! /bin/bash
var1=`ls`
var2=(whoami)
```

## basic command

### `read`

```bash
#! /bin/bash
echo "what's up,bro?"
read answer

echo "final exam projects?"
read -a projects
echo "${projects[0]}"

read -p "username:" user
read -sp "passwd:\n" pass
echo 
echo $user
echo $pass
```

### expr

```bash
expr length str #get the length of a str
expr index str char #get the first position of char in str (start from 1)
expr 100 % 9 #note the space besides operator
expr substr str num1 ... #get the substr in position num
```

### test

```bash
test 1 -eq 2
test  'asd' = 'asd'
test -r test.sh
```

### bc

```bash
#used as calculator in Linux
echo "5^5" | bc
echo 'scale=3;(2.333-1.222)/2' | bc
echo "obase=2;256" | bc
echo "ibase=2;100"
```



## operator

| operator          | example                                      |
| ----------------- | -------------------------------------------- |
| +-*/              | ellipsis                                     |
| **                | power  $((100**2))                           |
| += -= /= *= %=    | x=2002;let"x %= 6";echo $x                   |
| -eq               | 1 -eq 2,return true                          |
| -ne               | 1 -ne 2, return true                         |
| -gt               | 2 -gt 0,return true                          |
| -lt               | less than                                    |
| -ge               | greater or equal                             |
| -le               | less or equal                                |
| !expr             | expr is false?                               |
| -n str            | length>0?                                    |
| -z str            | length=0?                                    |
| == !=             | str equal/unequal?                           |
| -d/e/r/s/w/x FILE | directory/existed/readable/size>0/write/exe? |

- +-*/etc should be used in (()) or let ""

## structure

### if

```bash
if [ expression ];
then
statements
	if (( $1 + 2 == 100 ))
	then
	statements
elif [ expression ];
then
statements
else
statements
fi
```

### case

```bash
case expression in
	pattern1|pattern2)
		statements
		;;
	...
	patternn)
		statements
		;;
	*)                     #default final pattern
		statements
		;;
esac
	
```

### for

```bash
for var in list
do
commands
done

for (( expression1; expression2; expression; )) #similar to C
do
commands
break/continue                                   #available
done
```
### while

```bash
while [ expression ];
do
commands;
done
```

### 

