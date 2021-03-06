#### List directories only: 
```bash
ls -d <location>*/
```  

#### Copy files with progress and speed shown:
```
rsync -avh --progress --ignore-times
```

#### set date and time directly from terminal:
```
sudo date -s "$(wget -qSO- --max-redirect=0 google.in 2>&1 | grep Date: | cut -d' ' -f5-8)Z"
```

#### vi search and replace
```
:%s/foo/bar/g
```

#### vi open multiple files simultaneously
```
vi FILE1 FILE2 ... -O/-o
```

#### bash print two file side by side 
```
pr FILE1 FILE2 -m 
```

#### bash follow a file every N seconds
```
watch -n N FILE
```
#### tree with file size
```
tree -h -d 1 --du /path/to/dir
```
#### Modify file without opening it
```
sed -i "s/string/replace/g" file
```
#### Check diskIO of processes
```
sudo iotop
```

#### Pass output to a argument
```
moveRun() {
  cwd=$(pwd)
  cd $1
  pwd
  cd $cwd
}

export -f moveRun
ls -d */ | xargs -n1 bash -c 'moveRun "$@"' _
```

#### tail with timestamp
```
tail -f outputfile | xargs -IL date +"%I:%M:%S %p"
```

#### vim search current word
```
*
```