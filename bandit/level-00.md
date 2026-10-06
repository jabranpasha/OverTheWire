# Level 00
The first thing I had to do was give myself a refresher on ssh and its formatting, and figure out how to ssh into the remote host in the first place.

The host name is given and the command to connect is
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
The option `-p 2220` is necessary to connect to the host because ssh by default uses port 22, but this server is hosted on port 2220.

Password was also given, this was just to figure out how to actually get into each level.
