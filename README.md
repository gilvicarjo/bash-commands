# bash-commands

# List when commited git files with a certain extension (.tf) were modified
```
$ for i in $(ls -lh | awk -F ' ' '{print $9}'); do echo -n "$i " && git log --follow --format=%ad --date default $i | tail -1; done | grep .tf | awk -F ' ' '{print $1,$3,$4,$5}'
```
ou

```
$ for i in $(ls -lth | awk -F ' ' '{print $9}'); do echo -n "$i " && git log --follow --format=%ad --date format:'%Y-%m-%d %H:%M:%S' $i | tail -1; done | grep .tf | awk -F ' ' '{print $1,$2,$3}' | grep 2022
```

