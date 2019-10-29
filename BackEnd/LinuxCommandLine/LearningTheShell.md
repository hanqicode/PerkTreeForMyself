# Learning the Shell

## What is The Shell?
The shell is a program that takes keyboard commands and passes them to the operating system to carry out.

Terminal Emulator looks like: `[me@linuxbox ~]$ `. Let's try some simple commands.

`date`: displays the current time and date.

`cal`(calendar): displays a calendar of current month.

`df`(disk filesystem): to see current amount of free space on your disk drivers.

`free`(free memory): to see the amount of free memory.

`exit`: ending a terminal session.

## Navigation
Linux always have a single file system tree, regardless of how many drives or storage devices are attached to the computer.

`pwd`(print working directory): to display the current working directory.

`ls`(list): to list the files and directories in the current working directory.

`cd`(change directory): to change your working directory.

## Exploring The System
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
