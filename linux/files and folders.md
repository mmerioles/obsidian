`touch file1` - create the file, and can see timestamp with `ls -l`
`mkdir test-folder` - create folder

drwxrwxr-w - the d shows that its a directory

`mv file1 test-folder` - move the file into the directory (trick: use this to rename files)

`cp file1 file2` - copy creates a new one

if you have a really long file...

cat
=

`cat /var/log/dmesg | more`

Piping into more, lets you search page by page (searchable by /)

`cat /var/log/dmesg | less` - you can use this one to fine extra functionality

`which ping` useful for searching for programs

`echo "this file was made by echo" > file3` 

`>>` using two like this appends to the file

`cat <<EOF > file4`
`This is a test
`I am making lines`
`EOF`

It lets you make a file like this and keep typing

To combine files together
`cat file1 file2` - combines the two files!

filtering output
=

you can pipe output into programs like grep

`cat final-file | grep poker` find the poker in the file
`cat final-file | grep -i ine` - match insensitive
`cat final-file | grep -v this` - filter by anything but

substitutions
=

to normalize output or something
`cat final-file | sed "s/file/notebook"` (note it only makes one change per line)
if you want to do global add `/g`

`sed -i "s/notebook/video/g"` new-file : directly edit the file using -i

filter based on col
=

`cat new-file | awk '{print $1}'` - print the first col word





