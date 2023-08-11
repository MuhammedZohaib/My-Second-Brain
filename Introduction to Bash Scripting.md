Every Thing in Linux Unix is a file
# Commands:
`pwd` *Print working directory*
`ls` *Short for listings*
`ls -l` *Lists file in list order along with the read write permission* and owners and groups it belongs
`ls -a` *List all files in subdirectories including the hidden ones*
`ls -R -F`  *This will display everything even in sub-directories*
`cd ..` *Move back to parent directory*
`cd ~` *Move directly to home directory no matter where you're*
`cp` *To Copy*
`mv` *To move and Rename files*
`rm` *To delete files*
`rmdir` *To remove directories*
`mkdir` *To make new directory*
`cat` *To view content of a file*
`less` *To view content of a file page by page*
`head` *To view the first 10 lines*
`head -n "number"` *To view given number of lines as in flag*
`man` *To get help/manual about a command*
`cut` *To select columns*
`history` *To see History of used Commands*
`touch "filename here"` *Create a new file*
`ehco` *To print something on the terminal*
`wc` *Word count*
`grep` *Stands for global regular expression print*

In shell input is represented by 0, output by 1 and error by 2


**The shell decides if a path is absolute or relative by looking at its first character: If it begins with `/`, it is absolute. If it _does not_ begin with `/`, it is relative.**

* As shell doesn't have a trash can so once you delete file it cannot be recovered.
* Shell has a powerful function of auto-completion with `Tab`
* it's considered good style to put all flags _before_ any filenames, so in this course, we only accept answers that do that.

**`ls -R -F`** : `ls` has another flag `-F` that prints a `/` after the name of every directory and a `*` after the name of every run able program.


Unix preceded Linux and was developed by Ken Thompson and Denis Ritchie and team at AT&T Labs in 1969. Linux came in 1991 and was developed by Linus Torvalds as a hobby.


```bash
chmod 755 "filename here" # given a file permission for execution

wc filename -w

< # is used for standard input
> # standard output
grep -i "word to search" filename #return searched word intially and in between
grep "word to search" filename #matches the pattern only on start
grep -w "word" filename #return exact matches only
```