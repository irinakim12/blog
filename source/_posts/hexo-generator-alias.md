---
title: Hexo Generator Alias
date: 2016-06-30 21:54:41
categories: 
	- Blog
tags:
	- blog 
	- hexo
	- plugin
	- hexo generator alias
	- redirect
	- alias
thumbnail: /images/404error.jpg
---

이번 포스트는 `Hexo Generator Alias`라는 플러그인에 대해 소개하겠습니다.
저는 _url Redirection_ 을 하기 위해 사용하였습니다.

얼마 전 **검색 엔진 최적화(SEO)**에 맞춰 url을 내용과 구체적으로 관련있게 하기위해 포스트 파일명의 이름을 변경하였습니다.
2번째 포스트인 [Hexo+GitHub pages](https://simhyejin.github.io/2016/06/20/hexo-github-pages/)은 포스트 파일 명이 `hexo-git` 에서 `hexo-github-pages` 으로 변경되었습니다.

![](/images/dup_hexo_git.png)

이미 색인된 상태인지 구글에 예전 페이지가 남아있어 404 에러를 발생시켰습니다. 
**구글 웹마스터 도구 > Google 색인 > URL 삭제**로 이전 URL을 삭제하였습니다. 하지만, 'url 오류'라는 **크롤링 오류**가 계속 발생하여 `Hexo Generator Alias 플러그인`으로 이전 URL을 현 URL로 Redirecion 하였습니다. 

---
## Hexo Generator Alias 플러그인
[Hexo Generator Alias](https://github.com/hexojs/hexo-generator-alias) : Generates alias pages for redirecting to posts, pages or URL.
URL, 페이지, 포스트로 리다이렉션하기 위한 에일리어스 페이지를 생성하는 플러그인이다.

#### 설치
터미널을 열고 **hexo**가 설치되어있는 **blog 폴더**에서 npm을 통해 `Hexo Generator Alias 플러그인`을 설치한다.
```bash
npm install hexo-generator-alias --save
```
---
#### 이용법
- Post file 에서 alias 
```md
alias: about/index.html

alias:
- about/index.html
- bar/index.html
```
또는 
- `_config.yml`에서 alias
```yml
alias:
  api/index.html: api/classes/Hexo.html
  plugins/index.html: https://github.com/tommy351/hexo/wiki/Plugins
```
---
#### 나의 사용기
저는 2번째 방법인 `_config.yml`에서 alias를 지정했습니다.
`이전 페이지 html path : 현재 페이지 html path`를 설정하시면 됩니다.
```yml
alias:
  /2016/06/20/hexo-git/index.html: /2016/06/20/hexo-github-pages/index.html
```
이로 인해 
https://simhyejin.github.io/2016/06/20/hexo-git/
--- `Redirection` ---> 
https://simhyejin.github.io/2016/06/20/hexo-github-pages/
이전 페이지 url을 눌러도 현 페이지로 이동합니다.
![](/images/redirection.png)
URL Redirect로 삭제된 페이지를 현 페이지에 연결하는 것은 좋은 방법이 아닌것 같습니다.
하지만, 404 에러를 발생시키는 이전 페이지 노출로 인해 URL Redirection을 해보았습니다.
`Hexo Generator Alias 플러그인`으로 리다이렉션 하는 법 말고 다른 좋은 방법을 아시는 분은 알려주세요:)

---
#### [#Blog](https://simhyejin.github.io/tags/blog/) [#Hexo](https://simhyejin.github.io/tags/hexo/) [#Plugin](https://simhyejin.github.io/tags/plugin/)
< 이전 포스트 [Hexo 테마 적용하기](https://simhyejin.github.io/2016/06/24/hexo-themes/)
