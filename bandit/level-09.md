# Level 8 -> 9

For this level, we want to print the only line in `data.txt` that never repeats itself.

We can do this by piping together two commands, `sort`, and `uniq`.

`sort` is used to put everything in alphabetical order, and places duplicate lines adjacent to one another, which is important for the way `uniq` works.

`uniq` removes duplicate lines that appear _consecutively_

`uniq -u` removes _all_ duplicate lines that appear consecutively so if we were to just do `uniq -u` to `data.txt`, we wouldn't get the result we want since the duplicates are all mixed in with one another.

By combining the two, we get the desired output

<img width="386" height="21" alt="image" src="https://github.com/user-attachments/assets/2c55f051-dd96-458b-80ef-df23db1b51d6" />
