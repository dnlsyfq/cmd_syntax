### ls 
```
ls command has several more options. Here are three common ones:

-a - lists all contents, including hidden files and directories
-l - lists all contents of a directory in long format, as well as the file permissions
-t - orders files and directories by the time they were last modified
```

### cp
```
cp source.txt destination.txt 

cp source.txt destination/

cp file1.txt file2.txt my_directory/ 

cp * my_directory/

cp w*.txt my_directory/
```

### mv


```
mv my_file.txt my_directory/

mv my_file_1.txt my_file_2.txt my_directory/
```

### rename

```
mv file_origin.txt file_renamed.txt
```

### rm

```
rm unwanted_file.txt

rm -r unwanted_directory


````

### > file

```
echo 'text' > file.txt
```

* overwrites all original content in
```
cat deserts.txt > forests.txt
```


### >> file
to add to a file without losing the original text

```
cat deserts.txt >> forests.txt
```

### < 
< takes the standard input from the file on the right and inputs it into the program on the left

```
cat < deserts.txt
```

### | pipe 
| is a “pipe.” The | takes the standard output of the command on the left, and pipes it as standard input to the command on the right. You can think of this as “command to command” redirection.

```
cat volcanoes.txt | wc  

cat volcanoes.txt | wc | cat > islands.txt 


```

### wc 
wc command outputs the number of lines, words, and characters in doc 

```
```

### sort 
sort takes the standard input and orders it alphabetically
```
sort continents.txt 

cat glaciers.txt | sort > sorted-glaciers.txt 
```

### uniq
filters out adjacent, duplicate lines in a file.

```
sort deserts.txt | uniq > uniq-deserts.txt 
```

### grep

searches files for lines that match a pattern and then returns the results

```
grep America continents.txt 
```

grep -i enables the command to be case insensitive.

```
grep -i America continents.txt
```


---

### Bash
The beginning of your script file should start with #!/bin/bash on its own line. 

This tells the computer which type of interpreter to use for the script.

When saving the script file, it is good practice to place commonly used scripts in the ```~/bin/``` directory

### Permission

add this permission to a file with filename: script.sh use:
```
chmod +x script.sh
```

* On Linux style shells
```
~/.bashrc and on 
```
* On MacOSX
```
~/.bash_profile. 
```

To ensure that scripts in ~/bin/ are available, you must add this directory to your PATH within your configuration file:
```
PATH=~/bin:$PATH
```


```script.sh
#!/bin/bash

echo "Hello Codecademy!"
```

```terminal

$ ./script.sh
```

```script.sh
#!/bin/bash
phrase="Hello to you!"

echo $phrase
```

### Conditional

Use if to start the conditional, followed by the condition in square brackets ([ ]). then begins the code that will run if the condition is met. else begins the code that will run if the condition is not met. Lastly, the conditional is closed with a backwards if, fi.

```
if [ $index -lt 5 ]
then
  echo $index
else
  echo 5
fi
```

list of comparison operators for numbers you can use within bash scripts:
```
Equal: -eq
Not equal: -ne
Less than or equal: -le
Less than: -lt
Greater than or equal: -ge
Greater than: -gt
Is null: -z
```

When comparing strings, it is best practice to put the variable into quotes ("). This prevents errors if the variable is null or contains spaces. The common operators for comparing strings are:
```
Equal: ==
Not equal: !=
```

```
if [ "$foo" == "$bar"]
```

```script.sh

#!/bin/bash
first_greeting="Nice to meet you!"
later_greeting="How are you?"
greeting_occasion=1

if[$greeting_occasion -lt 1]
then
  echo $first_greeting
else
  echo $later_greeting
fi


```

### Loop
There are 3 different ways to loop within a bash script: for, while and until.

```
for word in $paragraph
do
  echo $word
done
```


while loops keep looping while the provided condition is true whereas until loops loop until the condition is true
```
while [ $index -lt 5 ]
do
  echo $index
  index=$((index + 1))
done
```

```script.sh
#!/bin/bash
first_greeting="Nice to meet you!"
later_greeting="How are you?"
greeting_occasion=0
while [ $greeting_occasion -lt 3 ]
do
  if [ $greeting_occasion -lt 1 ]
  then
    echo $first_greeting
  else
    echo $later_greeting
  fi
  greeting_occasion=$((greeting_occasion + 1))
done
 
```



```
until [ $index -eq 5 ]
do
  echo $index
  index=$((index + 1))
done
```


### input 

prompting the user for input. 
For this, we use the read syntax. To ask the user for input and save it to the number variable

```
echo "Guess a number"
read number
echo "You guessed $number"
```

to access external data is to have the user add input arguments when they run your script. These arguments are entered after the script name and are separated by spaces.

```
saycolors red green blue
```

Within the script, these are accessed using $1, $2, etc, where $1 is the first argument (here, “red”) and so on

If your script needs to accept an indefinite number of input arguments, you can iterate over them using the "$@" syntax
```
for color in "$@"
do
  echo $color
done
```

access external files to our script. You can assign a set of files to a variable name using standard bash pattern matching using regular expressions.


```
files=/some/directory/*
```


iterate through each file and do something. 


```
for file in $files
do
  echo $file
done
```


```
#!/bin/bash
first_greeting="Nice to meet you!"
later_greeting="How are you?"
greeting_occasion=0
echo "How many times should I greet?"

read greeting_limit

while [ $greeting_occasion -lt $greeting_limit ]
do
  if [ $greeting_occasion -lt 1 ]
  then
    echo $first_greeting
  else
    echo $later_greeting
  fi
  greeting_occasion=$((greeting_occasion + 1))
done
```

### aliases
set up aliases for your bash scripts within your .bashrc or .bash_profile file to allow calling your scripts without the full filename

```
alias saycolors='./saycolors.sh'
```

add standard input arguments to your alias.

```
alias saycolors='./saycolors.sh "green"'
```

```
alias greet3="./script.sh 3"
```
















