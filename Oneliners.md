# Oneliners

### Dirty merge of dev trees
```
tar cJf myproj_$(( $(date +'%y%m%d') - 1 )).txz --exclude-from=myproj/.ignore myproj
rsync -avubPWe 'ssh -c blowfish' --exclude-from=myproj/.ignore root@remote.host:/srv/myproj/ myproj/
```
