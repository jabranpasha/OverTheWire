# Level 1 -> 2

This level seems fairly simple at first, just repeating what was done in the previous level. But using the `cat` command on a file called `-` isn't that simple.

Bash thinks reads - as an option to the command instead of trying to read `-` as the name of a file.

After doing some research I found three ways to get past that issue and read the contents of the file.

- ./ (path)
  - By putting the absolute path in the command, you can read the file
  - `cat /home/bandit1/-`
- -- (delimiter)
  - By
- < (take input)
  - By taking the input of the file with `<` and inputting that into the cat command, you can read the file
