---
title: "전역변수와 멤버변수는 동일변수?"
excerpt: "자바의 변수"

categories:
  - Java
tags:
  - [Java, Java-variable]

permalink: /java/java-variable/

toc: true
toc_sticky: true
 
date: 2021-10-04
last_modified_at: 2021-10-04

---

## 결과부터 말하자면 아니다 🙄

변수의 종류는 그 선언 위치에 따라 크게 멤버변수와 지역변수로 나뉜다.

찾아 본 많은 자료들이 멤버변수는 클래스 영역에서 선언된 것으로, 멤버변수 = 필드 = 전역변수라고 언급한다. 혹은 전역변수는 Static이 붙은 클래스 변수라고 주장. 그런데 자바의 정석을 보니 또 클래스 변수에 접근제어자로 public을 붙여주면 전역 변수의 성격을 갖게 된다고 한다.

이 부분이 점점 더 헷갈리기 시작했다.<br>
전역변수가 멤버변수고 멤버변수에 클래스변수가 포함되고 public을 붙이면 전역변수의 성격을 띄게 된다? 또, Static을 붙이면 전역변수가 된다? 그럼 클래스변수가 전역변수라는 이야기인가?


<br>
<br>


### Public, Static, 전역변수 각각의 개념

* Public은 같은 프로젝트 안에서 다른 패키지라도 호출이 가능하게 하는 접근 제한자
* Static의 경우 클래스 변수를 만들어 별도의 인스턴스 없이 바로 호출 가능하게 하는 키워드
* 전역변수(global variable)는 함수의 외부에서 선언된 변수. 프로그램의 어디에서나 접근할 수 있으며, 프로그램이 종료되어야만 메모리에서 사라짐

여기서 '프로그램 어디에서나'라는 말이 애매하게 와닿는다. '어디에서나'라는 것은 '프로젝트 안에 모든 곳에서 접근 가능해야한다'는 것인가? 아니면 '실행하는 하나의 큰 프로그램 단위를 의미한다'는 것인가?


<br>
<br>


![global-variable](/assets/images/posts_img/java-program-structure/global-variable.png)

<span style="color:orange">**자바에는 전역변수의 개념이 없다.**</span>

애초에 자바에는 전역변수를 지원하지 않는다는 것이다. 전역변수의 정의는 사실 C언어의 것이었다.


<br>
<br>


### 왜 JAVA 에서는 전역변수를 지원하지 않을까?

디자인적인 결함 때문. 자바는 객체지향 프로그래밍 언어이고 이는 캡슐화를 통해 은닉성을 보장하는게 특징으로 전역변수는 해당 언어의 목적과 상반되는 개념이다.

굳이 전역변수의 역할을 수행하고 싶으면 Static이나 Public으로 충분히 구현 가능하다. <br>
(단, Public 역시 은닉성을 해침으로 무분별한 사용 지양)


<br>
<br>


### 멤버변수 or 클래스 변수

아무래도 지역변수와 구분 지을 개념이 필요하다 보니 전역변수를 많이 사용하는 듯하다. 멤버변수에 비해 비교하기가 쉽다.

그러나 자바에서는 전역변수를 제공하지도 않고 해당 개념을 사용하기엔 개념이 모호하다. 그러니 지역변수와 분리되는 개념으로 사용할 거라면 전역변수라는 말보다 멤버변수 혹은 필드라는 용어를 사용하는 편이 맞다.

혹은 모든 인스턴스가 공통된 변수를 공유하는 개념으로 실제 전역변수와 비슷한 용도로 사용할 거라면 클래스 변수(Static)로 대체하는 것이 나을 듯하다.


<br>
<br>
<br>


<span style="color:gray">참고자료</span>

* http://www.tcpschool.com/c/c_function_variableScope
* https://stackoverflow.com/questions/5581234/why-are-there-no-global-variables-in-java
* https://coderanch.com/t/542041/certification/global-variables-Java
* https://shm-m.github.io/blog/global_variable
