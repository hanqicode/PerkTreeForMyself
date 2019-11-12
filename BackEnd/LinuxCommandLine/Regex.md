# Regular Expression

`grep`(global regular expression print). `grep [options] regex [file...]`

`-i`: ignore case.

1. `ls /usr/bin | grep zip`: this will list all files in the /usr/bin directory whose names contain "zip".
1. `.`: match any character. Must have one digit.
1. `^` and `$`: they cause the match to occur only if the regex is found at the beginning/end of the line.
   Like: `grep '^zip' file.txt` or `grep 'zip$' file.txt`.

## Bracket Expression
1. `grep '[ah]an' file.txt`: match any line contains "aan" or "han" in file.txt.
1. `grep '[a-z]an' file.txt`: match any line contains "aan" to "zan" (a, b, c, ..., z).

## Quantifiers

`?`: match an element 0 or 1 time.

`*`: match an element 0 or more times.

`+`: match an element 1 or more times.
