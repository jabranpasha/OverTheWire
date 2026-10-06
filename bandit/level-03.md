# Level 2 -> 3

This level is fairly similar in concept to the previous one. The password is in a file that starts with `-`, but also contains spaces in its name.

Two of the previous methods work, but with the caveat that you need to put single quotes surrounding the filename, and they work for different reasons than before.

Rather than the command hanging, having a file start with `--` means the command will read the filename (before the first space if it's unqouted) as an option, and since it's an unrecognized option, an error is thrown.

- `./` (path)
  - By giving the path, the argument for the command no longer starts with `-`, so it doesn't read it as an option anymore.
  - Quotes are still needed unlike in the last level, because the shell splits on spaces and will read the filename as four arguments
  - `cat ./'--spaces in this filename--'`
  - `cat /home/bandit2/'--spaces in this filename--'`
- `<` (take input)
  - With `<` the contents of the file are directly passed into cat as stdin, so the filename isn't read at all by cat, quotes are still needed though for `<` to work correctly.
  - `cat <'--spaces in this filename--'`
- `--`
  - Putting this as the first argument will tell the command to no longer read any more options, even if they start with `-`, so the command works correctly, given you wrap it with quotes
  - `cat -- '--spaces in this filename--'`
