---
{"dg-publish":true,"permalink":"/manningfalting/fcitx/","created":"2025-06-24T16:25:29.872+08:00"}
---

`/usr/share/applications/wechat.desktop`
```
[Desktop Entry]
Name=wechat
Name[zh_CN]=微信
Exec=env XMODIFIERS="@im=fcitx" GTK_IM_MODULE="fcitx" QT_IM_MODULE="fcitx" /usr/bin/wechat %U
StartupNotify=true
Terminal=false
Icon=/opt/wechat/icons/wechat.png
Type=Application
Categories=Utility;
Comment=Wechat Desktop
Comment[zh_CN]=微信桌面版

```
