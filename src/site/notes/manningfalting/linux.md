---
{"dg-publish":true,"permalink":"/manningfalting/linux/","created":"2025-06-01T15:08:46.086+08:00"}
---

https://github.com/SuperManito/LinuxMirrors

```
bash <(curl -sSL https://linuxmirrors.cn/main.sh)
```

```
bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
```

```
bash <(curl -sSL https://linuxmirrors.cn/docker.sh) --only-registry
```

use following to find file type. `-L` means follow the symbolic link

```
file --mime-type -L file
```

use following shell scripts to set mime (need rofi)

```sh
#!/bin/sh

FILETYPE=$(xdg-mime query filetype $1)
APP=$( find /usr/share -type f -name "*.desktop" -printf "%p\n" | sed 's/\/.*\///g' | rofi -threads 0 -dmenu -i -p "select default app")
echo $APP
xdg-mime default "$APP" "$FILETYPE"
echo "$APP set as default application to open $FILETYPE"
```

`stat`展示文件状态，例如
```
stat /

  File: /
  Size: 122       	Blocks: 0          IO Block: 4096   directory
Device: 0,28	Inode: 256         Links: 1
Access: (0755/drwxr-xr-x)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2025-05-10 23:46:03.122616066 +0800
Modify: 2025-05-11 21:26:49.474145593 +0800
Change: 2025-05-11 21:26:49.474145593 +0800
 Birth: 2025-01-01 14:58:38.377746860 +0800
```
