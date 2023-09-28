# Introduction to Unix - MiCM Fall 2022

## Excersice 1 answers

1. Go to the exercises directory inside the intro to unix folder you downloaded

```{bash}
cd MiCM_Inro_Unix_Fall2022/exercises
```

2. Create a directory called folder1 under data/ho1.

```{bash}
mkdir data/ho1/folder1
```

3. Access the directory you just created
~~~{}
cd data/ho1/folder1
~~~
4. Create two files:  f1.txt and .f2.txt
~~~{}
touch f1.txt
touch .f2.txt

# Or just create them in nano and at the same time write in them
~~~

5. Write the numbers from 1 to 10 in f1.txt (one number per line)
~~~{bash}
# option 1 - write down the numbers inside the text editor
nano f1.txt

# option 2 - print and redirect the output (not very recommended as it is error prone)
echo -e "1\n2\n3\n4\n5\n6\n7\n8\n9\n10\n" >> f1.txt 
~~~
6. Write the following sequence in .f2.txt (one letter per line) 
* a a b b b c c c c d d d d d
~~~{bash}
# option 1 - write down the seq inside the text editor
nano .f2.txt

# option 2 - print them and redirect the output (not very recommended as it is error prone)
echo -e "a\na\nb\nb\nb\nc\nc\nc\nc\nd\nd\nd\nd\nd\n" > >.f2.txt
 
~~~
7. List all the contents of the directory (including .f2.txt) –hint look at the manual of ls
~~~{}
# check the manual, q to exit
man ls 

ls -a
~~~
8. Change the name of .f2.txt to f2.txt
~~~{}
mv .f2.txt f2.txt
~~~

9. Write the first 10 lines of f1.txt and all the lines in f2.txt to a new file f3.txt
```{}
head -10 f1.txt | cat f2.txt > f3.txt
```

10. Change the permissions of f1.txt so that only the user can read and write the file
```{}
# Multiple ways to do this one!
# one option - rewrite all of the permissions
chmod u+rw,go-rw f1.txt
# or
chmod 700 f1.txt

# another option - just remove the ones that are not useful
chmod go-rwx f1.txt
```

11. Count the number of lines in file f3.txt
```{}
wc -l f3.txt
```

12. Go back to the data directory and create a symbolic link to folder1.
```{}
# Go back two directories
cd ../..
# -s opition to create the symbolic link
ln -s ho1/folder1 folder1_link
```


#
MiCM Intro to Unix Fall 2022 - Hands on 1
