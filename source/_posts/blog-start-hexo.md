---
title: Hexo 정적 블로그 프레임워크
date: 2016-06-20 14:16:39
categories: 
	- Blog
tags:
	- blog 
	- hexo
	- 정적 블로그 프레임워크
	- git
	- Node.js
	- 헥소
	- Static Site Generator
thumbnail: /images/hexo.png
---

블로그 시작을 위해 사용하였던 [Hexo](https://hexo.io/) 를 소개합니다.

---
- 목차
	- [Hexo](#hexo)
	- [Hexo 설치](#hexo-install)
	- [Hexo 명령어](#hexo-command)
---

## <div id= "hexo">Hexo
_**Hexo**_ 는 _Node.js_ 기반 정적 블로그 프레임워크 입니다.

- **마크다운(Markdown)**을 지원하여 손쉬운 포스트 작성 가능 
- **GitHub Pages**를 이용한 호스팅을 지원
- 다양한 **테마** 제공

등 의 장점으로 이 블로그 또한 _Hexo_ 와 _GitHub Pages_ 로 제작되었습니다. 
**Hexo** 설치와 실행법에 대해 소개하겠습니다.

---
## <div id="hexo-install">Hexo 설치
**_Hexo_** 를 설치 하기 위해서는 `Node.js`와 `Git`이 설치 되어 있어야합니다.
아래의 링크를 통해 설치가 가능합니다.
- [Node.js](https://nodejs.org/en/)
- [Git](https://git-scm.com/)

_Node.js_ 와 _Git_이 설치되어 있다면 이제 **_Hexo_** 를 설치할 수 있습니다.

### 설치
터미널을 열어 명령어를 통해 **_Hexo_**를 설치합니다. 

``` bash
$ npm install -g hexo-cli
```

**_Hexo_** 가 설치 되었다면 아래의 명령어를 통해 `Hexo 폴더`를 초기 설정합니다.
(디렉토리명은 Github repo 이름과 달라도 무관합니다.) 

``` bash
$ hexo init <디렉토리명>
$ cd <디렉토리명>
$ npm install
```
위 과정이 끝나면 폴더안에 아래의 파일이 생성됩니다.

``` bash
.
├── _config.yml   : 사이트 설정 파일. 대부분의 설정 할 수 있습니다. 
├── package.json  : 응용 프로그램 데이터.  
├── scaffolds 	  : 새 게시물을 작성하면 Hexo는 scaffolds 폴더에 새로운 파일을 기반으로 하고 있습니다.
├── source 	  : 소스 폴더. 사이트 콘텐츠를 넣어두는 폴더입니다.
|   ├── _drafts 	
|   └── _posts 		
└── themes 	  : 테마 폴더. Hexo는 테마와 콘텐츠를 결합하여 정적 웹 사이트를 생성합니다.

```
### 실행
모든 설치가 끝났다면 내장 서버를 돌려봅니다.

``` bash
$ hexo server
```
`localhost:4000`을 통해 확인합니다.(기본포트 : 4000)

---
## <div id= "hexo-command">자주 쓰는 명령어
### New post
새로운 포스트 생성

``` bash
$ hexo new "My New Post"
```

### Generate
정적 파일 생성

``` bash
$ hexo generate
```
또는

```bash
$ hexo g
```
Opition으로 
-d , --deploy : generate가 끝난후 deploy
-w , --watch : 파일 변화 확인

### deploy
원격 사이트에 올리기

``` bash
$ hexo deploy
```
또는

```bash
$ hexo d
```
Opition으로 
-g , --generate : deploy 전에 generate

그 외에는 Hexo [Commands](https://hexo.io/docs/commands.html)에서 확인 할 수 있습니다.

---
#### [#Blog](https://simhyejin.github.io/tags/blog/) [#Hexo](https://simhyejin.github.io/tags/hexo/)
다음 포스트 > [Hexo+GitHub pages](https://simhyejin.github.io/2016/06/20/hexo-github-pages/)









