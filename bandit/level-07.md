# Level 6 -> 7

When I first started this level, I thought something was broken, since nothing appeared when I use the `ls` command. However, after taking a second look
at the instructions, I saw that it just said that the password was stored somewhere on the _server_, so the `find` command should still work.

We wanted to find a file that was:
- 33 bytes
- owned by user bandit7
- owned by group bandit 6

We can check for all of these things with the find options we've used so far, as well as using the `-user` and `-group` options.

`find / -type f -size 33c -user bandit7 -group bandit6`

Unfortunately, doing this produces a bunch of permission denied messages

<img width="690" height="249" alt="image" src="https://github.com/user-attachments/assets/ac8d35b9-9ab8-405d-b0bf-1ae36d4b90b3" />

After doing some research, I learned a way to suppress error messages. You can do so, by sending the `stderr` flow into `/dev/null` file, which is commonly called the "black hole", since it automatically discards anything that's sent to it.

Every program in Linux starts with these three streams:
- 0 (stdin)
- 1 (stdout)
- 2 (stderr)

0 is for inputs, 1 is for outputs, and 2 is for errors.

`2>/dev/null` outputs everything from the stderr stream into the black hole and discards it, so that what's left from our initial command is what we're looking for.

After doing the command `find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null`, you find the file where the password is located and `cat` it.
