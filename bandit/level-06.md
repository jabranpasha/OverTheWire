# Level 5 -> 6

To find  password in this level you need to use the `find` command to find a file that has a specific size (1033 bytes), and is not executable.

We can accomplish this by doing the following:
- using the `-size` option.
- negating the `-executable` option with !
- using the `-type` option to filter for files

This results in this command
`find . -type f -size 1033c ! -executable`

Like so: `find -size 1033c`.

We find that the password is located here

<img width="421" height="45" alt="image" src="https://github.com/user-attachments/assets/3dc90eda-b94b-46d7-9998-2f197620b0ae" />
