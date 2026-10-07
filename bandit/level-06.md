# Level 5 -> 6

To find  password in this level you need to use the `find` command to find a file that has a specific size (1033 bytes), is human-readable, and is not executable.

We can accomplish this by doing the following:
- using the `-size` option with a c (representing bytes) after 1033
- negating the `-executable` option with !
- using the `-type` option to filter for files
- starting from the current directory with `.`
- checking if the file is human-readable with the `file` command

You can use the following command `find . -type f -size 1033c ! -executable`, and then a `file` command on the resulting file, or you can do it in one line.

I initially thought to use piping with `|` to do the command in one line, but piping takes the output of one command and sends it to the other's `stdin`, but `file` reads filenames from its arguments, not from `stdin`


After some research I discovered that you can combine the two by using the `-exec` option for find, which basically says to execute a command (which you would put after the -exec) for whatever file you find.

The combined one-line answer for this level would be
`find . -type f -size 1033c ! -executable -exec file {} \;`
- The {} is a placeholder for the file location that we get from the find command, and the \; tells it to stop searching.

<img width="911" height="47" alt="image" src="https://github.com/user-attachments/assets/f56961d5-7007-41c3-bbf0-0929074b7cac" />

Finally, we run the cat command on file `.file2` and get the password we need
