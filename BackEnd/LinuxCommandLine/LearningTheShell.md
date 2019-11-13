# Learning the Shell

## 1 - What Is The Shell?
The shell is a program that takes keyboard commands and passes them to the operating system to carry out.

Terminal Emulator looks like: `[me@linuxbox ~]$ `. Let's try some simple commands.

`date`: displays the current time and date.

`cal`(calendar): displays a calendar of current month.

`df`(disk filesystem): to see current amount of free space on your disk drivers.

`free`(free memory): to see the amount of free memory. `free -h`: to display for human.

`exit`: ending a terminal session.

## 2 - Navigation
Linux always have a single file system tree, regardless of how many drives or storage devices are attached to the computer.

`pwd`(print working directory): to display the current working directory.

`ls`(list): to list the files and directories in the current working directory.

`cd`(change directory): to change your working directory.

## 3 - Exploring The System
`ls -l`(list with long format): list with more details.

It will print out like below:
```bash
-rw-r--r--@ 1 qihan  staff  423 Oct 18 20:21 Demo.iml
drwxr-xr-x  3 qihan  staff   96 Oct 18 20:21 src
```
Introduce briefly:

- About access right:
For the 1st column, it represents access rights to the file. "-" means a regular file; "d" means a directory.
For next 3 chars, are the access rights for the file's owner.
For next 3 chars, are for members of the file's group.
For last 3 chars, are for everyone.

- 1/3: File's numbeer of hard links.

- qihan: file owner.

- staff: group which owns the file.

- 423/96: size of file in bytes.

`file`: check a file's type. 

Like: `file Demo.iml`. Output: `Demo.iml: XML 1.0 document text, ASCII text`

`less`: to view text files. Press "q" to quit.

Introduce commands briefly in less:
- /characters: search forward to next occurence of characters.
- n: search for next occurence of previous search.
- q: quit less.

> Less Is More. The less program was designed to replace more with more features.

## 4 - Manipulating Files And Directories

Wildcard - allows you to select filenames based on patterns of characters.

| Wildcard      | Meaning                        |
|---------------|--------------------------------|
| *             | Match any characters           |
| ?             | Match any Single character     |
| [characters]  | Match any character in set     |
| [!characters] | Match any character Not in set |

`cp`(copy): copy files and directories.

`mv`(move): move and rename files.

`mkdir`(make directory): to create directory. E.g. `mkdir dir1 dir2 dir3` can make 3 directories at same time.

`rm`(remove): remove files and directories. E.g. `rm -r dir` to remove a directory.

`ln`(link): create a hard or symbolic links.

## 5 - Working With Commands

`type`: display a command's type. 

`which`: display an executable's location.

`help`: get help for shell builtins. 

`man`(manual): display a program's manual page.

`info`: display a program's info.

`whatis`: display a very brief description of a command.

`alias`: create own commands. Like: `alias foo='cd /usr; ls'`

## 6 - Redirection

`>`: redirect standard output to another file. Like: `ls -l /usr/bin > ls-output.txt`

`>>`: redirect standard output and **append** to a file.

`|`: Pipeline. Like: `command1 | command2` the stardard **output** of command1 can be piped into the standard **input**
of command2.

`cat`(concatenate): read one/more files and copies them to standard output.

`sort`: sort the order.

`uniq`: uniq is often used in conjunction with sort. Remove any duplicates from the list.

`grep`: print lines matching a pattern. `grep pattern [file1 file2 ...]`

`wc`(word count): display the number of lines, words, and bytes contained in files. 

Like: `wc test`.
Output: `       1       5      28 test` (lines, words, bytes)

`head -n N`: print first N lines of a file. Like: `head -n 2`.

`tail -n N`: print last N lines of a file. `tail -f [fileName]`: continue to monitor the file, until you type Ctrl-C.

## 7 - Seeing The World As The Shell Sees It

`echo`: prints out its text **arguments** on standard output. So it will print text actual value.
1. arithmetic expansion: `echo $((2 + 2))`.

## 8 - Advanced Keyboard Tricks
`clear`: clear the screen.

`history`: display history of commands used.

Cursor Movement Commands:
`ctrl + a`: move to the beginning of the line.
`ctrl + e`: move to the end of the line.

## 9 - Permission
`id`(identity): display user identity.

`chmod`(change file mode): to change the mode of a file or directory.
chmod <octal(base_8) number>, because octal number represents 3 binary digits -> read, write, execute.

`sudo`(super user do).

`chown`(change file owner and group).

## 10 - Processes
`ps`(process): provide a snapshot of the machine's state at the moment.
```
  PID TTY           TIME CMD
48240 ttys000    0:00.72 /bin/zsh --login -i
58881 ttys001    0:00.05 /Applications/iTerm.app/Contents/MacOS/iTerm2 --server login -fp qqihan
58883 ttys001    0:00.68 -zsh
```
As we can see: 
- PID(Process ID) is in ascending order. 
- TTY(Teletype) refers to controlling terminal for the process.
- TIME is the amount of CPU time consumed by the process.

We can use `px aux` to see more information, including CPU percentage, MEM percentage.

`top`: to see a dynamic view of a machine's activity.

`kill`: kill processes to terminate programs. `kill -<single> <PID>` -> `kill -9 1234`
