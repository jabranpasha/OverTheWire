# Level 5 -> 6

To find  password in this level you need to use the `find` command to find a file that has a specific size (1033 bytes), and is not executable.

We can accomplish this by doing the following:
- using the `-size` option.
- negating the `-executable` option with !
- using the `-type` option to filter for files
- starting from the starting directory with `.`

This results in this command

`find . -type f -size 1033c ! -executable`

We find that the password is located here

<img width="706" height="46" alt="image" src="https://github.com/user-attachments/assets/e4340ff0-7f80-4285-acd3-f207d0a2ed94" />
