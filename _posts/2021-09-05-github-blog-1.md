---
title: "[GitHub Blog] 고민 끝에 GitHub 블로그 시작"
excerpt: "다시 시작하는 블로그 :)"

categories:
  - GitHub Blog
tags:
  - [GitHub Blog, Git, 깃허브 블로그]

permalink: /github-blog/

toc: true
toc_sticky: true
 
date: 2022-08-31
last_modified_at: 2022-08-31

# sitemap :
#   changefreq : daily
#   priority : 1.0
---

## 다시 시작하는 블로그

만드는 데까지 시간이 많이 소요될까 고민됐지만 그래도 시작이 반이라고 생각하며 바로 시작했다.  
하지만 역시나 쉽지 않았다😂 저의 오류들이 도움이 되기를 바라며💪!

<br>
<br>

### 깃허브 블로그 한번 만들어봐!

- <mark>새로운 Repository를 만든다.</mark>

![new-repository-1](../assets/images/posts_img/github-blog/new-repository-1.JPG)


<br>
<br>
<br>


- <mark>Repository 이름을 설정한다.</mark>

💡 꼭 username.github.io 이런식으로 만들어 준다.

![new-repository-2](../assets/images/posts_img/github-blog/new-repository-2.jpg)


<br>
<br>
<br>


- <mark>clone한다.</mark>

원하는 경로로 이동한 다음 터미널을 열어 클론한다.

git clone https://... 복사한 주소

![new-repository-3](../assets/images/posts_img/github-blog/new-repository-3.jpg)


<br>
<br>
<br>


- <mark>clone한 폴더에 추가로 파일 생성한다.</mark>

index.html 파일 생성 (안에 내용은 상관✖️)

터미널에 해당 명령어 입력한다.

echo "Hello World" > index.html


<br>
<br>
<br>


- <mark>Push</mark>

해당 폴더 모두 Push

터미널에 해당 명령어를 입력한다.

git add <br>
git commit -m "lnitial commit" <br>
git push -u origin main


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