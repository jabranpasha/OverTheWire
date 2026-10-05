# Level 1 -> 2

This level seems fairly simple at first, just repeating what was done in the previous level. But using the `cat` command on a file called `-` isn't that simple.

`cat` reads `-` as standard input (stdin) instead of a file name, so it just hangs there waiting for you to type something.

After doing some research I found two ways to get past that issue and read the contents of the file.

- ./ (path)
  - By putting the absolute path in the command, you can read the file
  - `cat /home/bandit1/-`
- < (take input)
  - By taking the input of the file with `<` and inputting that into the `cat` command, you can read the file
  - `cat <-`
