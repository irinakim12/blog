---
title: GitHub pages Hexo적용하기
date: 2016-06-20 16:37:00
categories: 
	- Blog
tags:
	- hexo
	- github-pages
thumbnail: "http://masatolan.com/images/2015/programming/1/hexo-blog-basic1.jpg"
---
## GitHub Pages 
`GitHub Pages`는 GitHub에서 무료로 호스팅하는 공개 웹페이지입니다. 
GitHub의 저장소에서 개인이나 조직 또는 프로젝트 페이지를 호스팅하도록 설계되어 있습니다. 
GitHub에서 제공하는 페이지 제작 도구로 쉽게 페이지를 만들어 공개할 수도 있고, 로컬에서 git을 이용해 수동으로 만들 수도 있습니다.

`GitHub Pages`의 종류는 크게 두가지로 나뉩니다. 

- 개인 사이트 GitHub Pages
- 프로젝트 사이트 GitHub Pages

**개인 사이트**는 `<username>.github.io`라는 저장소를 만들게되면 자동으로 개인 사이트를 위한 GitHub Pages를 만들 수 있습니다. 
이 사이트의 저장소 브랜치는 `master`에서 만들어져야 합니다.

**프로젝트 사이트**는 GitHub에 등록한 프로젝트별로 사이트를 자동으로 만들 수 있습니다. 
프로젝트 사이트는 `<username>.github.io/[프로젝트 저장소 이름]`으로 만들어집니다.
사이트의 저장소를 위한 브랜치가 `gh-pages`라는 브랜치이여야 합니다. 


이 블로그는 개인 사이트 Github Pages로 Github 저장소의 이름을 [simhyejin.github.io](simhyejin.github.io)로 설정하여 만들었습니다. 

GitHub Pages에 대한 자세한 내용은 [GitHub help](https://help.github.com/categories/github-pages-basics/)에서 확인할 수 잇습니다.

---
## Git pages에 Hexo 적용

먼저 `hexo-deployer-git`을 설치합니다.

```bash
$ npm install hexo-deployer-git --save
```
그 다음 

`_config.ym` 파일을 열어 `#deploymeny` 부분을 수정합니다.

```yml
deploy:
  type: git
  repo: https://github.com/Simhyejin/Simhyejin.github.io.git
  branch: master
```

`repo` 	: GitHub repository URL
`branch`	: 브랜치 이름 
`message`	: 커밋 내용. 커스터마이징 가능합니다. (*Site updated:'YYYY-MM-DD HH:mm:ss'* 로 기본 설정되있습니다.)

