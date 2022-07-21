# bash-commands

# List when commited git files with a certain extension were modified
````
$ for i in $(ls -lh | awk -F ' ' '{print $9}'); do echo -n "$i " && git log --follow --format=%ad --date default $i | tail -1; done | grep .tf | awk -F ' ' '{print $1,$3,$4,$5}'
