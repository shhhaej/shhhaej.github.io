---
title: "객체와 JVM의 메모리 구조"
excerpt: "자바의 구조"

categories:
  - Java
tags:
  - [Java, JVM, Java structure]

permalink: /java/JVM/java-program-structure/

toc: true
toc_sticky: true
 
date: 2021-10-04
last_modified_at: 2021-10-05

---

## 클래스

클래스는 서로 연관되어 있는 데이터와 메서드의 집합(Grouping)이다. **객체를 만들기 위한 설계도**로서, 코드의 응집도(Cohesion)을 높이고 결합도(Coupling)을 낮출 수 있다.

<br>
<br>

## 생성자

생성자는 객체가 생성될 때 **객체의 초기화를 위해 실행**되는 코드 블록이다. 생성자는 자바 클래스의 멤버가 아니며, 멤버가 아니므로 상속되지 않는다. 따라서 오버라이딩의 대상이 될 수 없고, 메소드가 아니므로 리턴 타입이 없다.(void 조차 허용 안됨)

~~~
public Class Circle { // 클래스
    pulbic Cirche() {...} // 생성자
}
~~~

생성자의 이름은 반드시 클래스 이름과 동일하게 작성해야 한다.

<br>
<br>

~~~
public class Circle {
    public Circle() {...} // 매개변수 없는 생성자
    public Circle(int a, String b) {...}// 2개의 매개변수를 가진 생성자
}
~~~

생성자는 여러개의 작성(오버로딩)을 할 수 있다.

* 오버로딩이란? 같은 동작을 하지만 매개변수를 다르게 하는 경우에 오버로딩을 구현한다.
    - 생성자 이름이 같아야 한다.
    - 매개변수의 개수 or 매개변수의 타입이 달라야 한다.


<br>

<script src="https://gist.github.com/shhhaej/c9b161cbd0597b56ee7090133a0859e0.js"></script>

![moon-result](/assets/images/posts_img/java-program-structure/moon-result.JPG)

<br>
<br>

## 메서드

클래스의 기능(동작)에 해당하는 구현 부분으로 해당 메서드 호출 시 메서드의 블럭 {}에 해당하는 부분을 실행하고, 리턴 타입이 존재한다.

~~~
public class Car { // 클래스
    String carName; // 멤버 변수
    String carColor;
    int velocity;
    int wheelNum;


    public void steedUp() {...} // 멤버 메서드
    public void speedDown() {...}
    public void stop() {...}

};
~~~


<br>
<br>

## 인스턴스

설계도인 클래스 바탕으로 객체를 소프트웨어 실체화 하면 인스턴스(Instance)가 되고, 이 과정을 인스턴스화(instantiation)라고 한다. 인스턴스는 new 연산자를 통해 생성할 수 있으며, 실체화된 인스턴스는 메모리에 할당된다. 따라서 **인스턴스는 메모리에 할당된 객체**이다.

인스턴스를 생성하는 방법은 <span style="color:orange">클래스 변수 = new 클래스(); </span>이다.


<br>
<br>
<br>


## 변수

* 변수란 데이터를 저장할 수 있는 메모리 공간을 의미한다.

<br>

* 원시 타입 변수(기본형 primitive type) : 호출하면 값이 출력 <br>
    정수형 [ int, long, byte, short ] <br>
    실수형 [ float, double ] <br>
    논리형 [ boolean ] <br>
    문자형 [ char ]

    <br>

    <span style="color:orange"> Int i;  원시타입 변수 선언 </span>

<br>

* 레퍼런스 타입 변수(참조형 reference type) : 호출하면 주소번지 출력 <br>
    배열 <br>
    객체 배열(주소번지 두 번 접근) <br>
    List, Map(자료구조 - 주소번지를 두 번 접근) <br>

    <br>

    <span style="color:orange"> String name = null;  레퍼런스 타입 변수 선언 </span>


<br>

<script src="https://gist.github.com/shhhaej/2088caa8ac22219343c1773bd4a02715.js"></script>

![variable-result](/assets/images/posts_img/java-program-structure/variable-result.JPG)

double 타입의 pi 멤버 변수는  non-static이기 때문에 main메소드에서 사용할 수 없어 Static으로 변경해야 사용 가능하다.


<br>
<br>
<br>


## 메모리 구조

<br>

### Static

JAVA 파일은 크게 필드(field), 생성자(constructor), 메소드(method)로 구성된다. **그중 필드에서 선언된 멤버변수(static이라는 키워드를 사용하여 static변수와 static메소드를 만듦) Static영역에 데이터를 저장한다.** Static영역의 데이터는 **프로그램의 시작부터 종료가 될 때까지 메모리에 남아있게 된다.** 다르게 말하면 전역변수가
프로그램이 종료될 때까지 어디서든 사용이 가능한 이유이기도 하다. 따라서 멤버변수를 무분별하게 많이 사용하다 보면 메모리가 부족한 우려가 있어 필요한 변수만 사용할 필요가 있다. 


<br>
<br>


### Stack

메소드 내에서 정의하는 **기본 자료형(int, double, byte, long, boolean..)에 해당되는 지역변수의 데이터 값이 저장되는 공간이 Stack영역이다.** 해당 **메소드가 호출될 때 메모리에 할당되고 종료되면 메모리가 해제된다.**

