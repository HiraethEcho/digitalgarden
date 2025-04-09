---
{"dg-publish":true,"permalink":"/readme/","tags":["gardenEntry"]}
---


# Obsidian
This is my Obsidian Vault.

## List
```dataview
TABLE title, excerpt, tags, version
FROM "hexo"
SORT version DESC
```
## tags
```dataviewjs
dv.paragraph(
  dv.pages("").file.etags.distinct()
  .sort(t => dv.pages(t).length , 'desc')
  .map(
  	t => {
		return `[${t}](${t})`+"("+dv.pages(t).length+")"
	}
  ).array().join(" ")
)
```

## 最近编辑
```dataview
table WITHOUT ID file.link AS "标题",file.mtime as "时间"
from !"10 归档" and !"1 看板"
sort file.mtime desc
limit 5
```

## 归档
```dataviewjs
let ftMd = dv.pages("").file.sort(t => t.cday)[0]
let total = parseInt([new Date() - ftMd.ctime] / (60*60*24*1000))
let totalDays = "已使用 *Obsidian* "+total+" 天，"
let nofold = '!"misc/templates"'
let allFile = dv.pages(nofold).file
let totalMd = "共创建 "+
	allFile.length+" 篇文档"
let totalTag = allFile.etags.distinct().length+" 个标签"
let totalTask = allFile.tasks.length+" 个待办。 <br><br>"
dv.paragraph(
	totalDays+totalMd+"、"+totalTag+"、"+totalTask
)
```

<!--
```dataview
TABLE rows.file.link AS "link"
FROM "hexo"
GROUP BY tags
```

## 最近创建
```dataview
table WITHOUT ID file.link AS "标题",file.ctime as "时间"
from !"10 归档" and !"1 看板"
sort file.ctime desc
limit 5
```
-->
<!--stable:
```dataview
TABLE title, excerpt, tags
FROM "hexo"
WHERE version = "stable"
```
beta:
```dataview
TABLE title, excerpt, tags
FROM "hexo"
WHERE version = "beta"
```
rc:
```dataview
TABLE title, excerpt, tags
FROM "hexo"
WHERE version = "rc"
```
draft:
```dataview
TABLE title, excerpt, tags
FROM "hexo"
WHERE version = "draft"
```
others:-->
<!--
## Status
```dataview
TABLE rows.file.link AS "link"
FROM "hexo"
GROUP BY version
SORT version
```
-->
