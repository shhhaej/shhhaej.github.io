---
title: "[GitHub Blog] Jekyll 테마 적용"
excerpt: "Github 블로그 테마 적용"

categories:
  - GitHub Blog
tags:
  - [GitHub Blog, Git, 깃허브 블로그]

permalink: /github-blog/

toc: true
toc_sticky: true
 
date: 2022-08-26
last_modified_at: 2022-08-26

# sitemap :
#   changefreq : daily
#   priority : 1.0
---

## 테마 선택

테마를 볼 수 있는 사이트가 있다.<br>

<span style="color:gray">- [jekyll-themes.com](https://jekyll-themes.com/)</span><br>
<span style="color:gray">- [jekyllthemes.io](https://jekyllthemes.io/)</span><br>
<span style="color:gray">- [jekyllthemes.org](http://jekyllthemes.org/)</span><br>
<span style="color:gray">- [jamstackthemes.dev](https://jamstackthemes.dev/ssg/jekyll/)</span><br>

<br>

하지만 난 이미 한 테마 시도 후에<br>
오류 탈탈 털려서 두번이나 테마 전체 리셋 후에 다시 시도 했다 🥴

그래서 이틀 날리고.....<br>
한참 테마 고민 끝에 알고 있었던 choiiis님의 블로그 테마를 다시 적용하기로 했다.

원래는 choiiis님의 github를 fork해서 사용중이었는데<br>
갑자기 사용이 안되는것이더라ㅜㅜ 왜 안되는것이니이.. 멘붕😱


<br>
<br>

---

<br>
<br>


### 테마 적용하기

- <mark>선택한 테마 링크로 이동</mark>

다른 테마 적용 중 실패를 했고,<br>
결국 익숙한 choiiis님의 테마로 적용하기로 했다.


<br>
<br>
<br>


- <mark>다운로드</mark>

원하는 테마에서 'Download ZIP' 를 클릭하여 다운로드 한다.

![zip](../assets/images/posts_img/github-blog/zip.jpg)


<br>
<br>
<br>


- <mark>다운받은 폴더 열기</mark>

다운받은 폴더를 열고 파일을 전체 복사한다.

![copy](../assets/images/posts_img/github-blog/copy.JPG)


<br>
<br>
<br>


- <mark>나의 github.io 폴더에 붙여넣기</mark>

모든파일 '대치하기' 붙여넣기한다.


<br>
<br>
<br>


- <mark>bundle install</mark>

터미널 github.io 폴더 경로에서<br>

bundle install 를 입력한다.


<br>
<br>
<br>


- <mark>bundle exec jekyll serve</mark>

bundle exec jekyll serve<br>

해당 명령어를 입력하고, 

http://127.0.0.1:4000 를 주소창에 입력한다.

![bundle-2](../assets/images/posts_img/github-blog/bundle-2.jpg)

<br>

그러면 원하는 테마를 확인할 수 있다 🙂
![shhhaej](../assets/images/posts_img/github-blog/shhhaej.JPG)


<br>
<br>

---

<br>
<br>


## 블로그 설정

- <mark>_congif.yml 파일 열기</mark>

본인의 github.io 폴더에 있는 _congif.yml 파일을 연다.

![yml](../assets/images/posts_img/github-blog/yml.jpg)

minimal_mistakes_skin : "default" 블로그의 색
locale : "ko-KR" 블로그의 주요 언어 (한국어로 설정)
title : 사이트 탭 이름
subtitle : 화면  title 하단에 있는 소제목
name : 화면 하단의 영역의 이름
description : 설명란
url : "https://XXX.github.io" 본인 블로그의 url
baseurl : 오류 발생 시 연결되는 url
repository : Github Repo url
masthead_title : 화면 title


<br>
<br>
<br>


### 세팅된 설정 변경

- <mark>README.md 파일 변경</mark>

저는 choiiis님 README.md 파일에 안내된 내용대로 설정을 변경한다.

변경 후에 브라우저 리로드하여 확인하면 끝!

혹시 변경내용이 확인 안된다면..?<br>

터미널에 bundle exec jekyll serve 다시 입력하면 끝!


<br>
<br>
<br>


### Post 추가

_posts 폴더에 원하는 내용을 markdown 형식으로 작성한다.

저는 Hello World 를 입력했다 😎

![post](../assets/images/posts_img/github-blog/post.jpg)


<br>
<br>
<br>


### Push 

설정 변경이 모두 끝나면 Push하면 된다.<br>

<br>

git add . <br>
git commit -m "커밋 메시지" <br>
git push

<br>

Push 후에<br>
주소창에 username.github.io 를 입력하여 확인하면<br> 
드디어 완성 😊✌️


<br>
<br>