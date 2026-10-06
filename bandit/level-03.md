# Level 2 -> 3

This level is fairly similar in concept to the previous one. The password is in a file that starts with `-`, but also contains spaces in its name.

Two of the previous methods work, but with the caveat that you need to put single quotes surrounding the filename, and they work for different reasons than before.

Rather than the command hanging, having a file start with `--` leaves the command waiting for an option instead of an input.

- ./ (path)
  - By giving the path, the command no longer starts with `-`, so it doesn't read it as an option anymore.
  - `cat ./'--spaces in this filename--'`
  - `cat /home/bandit2/'--spaces in this filename--'`
- < (take input)
  - `cat <'--spaces in this filename--'`
