---
{"dg-publish":true,"permalink":"/wiki/code/arch/archwiki/","title":"ArchWiki摘抄","tags":["arch","linux","handbook"],"created":"2025-06-04T22:04:15.520+08:00"}
---


# ArchWiki摘抄


## font

find the font that contains chinese

```sh
fc-list -f '%{file}\n' :lang=zh
```

check monospace

```sh
fc-match monospace
```

set fallback fonts, edit `$XDG_CONFIG_HOME/fontconfig/fonts.conf`:

```text
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
<alias>
   <family>serif</family>
   <prefer>
     <family>LXGW Wenkai mono</family>
   </prefer>
 </alias>
<alias>
   <family>monospace</family>
   <prefer>
     <family>CodeNewRoman Nerd Font</family>
     <family>LXGW Wenkai mono</family>
   </prefer>
 </alias>
</fontconfig>

```
