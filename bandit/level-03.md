# Level 2 -> 3

This level is fairly similar in concept to the previous one. The password is in a file that starts with `-`, but also contains spaces in its name.

The same two previous methods work, but with the caveat that you need to put single quotes surrounding the filename.

- ./ (path)
  - `cat ./'--spaces in this filename--'`
  - `cat /home/bandit2/'--spaces in this filename--'`
- < (take input)
  - `cat <'--spaces in this filename--'`
