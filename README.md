# Terminal and Bash commands

## Paths to files and folders

- [Relative and absolute paths](https://github.com/FoundCompBio-Spr26/Intro_Week1/blob/main/Filesystems.md)

- Compare your answers to the practice exercise about paths with someone next to you. If your answers were different, discuss why.

## Your remote Linux computer

- [ondemand.mike.hpc.lsu.edu](https://ondemand.mike.hpc.lsu.edu)

```
Practice Exercise

(1) Log on to HPC OnDemand
(2) Go to Files -> Home Directory
(3) Look at the header bar at the top. What is the path to your home directory?
(4) Using the "New File" and "New Dir" buttons at the top, create some sample
    directories and files in your home folder.
(5) For each of your `.txt` files, click the "Edit" button, add some relevant text,
    and save your changes.
```

## Introduction to the Command Line

### Terminal

 - Built in to Linux (and Mac OS X)
 - By default,__usually__ uses the bash shell (interpreter)
 - The command prompt
 - Tab completion
 	- Double tapping tab will list all files with that beginning
 - Scrolling through history

### Commands related to navigating the filesystem

- `touch filename.txt` will create file
- `pwd` - print working directory - or - "where am I?"
- `ls` - list directory contents
- `ls -l` - long list
    - Everything has three types of permissions
        - Read
        - Write
        - Execute
    - And three groups whose permissions can be controlled
        - Owner
        - Group
        - Others
- [Wikipedia on Unix Permissions](https://en.wikipedia.org/wiki/File_system_permissions#Notation_of_traditional_Unix_permissions)
- `la` - list with hidden files
- `cd` - change directory
    - will accept absolute or relative paths
- `chmod` - change permissions - specify who (ugo), how (+ or -), and what (rwx)
- `man <command>` - gives us the manual page and options for any Unix command (q will get out of manual page)
- [Notes about command-line navigation](https://github.com/FoundCompBio-Spr26/Shell_Week2/blob/main/CommandLine_Navigating.md)

```
Practice Exercise

(1) Use the cd command to navigate up and down through the folders you created in the previous exercise.
(2) After each change of directory, use pwd to check the absolute path of your location.
(3) In folders with text files, use ls to examine the folder's contents.
```

### Commands related to files and folders

- `cp` - copies a file
    - `cp originalFile.txt newFile.txt`
- `mv` - moves __or__ renames a file
    - To change location, use paths: `mv myFile.txt ./folder/myFile.txt`
    - To change name, just use different names: `mv myFile.txt newName.txt`
- `cat filename.txt` - view file contents - can be called on multiple files and will conCATenate their contents
    - `cat file1.txt file2.txt file3.txt` will show all files in command line
    - `cat *.txt` shows all text in files with the file ending .txt
- `ls *.txt` show all files that end in .txt
    - `ls ../*.txt` go up one directory then tell me the txt files there (still within the same directory)
- `head -n #` - view the first # of lines of a file
- `tail -n #` - view the last # of lines of a file
- `less` - view the contents of a file a little at a time nice way to scroll through
- `touch filename.txt` - quickly create a new file
- `nano filename.txt` - this is actually an entire text editing program (type text like normal)
    - write out is save and ^=control (^O) exit (^X)
- `wc` - print out the length of a file in lines, words, and characters

```
Practice Exercise

(1) Create a file with the touch command.
(2) Make a copy of the file using cp.
(3) Rename the original version of the file to something else with mv.
(4) Use nano to add different text to each copy and save it.
(5) View the contents of each file with cat.
(6) Check the sizes of each file with wc.
```

- `echo` - prints something to the screen (or elsewhere, as directed)
- `>>` - appends to file
    - `echo "some text here" >> myTextFile.txt`
- `>` - writes to (or over!) file
    - `echo "more text here" > myTextFile.txt`
- __WARNING - BIG WARNING - PAY ATTENTION__ - `rm` _permanently_ removes a file
    - No going back - always use this VERY carefully
    - I know people who've accidentally erased their __entire computers__ using this command
    - `rm -r` recursively removes a directory and everything inside it - even more dangerous than just `rm`!
    - This is the reason permissions are so important. If someone doesn't have write permissions on a file or folder, they shouldn't be able to delete it.
- `mkdir MyDirectory` - create a new (empty) directory (folder)
- `rmdir MyDirectory` - remove an empty directory !!WARNING!!
- wildcards - * is especially useful - matches anything
- `grep` - find only lines matching some particular string

```
Practice Exercise

(1) Create a series of new text files, with some filenames starting with one letter and some starting with another.
(2) Use echo and output redirection (> or >>) to add content to the files.
(3) With one command, list all the files that start with one particular letter.
(4) Make a new directory
(5) Move all files that start with one particular letter into the new directory.
(6) Try to remove that directory with rmdir. Can you?
(7) Extract all the lines from the files you created that contain one particular word of your choosing.
```

- [Notes about editing files and folders from the command line](https://github.com/FoundCompBio-Spr26/Shell_Week2/blob/main/CommandLine_Editing.md)

### Commands related to the Unix environment

- Can create a variable and assign value using `=`
    - `myVariable=2`
- Can print value of variable using `echo` and starting name with `$`
    - `echo $myVariable`
- `|` - the Unix pipe can be used to send the output of one command into the input of another
    - `history | tail -n 20 >> endOfHistory.txt`


Jake personal notes:
~ tildy - home directory

Ls = list, can put a further argument after
Shell = default what actually interprets commands, most common is bash


username@computer

Randomly assigned to either computer 1 or 2


[username@mike1] = command prompt

Pwd = print working directory, shows your path Ex. /home/jmath84/

Cd = change directory, put a space and then the extra piece (known as an argument). You could also do h, then tab it so it autocompletes

Ctrl + c cancels what you just typed 


NEVER use spaces in filenames

You can use CamelCase

Folders and directories are interchangeable

.. takes you to the parent directory (basically just takes you up one. So if I was in /work/jembrown/pps, it would take me to just /work/jembrown) 
. Is a shortcut for where I am currently 

Cat = short for concatenate, used to look at contents of 1 file

Nano is to edit the file

^ is ctrl

Flags are optional settings
Arguments

When you do ls -a, it shows all hidden files
When you do -l, it is a long list (helps show permission)
When you do -h flag, it makes it human readable . Ex. -lh for both long and human.
Hidden file names start with a period

doing man "command" will list all specific options for a command that can be used

If you do something like ls -lh, there's a code to understanding the formatting
rw-r--r-- 1 for instance
    R = read, W = write. Last set of 3 is anyone on the computer. Second is for anyone in the users group.


top command can be used to show resource usage in terminal
"q" can quit
