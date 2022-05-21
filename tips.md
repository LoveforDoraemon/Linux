# tips-5.12

1. ```bash
   # about echo
   echo -n #cancel auto \n
   echo -e #enable escape
   ```

2. ```bash
   # no ouput, because while after pipe | will be in a sub-process
   cat text.txt | while read line; do
     symble=$line
   done
   
   echo $symble
   ```

3. ```bash
   # recommanded method is as follows to read data from a file
   while read line;do
   	symbol=$line
   done < text.txt
   ```

4. ```bash
   # transfer a str to an array
   IFS=,
   list=($str)
   echo "${list[@]}"
   ```

5. ```bash
   # array as a cmd parameter
   a=(1 2 3 4 5)
   bash file "${b[*]}" # "" is very important
   
   # in the script
   b=($1) # () 
   ```
# tips-5.14

1. ```bash
   # to compare a int and a float
   [ `echo "1.1 > 1" | bc` -]
   # to convert a float to integer
   echo "1.2323*23/1" 
   ```
   
2. ```bash
   # notice! () and (()) must be used with $
   # i.e. arithmetic expansions need $
   ```

# tips-5.15

1. ```bash
   # to get a str's length
   # method 1:
   str="Hello,World!"
   len=${#str}
   # method 2:
   str="Hello,World!"
   len=`expr length "$"`
   ```

# tips-5.16

1. ```bash
   # to substitue a str
   echo ${str/substr/replace} # substitute the first match
   echo ${str//substr/replace} # substitute all matches
   ```

2. ```bash
   # to find a substr with index
   echo ${str:start:length} # index starts from 0
   ```

3. ```bash
   # to make grep target a sentence
   echo $sentence | grep -Eo PATTERN
   ```

4. ```bash
   # to transfer a date to stamp
   date [--date="year-month-date"] "+%"
   ```

   