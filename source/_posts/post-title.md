---
title: '[Markdown] title 대괄호[] 사용하기'
date: 2016-06-24 15:22:11
tags:
	- hexo
	- post
	- title
	- markdown
categories: 
- Blog
thumbnail: /images/title.png
sitemap: false
---

`Hexo`로 블로그를 운영하며 `마크다운(Markdown)`을 사용하여 포스트를 작성하고 있습니다.
포스트 제목 앞에 **대괄호**를 썻더니 오류가 발생하였습니다. 이에 대한 해결방안을 가져왔습니다.

## YAMLException: can not read a block mapping entry 해결하기

![](/images/post-head.png)
위 사진과 같이 포스트를 작성할 때 title 앞에 대괄호를 넣으면 아래와 같은 Error가 발생합니다.

```bash
ERROR Process failed: _posts/test.md
YAMLException: can not read a block mapping entry; a multiline key may not be an implicit key at line 2, column 5:
    date: 2016-06-24 15:19:38
        ^
```

---

해결방법은 간단합니다.
아래와 같이 title을 **"" 큰따옴표** or **'' 작은따옴표**로 감싸주시면 됩니다.

![](/images/post[].png)

문제해결 완료 :)
