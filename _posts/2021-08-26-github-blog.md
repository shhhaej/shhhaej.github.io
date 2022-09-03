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

![bundle-1](../assets/images/posts_img/github-blog/bundle-2.jpg)


<br>
<br>
<br>


- <mark>GitHub repository 확인</mark>

username.github.io repository 확인 시 Push한 파일이 확인 잘 된다면

브라우저 주소창에 username.github.io 입력하면 

![new-repository-4](../assets/images/posts_img/github-blog/new-repository-4.jpg)

짜잔

⭐Github 블로그 완성⭐

다 확인되었다면 index.html 파일 제거한다.


<br>
<br>

---

<br>
<br>


### Jekyll

- <mark>github.io 폴더에 Jekyll을 설치</mark>

터미널에 gem install jekyll bundler 명령어를 입력한다.


<br>
<br>
<br>


- <mark>Jekyll 생성</mark>

jekyll new ./ <br>

명령어를 입력한다.

이때 뚜둥!

![force](../assets/images/posts_img/github-blog/force.JPG)

<span style="color:red">
Conflict: C:/GitHub/shhhaej.github.io exists and is not empty.<br>
          Ensure C:/GitHub/shhhaej.github.io is empty or else try again with '-  -force' to proceed and overwrite any files.
</span>

오류가 발생되었...🤦

<br>
<br>

당황하지 말고 

jekyll new ./ - -force 를 당당하게 입력한다.

![force-solution](../assets/images/posts_img/github-blog/force-solution.JPG)


<br>
<br>
<br>


- <mark>bundle install</mark>

bundle install 

위 명령어를 입력한다.


<br>
<br>
<br>


- <mark>Jekyll을 로컬서버로 연결하기</mark>

bundle exec jekyll serve  를 입력하면 로컬서버가 띄워진다.

단...

또 두둥ㅠㅠㅠ

![trace](../assets/images/posts_img/github-blog/trace.JPG)
<span style="color:red">    
Jekyll 4.2.2  Please append '- -trace' to be 'serve' command for any additional information or backtrace.
<span>

bundle add webrick 를 입력하면 오류 해결✨

<br>

그럼 다시 

bundle exec jekyll serve 를 입력

![bundle](../assets/images/posts_img/github-blog/bundle-1.JPG)
![bundle](../assets/images/posts_img/github-blog/bundle-2.jpg)

브라우저 주소창에 'http://127.0.0.1:4000' 입력하면..!

<br>

요로코롬 잘 나오면 성공 오예오예😆🙌

![jekyll](../assets/images/posts_img/github-blog/jekyll.JPG)


<br>
<br>
<br>


✔️ 참고로!
혹시 bundle exec jekyll serve 를 입력 시,
해당 내용이 떴을 경우에는
![conflict](../assets/images/posts_img/github-blog/conflict.JPG)

이건 오류는 아니고 중복된 파일로 주의하란 문구란다.

그래도 신경쓰이니까<br>

404.html<br>
about.markdown<br>
index.markdown<br>

파일을 삭제하면 된다.


<br>
<br>