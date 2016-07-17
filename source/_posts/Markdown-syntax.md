---
title: '[Markdown] 마크다운 문법'
date: 2016-06-30 01:41:00
categories: 
	- Blog
tags:
	- markdown
	- 마크다운
	- markdown syntax
	- 마크다운 문법
thumbnail: /images/Markdown-help-thumbnail.jpg
---
마크다운 문법에 대해 소개하겠습니다. 

---
- <div id="index">목차
	- [제목 Headers](#headers)
	- [인용 Blockquotes](#blockquotes)
	- [코드 블럭 Code Blocks](#code-blocks)
	- [인라인 코드 Inline Code Blocks](#inline-code-blocks)
	- [강조 Emphasis](#emphasis)
	- [수평선 Horizontal Rules](#horizontal)
	- [링크 Links](#link)
		- [외부 링크 External Links](#external-link)
		- [내부 링크 Internal (Anchored) Links](#internal-link)
	- [리스트 Lists](#list)
		- [순서 있는 리스트 Ordered Lists](#ordered-list)
		- [순서 없는 리스트 Unordered Lists](#unordered-list)
	- [테이블 Tables](#tables)
	- [이미지 Adding Images](#images)
	- [각주 Footnotes](#footnote)

---
## <div id="markdown-syntax">마크다운 문법
#### <div id="headers">제목 Headers
`#`으로 시작하는 텍스트. 
`#`은 하나부터 여섯개까지 쓸 수 있고, `#`이 늘어날때마다 제목의 수준은 내려간다.
(보통 글씨 크기가 작아진다.)

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| \# h1<br>\#\# h2<br>\#\#\# h3<br>\#\#\#\# h4<br>\#\#\#\#\# h5<br>\#\#\#\#\#\# h6         | <h1> h1<br><h2> h2<br><h3> h3<br><h4> h4<br><h5> h5<br><h6> h6        | 

또는 `-`, `=`을 이용하여 h1, h2를 쓸 수 있다.

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| h1<br>===<br><br>h2<br>--- | <h1> h1<br><h2> h2 |

---

#### <div id="blockquotes">인용 Blockquotes
`>`으로 시작하는 텍스트

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| > 인용문   | <blockquote> 인용문 </blockquote>     | 
| >> 인용문안의 인용문    | <blockquote> 인용문 <blockquote> 인용문 </blockquote></blockquote>     | 

---

#### <div id="code-blocks">코드 블럭 Code Blocks
<code>\`\`\`</code> 혹은 <code>\~\~\~</code> 코드 첫 줄과 마지막 줄에 Back quote ( \` ) 또는 물결( ~ ) 3개 삽입

| 마크다운 | 실행결과 |
| ---------- | :--------: | 
| \`\`\`<br>이것은<br>코드 블럭<br>입니다<br>\`\`\`<br><br>\~\~\~<br> 이것은 <br>코드 블럭<br>입니다<br>\~\~\~ | <figure class="highlight bash"><table><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br></pre></td><td class="code"><pre><span class="line">이것은</span><br><span class="line">코드 블럭</span><br><span class="line">입니다</span><br></pre></td></tr></table></figure><br><figure class="highlight bash"><table><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br></pre></td><td class="code"><pre><span class="line">이것은</span><br><span class="line">코드 블럭</span><br><span class="line">입니다</span><br></pre></td></tr></table></figure>|
| \`\`\`c<br>void f()<br><pre>    printf(%s,“이것은 c 코드 입니다”);</pre>}<br>\`\`\` |<figure class="highlight c"><table><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br></pre></td><td class="code"><pre><span class="line"><span class="function"><span class="keyword">void</span> <span class="title">f</span><span class="params">()</span></span>&#123;</span><br><span class="line">	<span class="built_in">printf</span>(%s,<span class="string">"이것은 c 코드 입니다"</span>);</span><br><span class="line">&#125;</span><br></pre></td></tr></table></figure>|

---
#### <div id="inline-code-blocks">인라인 코드 Inline Code Blocks
<code>\`(Back quote)</code>로 감싸진 텍스트

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| \`인라인 코드 블럭\` | `인라인 코드 블럭`    | 

---
#### <div id="emphasis">강조 Emphasis
기울여 쓰기(italic) : `*` 또는 `_`로 감싼 텍스트
굴게쓰기(bold) : `**` 또는 `__`로 감싼 텍스트

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| \*기울여쓰기(italic)\*<br>\_기울여쓰기(italic)\_<br><br>\*\*굵게쓰기(bold)\*\*<br>\_\_굵게쓰기(bold)\_\_ | *기울여쓰기(italic)*<br>_기울여쓰기(italic)_<br><br>**굵게쓰기(bold)**<br>__굵게쓰기(bold)__ |

---
#### <div id="horizontal">수평선 Horizontal Rules
`-` 또는 `*` 또는 `_` 을 3개 이상 작성
(단, `-`을 사용할 경우 header로 인식할 수 있으니 이 전 라인은 비워두어야한다.) 

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| \-\-\- | <hr> |
| \*\*\* | <hr> |
| \_\_\_ | <hr> |

---
#### <div id="link">링크 Links
##### <div id="external-link">외부 링크 External Links
`[링크](http://example.com "링크 제목")` 인라인 링크
`[링크1][1]` `[1]: http://example1.com/ "링크제목1"` 참조 링크
`<example.com/>` `<example@example.com>` url 링크

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| **인라인 링크** <pre>\[Google\](http://www.google.co.kr "구글")</pre> | <br>[Google](http://www.google.co.kr "구글")|
| **참조 링크** <br>\[Google\]\[1\]<br>\[Naver\]\[2\]<br>\[1\]: http://google.com/ "구글"<br>\[2\]: http://naver.com/ "네이버" | <br>[Google][1]<br>[Naver][2]|
| **URl 링크**<br>&#60;http://google.com/<span>&#62;</span><br>&#60;example@gmail.com/&#62;| <br><http://google.com><br><example@gmail.com> |


[1]: http://google.com/ "구글"
[2]: http://naver.com/ "네이버"

---
##### <div id="internal-link">내부 링크 Internal (Anchored) Links
`[링크](#id)` 내부 링크

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| \[목차\](#index) | [목차](#index) |
---
#### <div id="list">리스트 Lists
##### <div id="ordered-list">순서 있는 리스트 Ordered Lists
`No. ` 숫자 다음 .을 찍는다. (적힌 숫자랑 상관없이 순서대로 번호가 매겨진다.)

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| 1. list item 1<br>1. list item 2<br>2. list item 3<br>0. list item 4<br>3. list item 5 | <ol><li>list item 1</li><li>list item 2</li><li>list item 3</li><li>list item 4</li><li>list item 5</li></ol> |

---
##### <div id="unordered-list">순서 없는 리스트 Unordered Lists
`*`, `+`, `-` 으로 시작

| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| \* list item 1<pre>	\* list item 1-1</pre><pre>	\* list item 1-2</pre> | <ul><li>list item 1</li><ul><li>list item 1-1</li><li>list item 1-2</li></ul></ul> |
| \+ list item 1<pre>	\+ list item 1-1</pre><pre>	\+ list item 1-2</pre> | <ul><li>list item 1</li><ul><li>list item 1-1</li><li>list item 1-2</li></ul></ul> |
| \- list item 1<pre>	\- list item 1-1</pre><pre>	\- list item 1-2</pre> | <ul><li>list item 1</li><ul><li>list item 1-1</li><li>list item 1-2</li></ul></ul> |
---
#### <div id="tables">테이블 Tables
| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| **테이블 생성**<br>Header 1  &#124; Header 2<br>&#45;&#45;&#45;&#45;&#45;&#45;&#45;&#45;&#45; &#124; &#45;&#45;&#45;&#45;&#45;&#45;&#45;&#45;&#45;<br>Content 1  &#124; Content 3<br>Content 2  &#124; Content 4 | <br><table><thead><tr><th>Header 1</th><th>Header 2</th></tr></thead><tbody><tr><td>Content 1</td><td>Content 3</td></tr><tr><td>Content 2</td><td>Content 4</td></tr></tbody></table> |
| **테이블 정렬**<br>&#124; Header 1  &#124; Header 2  &#124; Header 3  &#124;<br>&#124; :&#45;&#45;&#45;&#45;&#45;&#45;&#45;&#45; &#124; :&#45;&#45;&#45;&#45;&#45;&#45;&#45;&#45;: &#124; &#45;&#45;&#45;&#45;&#45;&#45;&#45;&#45;: &#124;<br>&#124; Left       &#124; Center       &#124; Right       &#124; | <br><table><thead><tr><th style="text-align:left">Header 1</th><th style="text-align:center">Header 2</th><th style="text-align:right">Header 3</th></tr></thead><tbody><tr><td style="text-align:left">Left</td><td style="text-align:center">Center</td><td style="text-align:right">Right</td></tr></tbody></table>|

---
#### <div id="images">이미지 Adding Images
| 마크다운 | 실행결과 | 
| ---------- | :--------- | 
| **인라인 이미지**<pre>!&#91;alt text&#93;&#40;/test.png &#41;</pre>| ![alt text](/images/test.png) |
| **링크 이미지**<pre>!&#91;alt text&#93;&#40;image_URL&#41;| ![alt text](https://simhyejin.github.io/images/test.png) |
| **참조 이미지**<br>!&#91;alt text&#93;&#91;1&#93;</br>&#91;1&#93;: /test.png | ![alt text][3] |
[3]: /images/test.png

---
#### <div id="footnote">각주 Footnotes
각주입니다[^id]
[^id]: 각주에 대한 설명. 
>GitHub에서는 footnote를 지원해주지 않는다.

---
#### [#Blog](https://simhyejin.github.io/tags/blog/) [#Markdown](https://simhyejin.github.io/tags/markdown/)
< 이전 포스트 [[Markdown] title 대괄호[] 사용하기](https://simhyejin.github.io/2016/06/24/markdown-post-title/)


