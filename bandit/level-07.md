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

<img width="671" height="223" alt="image" src="https://github.com/user-attachments/assets/0ba662c6-28e3-4207-bb2c-88d1519bf87a" />

After doing some research, I learned a way to suppress error messages. You can do so, by sending the `stderr` flow into `/dev/null` folder, which is commonly called the "black hole folder", since it automatically deletes anything that's sent to it.

After doing the command `find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null`, you find the file where the password is located and `cat` it.
