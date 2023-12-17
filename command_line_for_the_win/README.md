-----------------------------------------------------------------------------------------------------------------------------------

1.Your first challenge is to helloon the terminal in a single command. worldprint 
Hint: There are many ways to print text on the command line, one way is with > command. Try it below and good luck!echothe 

echo "hello world"
-----------------------------------------------------------------------------------------------------------------------------------

2. Print the current working directory.

pwd
-----------------------------------------------------------------------------------------------------------------------------------

3. List names of all the files in the current directory, one file per line.

ls
-----------------------------------------------------------------------------------------------------------------------------------

4. There is a file named access.log in the current directory. Print the contents.

cat access.log
-----------------------------------------------------------------------------------------------------------------------------------

5. Print the last 5 lines access.logof 

tail -5 access.log
-----------------------------------------------------------------------------------------------------------------------------------

6. Create an empty file named take-the-command-challenge in the current working directory.

touch take-the-command-challenge
-----------------------------------------------------------------------------------------------------------------------------------

7. Create a directory named tmp/files in the current working directory

Hint: The tmp/" doesn't exist, with one command you need to create both "tmp/" and "tmp/files"directory 

mkdir -p tmp/files
-----------------------------------------------------------------------------------------------------------------------------------

8. Copy the file named take-the-command-challenge to the directory tmp/files

cp take-the-command-challenge tmp/files/take-the-command-challenge
-----------------------------------------------------------------------------------------------------------------------------------

9. Move the file named take-the-command-challenge to the directory tmp/files

mv take-the-command-challenge tmp/files/take-the-command-challenge
-----------------------------------------------------------------------------------------------------------------------------------

10. A symbolic link is a type of file that is a reference to another file.

Create a symbolic link named take-the-command-challenge that points to the file tmp/files/take-the-command-challenge.

ln -s tmp/files/take-the-command-challenge "take-the-command-challenge"
-----------------------------------------------------------------------------------------------------------------------------------

11. Delete all of the files in this challenge directory including all subdirectories and their contents.

Hint: There are files and directories that start with a .", "rm -rf *" won't work here!dot 

find -delete
-----------------------------------------------------------------------------------------------------------------------------------

12. There are files in this challenge with different file extensions. Remove all files with the .doc extension recursively in the current working directory.

find . -name "*.doc" -delete
-----------------------------------------------------------------------------------------------------------------------------------

13. There is a file named access.log in the current working directory. Print all lines in this file that contains the string "GET".

grep GET access.log
-----------------------------------------------------------------------------------------------------------------------------------

14. Print all files in the current directory, one per line (not the path, just the filename) that contain the 500string 

grep -l 500 *
-----------------------------------------------------------------------------------------------------------------------------------

15. Print the relative file paths, one path per line for all filenames that startin the current directory. access.logwith 

ls
-----------------------------------------------------------------------------------------------------------------------------------

16. Print all matching lines (without the filename or the file path) in all files under the current directory that startthat contain the 500string  access.logwith 

Note that there are no files named access.log in the current directory, you will need to search recursively.

grep -rh 500
-----------------------------------------------------------------------------------------------------------------------------------

17. Extract all IP addresses from files that startprinting one IP address per line. access.logwith 

grep -ro ^[0-9.]*
-----------------------------------------------------------------------------------------------------------------------------------

18. Count the number of files in the current working directory. Print the number of files as a single integer.

find . -type f | wc -l
-----------------------------------------------------------------------------------------------------------------------------------

19. Print the contents of access.log sorted.

sort access.log
-----------------------------------------------------------------------------------------------------------------------------------

20. Print the number of lines in access.log that contain the GETstring 

grep GET access.log | wc -l
-----------------------------------------------------------------------------------------------------------------------------------

21. The file split-me.txt contains a list of numbers separated by a ; character.

Split the numbers on the ; character, one number per line.

cat split-me.txt | tr ";" "\n"
-----------------------------------------------------------------------------------------------------------------------------------

22. Print the numbers 1 to 100 separated by spaces.

echo {1..100}
-----------------------------------------------------------------------------------------------------------------------------------

23. This challenge has text files (with a  Delete this phrase from all text files recursively..txt extension) that contain the challenges are difficultphrase 

Note that some files are in subdirectories so you will need to search for them.

