# Level 4 -> 5

For this level, after navigating to the `inhere` directory, you have to find which of the 10 files is human-readable and contains the password.

I'm going to be honest, for my first attempt I just brute forced my way through this level by checking each file individually until I found one that was human-readable.

After some research I found out that you can use the `file` command to list what kinds of data are in each file

For this exercise, you would have to use `file` in the current directory to all files, so you can use the command `file ./*`. 
In this scenario, the `*` is a wildcard, which basically means anything can come after it and it the command will still run. Since all files start with `-`, going back to our earlier example we can use the absolute path to bypass this.

After running `file ./*` you get the following result
<img width="338" height="210" alt="image" src="https://github.com/user-attachments/assets/660bf186-10ba-4311-84b6-bb2998ba8a53" />

Then, simply running `cat ./-file07` will get you the result you need.
