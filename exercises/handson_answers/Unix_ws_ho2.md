# Introduction to Unix - MiCM Fall 2022

## Excersice 2 answers

**Don't forget to always explore your files**

1. Go to the directory data/ho2 and list the files in it in long format
```{}
cd data/ho2
ls -l
```
2. Count how many lines start with a “,” in the file happiness.csv
```{}
grep -c ^, happiness.csv

# or

grep ^, happiness.csv | wc -l
```
3. Convert the file happiness.complete.csv into a tab-delimited file and store it as happiness.complete.tsv 
```{}
sed 's/,/\t/g' happiness.complete.csv > happiness.complete.tsv
```
4. Using the file happiness.complete.tsv:
   1. Count how many unique countries are listed.
   ```{}
   sed 1d happiness.complete.tsv | cut -f1 | sort -u | wc -l 

   # or 

   sed 1d happiness.complete.tsv | cut -f1 | sort | uniq | wc -l

   ```
   2. Count how many entries of each gender are
   ```{}
    sed 1d happiness.complete.tsv | cut -f2 | sort | uniq -c
    ```
   3. Replace all spaces with “_” within the same file. Hint: Remember looking at the options in the manual (and/or google)!
    ```{}
    sed -i '' 's/ /_/g' happiness.complete.tsv
    ```
   4. Replace “Female” for “F”, “Male for “M” and “Both” for B and look at the first 10 lines
    ```{}
    sed -e 's/Male/M/' -e 's/Female/F/' -e 's/Both/B/' happiness.complete.tsv | head -10
    ```
   5. Write a new file with all the “Both” entries from the countries in the file countries.txt
   ```{}
   grep Both happiness.complete.tsv | grep -f countries.txt > happiness.complete.both.countries.tsv

   # or 
   grep -f countries.txt happiness.complete.tsv | grep Both > happiness.complete.both.countries.tsv
   ```

#
MiCM Intro to Unix Fall 2022 - Hands on 2
