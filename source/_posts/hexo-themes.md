---
title: Hexo 테마 적용하기
date: 2016-06-24 16:11:20
categories: 
	- Blog
tags:
	- blog 
	- hexo
	- themes
	- hueman
	- thumbnail
	- disqus
	- theme color
thumbnail: /images/hueman.jpg
---
이전 포스트 [Hexo+GitHub pages](https://simhyejin.github.io/2016/06/20/hexo-github-pages/)에서 _Hexo_ 와 _GitHub Pages_를 연동하여 블로그를 만들었습니다. 

이번 포스트는 테마를 바꿔 블로그를 꾸며 보도록 하겠습니다.
**_Hexo_** 는 다양한 테마를 지원해 줍니다. [Hexo Themes](https://hexo.io/themes/) 에서 원하는 테마를 고를 수 있습니다. 
데스크탑, 태블릿, 모바일 등 지원 가능한 반응형 테마를 고르기 위해 **responsive**을 검색하였고 그 중 [Hueman](https://github.com/ppoffice/hexo-theme-hueman)이라는 테마를 적용하엿습니다.
`Hueman` 테마 적용법과 테마 설정(CSS 수정, Thumbnail, Disqus)에 대해 소개하겠습니다.

---
- 목차
	- [Hueman 테마 적용하기](#hueman)
		- [Hueman 설치](#hueman-install)
		- [Hueman 설정](#hueman-config)
	- [Theme Color](#theme-color)
	- [Thumbnail](#thumbnail)
	- [Disqus](#disqus)
---

## <div id= "hueman">Hueman 테마 적용하기
### <div id= "hueman-install">설치

1. 터미널을 열어 `hexo init`했던 폴더(이하 **blog** 폴더)에 들어갑니다. Heuman 테마를 `themes/hueman` 폴더에 clone합니다.
```bash
$ cd blog
$ git clone https://github.com/ppoffice/hexo-theme-hueman.git themes/hueman
```

2. **blog** 폴더에 있는 `_config.yml`에서 `##Theme` 부분을 _landscape_ 에서 _hueman_ 으로 수정합니다.
```yml
## Themes: https://hexo.io/themes/
theme: hueman
```
3. **themes/hueman** 폴더에 있는 `_config.yml.example`를  `_config.yml`로 바꿉니다.
4. (Optional) 최신 버전을 다운 받기위해 pull해줍니다. 
```bash
$ cd themes/hueman
$ git pull
```
5. (Optional) Hueman 테마의 `Insight Search` 검색엔진을 사용하기위해 npm으로 `hexo-generator-json-content`을 설치합니다.
```bash
$ npm install -S hexo-generator-json-content
```

### <div id= "hueman-config">설정
**themes/hueman** 폴더에 있는 `_config.yml`에서 아래의 테마 설정을 바꿀 수 있습니다.
- Theme 
	- `Menu`
	- `Customize`(Logo, Thema Color, Highlight, Sidebar, Thumbnail, Favicon, Social Links)
- Widgets : Recent Posts, Category, Archive, Tag, Tag Cloud, Links
- Search 
- Comment : Disqus
- Share 
- Plugins
- Miscellaneous

---
### <div id= "theme-color">- Theme Color
저는 제 로고의 보라색을 따와 `Theme Color`를 보라색으로 설정했습니다. 
Hueman 테마의 `Theme Color`는 오른쪽 사이드바의 `Follow`영역의 색을 바꾸게 해줍니다. 
또한 `Theme Color`는 이외에도 여러군데 사용이됩니다. 
- 게시물 hover
- 글자 드래그
- 링크
등이 `Theme Color`가 적용됩니다. 
저의 `Theme Color` 보라색인 링크 글씨과 검은색 글씨의 눈으로 보기에 차이가 나지않아서 링크 글씨의 색을 지금 보이는 것과 같은 [하늘색](https://simhyejin.github.io/2016/06/24/hexo-themes/)으로 바꾸었습니다.

** [링크 색 바꾸기] **
**themes/hueman/source/css/_partial** 폴더의 `article.styl` 파일을 수정하면 됩니다.

```styl
.article-entry
    //...
    a //링크 
        color: "원하는색상" 
    //...
```
이 외에도 `styl 파일`을 수정하면 커스터마이징 가능합니다. 

---
#### <div id= "thumbnail"> - Thumbnail
**themes/hueman** 폴더에 있는 `_config.yml`에서 _true_, _false_ 로 설정 할 수 있습니다.
```yml
customize:
	thumbnail: true # enable posts thumbnail, options: true, false
```
![thumbnail: false | thumbnail: true](/images/thumbnail.png)

- **포스트에 thumbnail  추가하기**
`source/images`에 이미지 파일을 넣고 포스트 [font-matter](https://hexo.io/docs/front-matter.html)에 `thumbnail`을 추가하고 이미지 경로를 넣어줍니다.
```md
---
title: Hexo 테마 적용하기
date: 2016-06-24 16:11:20
thumbnail: /images/hueman.jpg
---
```
혹은 이미지 url인 경우에는 `thumbnail`을 추가하고 이미지 경로 url을 넣어줍니다.
```md
---
title: Hexo 테마 적용하기
date: 2016-06-24 16:11:20
thumbnail: https://example.com/image.jpg
---
```

---
#### <div id= "disqus"> - Disqus
**themes/hueman** 폴더에 있는 `_config.yml`에서 `#Comment` 부분의 _disqus_ 에 _disqus shortname_을 적어줍니다.
```yml
# Comment
comment:
    disqus: [Disqus Shortname] # enter disqus shortname here
```
**[ShortName 만들기 및 확인하기]**
먼저 [Disqus](https://disqus.com/) 계정이 있어야합니다. 회원가입 또는 SNS(페이스북, 트위터, 구글)로 로그인 가능합니다.
0. Get Started 클릭 후 블로그 이름 설정(예시: aaaaba)[※블로그 이름이 Short Name으로 설정됩니다] 
![](/images/Disqus1.png)
0. 왼쪽 General 클릭하면 ShortName 확인 할수 있습니다.
![](/images/Disqus2.png)

---

#### [#Blog](https://simhyejin.github.io/tags/blog/) [#Hexo](https://simhyejin.github.io/tags/hexo/)
< 이전 포스트 [Hexo+GitHub pages](https://simhyejin.github.io/2016/06/20/hexo-github-pages/)
다음 포스트 > [Hexo Generator Alias](https://simhyejin.github.io/2016/06/30/hexo-generator-alias/)