sed -i 'challenge are difficult/d' **/*.txt
-----------------------------------------------------------------------------------------------------------------------------------

24. The file sum-me.txt has a list of numbers, one per line. Print the sum of these numbers.

jq -s add sum-me.txt
-----------------------------------------------------------------------------------------------------------------------------------

25. Print all files in the current directory recursively without the leading directory path.

find . -type f -printf "%f\n"
-----------------------------------------------------------------------------------------------------------------------------------

26. Rename all files removing the extension from them in the current directory recursively.

mv * .*
-----------------------------------------------------------------------------------------------------------------------------------

27. The files in this challenge contain spaces. List all of the files (filenames only) in the current directory but replace all spaces > character.with .a 

ls | tr ' ' '.'
-----------------------------------------------------------------------------------------------------------------------------------

28. In this challenge there are some directories containing files with different extensions. Print all directories, one per line without duplicates that contain one or more files withextension. .tfa 

dirname **/*tf | sort -u
-----------------------------------------------------------------------------------------------------------------------------------

29. There are a mix of files in this directory that start with letters and numbers. Print the filenames (just the filenames) of all files that start with a number recursively in the current directory.

find -type f -printf '%f\n' | grep ^[0-9]
-----------------------------------------------------------------------------------------------------------------------------------

30. Print the 25th line of the file faces.txt

sed -n '25p' faces.txt
-----------------------------------------------------------------------------------------------------------------------------------

31. Print the lines of the file reverse-me.txt in this directory in reverse line order so that the last line is printed first and the first line is printed last.

~~~~~~~~~~~~~~~~~~~~~
In the future
Environmental destruction will be the norm
No longer can it be said that
My peers and I care about this earth
It will be evident that
My generation is apathetic and lethargic
It is foolish to presume that
There is hope
~~~~~~~~~~~~~~~~~~~~~
-Jonathan Reed "The Lost Generation"
ANSWER: tac *
-----------------------------------------------------------------------------------------------------------------------------------

32. Print the file faces.txt, but only print the first instance of each duplicate line, even if the duplicates >t appear next to each other.don

Note that order matters so >t sort the lines before removing duplicates.don

awk '!c[$0]++' faces.txt
-----------------------------------------------------------------------------------------------------------------------------------

33. The file random-numbers.txt contains a list of 100 random integers. Print the number of unique prime numbers contained in the file.

cat random-numbers.txt | sort|uniq | factor | awk 'NF==2'| wc -l
-----------------------------------------------------------------------------------------------------------------------------------

34. access.log.1 and access.log.2 are http server logs.

Print the IP addresses common to both files, one per line.

awk 's[$1]++{print $1}' access.log*
-----------------------------------------------------------------------------------------------------------------------------------

35. Print all matching lines (without the filename or the file path) in all files under the current directory that start access. where the next line contains the 404string logwith 

Note that you will need to search recursively.

grep -h -B1 404 **/access.log*|grep -vE '404|--'
-----------------------------------------------------------------------------------------------------------------------------------

36. Print all files with a .bin extension in the current directory that are different than the file named base.bin.

for f in t*; do cmp -s bas* $f || echo $f; done
-----------------------------------------------------------------------------------------------------------------------------------

37. There is a file: ./.../ /. .the flag.txt

Show its contents on the screen.

cat './.../  /. .the flag.txt'
-----------------------------------------------------------------------------------------------------------------------------------

38. How many lines contain tab characters in the file named file-with-tabs.txt in the current directory.

grep -P "\t" * | wc -l
-----------------------------------------------------------------------------------------------------------------------------------

39. There are files in this challenge with different file extensions.

Remove all files without the .txt and .exe extensions recursively in the current working directory.

find -type f ! -regex '.*\(exe\|txt\)$' -delete
-----------------------------------------------------------------------------------------------------------------------------------

40. There are some files in this directory that start with a dash in the filename. Remove those files.

rm ./-*
-----------------------------------------------------------------------------------------------------------------------------------

41. There are two files in this directory, ps-ef1 and ps-ef2. Print the contents of both files sorted by PID and delete repeated lines.

cat ps-* | sort -k2 -n |uniq
-----------------------------------------------------------------------------------------------------------------------------------

42. In the current directory there is a file called netstat.out.

Print all the IPv4 listening ports sorted from the higher to lower.

grep "\bLISTEN\b" netstat.out|grep -oP "tcp\s+.*:\K\d+"|sort -nr
-----------------------------------------------------------------------------------------------------------------------------------

Thanks for reading!!!
