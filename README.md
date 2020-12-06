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