~~~
public class StackArea {
    public static void main(String[] args) {
        int a = 5;  a = 4;  a = 3;  a = 2;
        System.out.println(a);
        for(int i = 0; i<5; i++) {
        }
        system.out.println(i);  //컴파일 에러
    }
}
~~~

a라는 변수는 main 메소드가 호출될 때 Stack 영역에 할당되고 종료 시 해제된다. a라는 변수의 값이 5, 4, 3, 2 순으로 값을 할당하였고 출력되는 값은 '2'가 출력된다. 이전 데이터는 지워지고 마지막 '2'라는 값만 출력된다. 즉, **Stact영역은 LIFO(Last In First Out)의 구조를 갖고 변수의 새로운 데이터가 할당되면 이전 데이터는 지워진다**는 것을 알 수 있다.

![stack](/assets/images/posts_img/java-program-structure/stack.jpg)

또한 for문 내에 int i 를 정의하였는데 for문이 종료된 다음 i를 출력하지 못하는 이유는 **지역변수이므로 for문의 종료와 함께 Stack영역에서 해제**되었기 때문이다.


<br>
<br>


### Heap 

**참조형(reference Type)의 데이터 타입을 갖는 객체(인스턴스), 배열 등은 Heap영역에서 데이터가 저장된다.** 이때 **변수(객체, 객체변수, 참조변수)는 Stack영역의 공간에서 실제 데이터가 저장된 Heap영역의 참조값(reference value, 메모리에 저장된 주소를 연결해주는 값)을 new 연산자를 통해 리턴 받는다.** 다시 말하면 <span style="color:orange">**실제 데이터를 갖고 있는 Heap영역의 참조 값을 Stack영역의 객체가 갖고 있다.**</span> **이렇게 리턴 받은 참조 값을 갖고 있는 객체를 통해서만 해당 인스턴스를 사용할 수 있다.**

<br>

~~~
public class HeapArea01 {
    public static void main(String[] args) {
        int[] a = null; // int형 배열 선언 및 Stack영역 공간 할당
        System.out.println(a); // 결과 : null

        a = new int[5]; // Heap영역에 5개 연속된 공간 할당 및 변수 a에 참조값 할당
        System.out.println(a); // 결과 : @15ds4751 (참조값)
    }
}
~~~

결국 a변수는 데이터가 저장된 Heap영역의 참조 값을 리턴 받아 갖고 있다는 것이다. 

<br>

~~~
public class HeapArea02 {
    public static void main(String[] args) {
        String str1 = new String("joker");
        String str2 = new String("joker");

        if(str1 == str2) {
            System.out.println("같은 주소값 입니다.");
        } else {
            System.out.println("다른 주소값 입니다.");
        }
    }
}
~~~

문자열을 저장하는 String도 참조형이다. new 연산자를 이용해서 생성하면 데이터는 Heap영역에 저장되고 str1과 str2는 참조 값을 리턴 받는다. 저장된 주소가 다르기 때문에 "==="으로 비교 시 "다른 주소값 입니다."가 출력되는 것이다. 

<br>

~~~
class A{}

public class HeapArea {
    public static void main(String[] args) {
        A a = null; // A타입의 a객체 선언 및 Stack 영역 공간 할당
        System.out.prlintln(a); // 결과 : null

        a = new A(); // Heap 메모리에 공간 할당 및 객체(a)에 참조 값 할당
        System.out.println(a); // 결과 : @15ds4751 (참조값)
    }
}
~~~

결국 객체(인스턴스)가 참조 값을 갖는다는 것이다.

![heap](/assets/images/posts_img/java-program-structure/heap.jpg)

**1. 참조변수 정의** : 참조변수 a는 Stack 메모리에 저장되어 초기 값은 null이다. <br>

**2. 인스턴스 생성** : new 연산자를 통해 인스턴스를 생성하면 Heap 메모리에 A 인스턴스가 <br> 
      생성되고, 인스턴스를 가리키는 주소(reference)를 반환하여 참조변수 a에 저장된다. <br>
      참조변수는 인스턴스 그 자체가 아니라, 단지 인스턴스를 가리키기 위한 변수이다. <br>

**3. 인스턴스 접근** : 2번 과정을 통해 해당 객체의 멤버 변수와 멤버 메서드를 사용할 수 있다.<br>
  - 참조변수.멤버변수
  - 참조변수.멤버메서드()

<br>  

인스턴스를 생성하고 다룰 때 주의해야 할 것은 **가리키고 있는 인스턴스가 없다는것을 나타내는 'Null'주소**이다. 예제와 같이 Null주소로 지정된 경우 컴파일 에러는 발생하지 않지만 런타임 시 **NullPointerException**이 발생한다.

~~~
public class Car {
    ...

    public static void main(String args[]) {
        Car c2;
        c2.carName = "그랜저"; //  컴파일 에러 발생

        c2 = null;
        c2.carName = "그랜저"; // NullPointException 에러 발생
    }
}
~~~


<br>
<br>


추가로 **Heap에 저장된 데이터가 더 이상 사용이 불필요하다면 메모리 관리를 위해 JVM(자바가상머신)에 의해 알아서 해제**된다. 이러한 기능을 **가비지컬렉션(GC, 쓰레기 수집)**이라고 한다.


<br>
<br>
<br>


<span style="color:gray">참고자료</span>

- https://m.blog.naver.com/heartflow89/220954420688
- https://gbsb.tistory.com/155