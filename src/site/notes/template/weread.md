---
{"dg-publish":true,"permalink":"/template/weread/","title":{"{ metaData.title }":null},"created":"2025-06-28T17:48:48.602+08:00"}
---

# 元数据

![{{metaData.title}}|200]({{metaData.cover}})

> [!note] {{metaData.title}}
> - 书名： {{metaData.title}}
> - 作者： {{metaData.author}}
> - 简介： {{metaData.intro}}
> - 类型： {{metaData.category}}


# 高亮划线
{% for chapter in chapterHighlights %}
## {{chapter.chapterTitle}}
{% for highlight in chapter.highlights %}{% if highlight.reviewContent %}{% else %}> {{ highlight.markText |trim }}
{% endif %}{% endfor %}{% endfor %}


<!-- default -->

---
isbn: {{metaData.isbn}}
category: {{metaData.category}}
---
# 元数据
> [!abstract] {{metaData.title}}
> - ![ {{metaData.title}}|200]({{metaData.cover}})
> - 书名： {{metaData.title}}
> - 作者： {{metaData.author}}
> - 简介： {{metaData.intro}}
> - 出版时间 {{metaData.publishTime}}
> - ISBN： {{metaData.isbn}}
> - 分类： {{metaData.category}}
> - 出版社： {{metaData.publisher}}

# 高亮划线
{% for chapter in chapterHighlights %}
## {{chapter.chapterTitle}}
{% for highlight in chapter.highlights %}
{% if highlight.reviewContent %}{% else %}
- {{ highlight.markText |trim }}{% endif %}{% endfor %}{% endfor %}
# 读书笔记
{% for chapter in bookReview.chapterReviews %}{% if chapter.reviews or chapter.chapterReview %}
## {{chapter.chapterTitle}}
{% if  chapter.chapterReviews %}{% for chapterReview in chapter.chapterReviews %}
### 章节评论 No.{{loop.index}}
- {{chapterReview.content}}{% endfor%}{%endif %}{% if chapter.reviews %}{%for review in chapter.reviews %}
### 划线评论
- {{review.abstract |trim }}
    - {{review.content}}
{% endfor %}{%endif %}{% endif %}{% endfor %}
# 本书评论
{% if bookReview.bookReviews %}{% for bookReview in bookReview.bookReviews %}
## 书评 No.{{loop.index}} {{bookReview.mdContent}} ^{{bookReview.reviewId}}
{% endfor%}{% endif %}
