---
title: "정보처리기사"
excerpt: "licence"

categories:
  - licence
tags:
  - [licence]

permalink: /categories/licence/

toc: true
toc_sticky: true

date: 2023-09-20
last_modified_at: 2023-09-20
---

## 데이터 타입

- MAC주소란 데이터링크 계층(제 2계층)에서 통신을 위해 사용되는 48비트로 된 식별자
- MAC주소는 8비트마다 하이픈(-)이나 콜론(:)으로 구분하여 16진수로 표기
- 상위 24비트는 전기 및 전자 관계 지술자 단체가 제조업체 별로 할당한 제조업체 코드,
  해당 코드로 제조업체를 알 수 있음
- 하위 24비트는 제조업체가 기기 별로 고유한 값을 할당한 코드임
- NIC에 할당되어 있는 MAC주소는 전 세계 하나 밖에 없는 고유한 값임

<br>

### MAC주소 확인 방법

- 윈도우 Key > 검색 > 명령 프롬포트(CMD) 실행 > 'ipconfig /all' 입력 후 엔터
- 이더넷 어댑터 이더넷의 물리적 주소를 확인하면 됨

<br>
<br>
<br>
<br>

## IP주소(Internet Protocol)

- IP는 전송 계층(제 4계층)으로부터 받은 데이터에 IP 헤더를 붙여 패킷으로 만드는 역할을 함
- IP 헤더에는 여러 필드(버전, 헤더길이, 프로토콜 등), 출발지 IP주소, 도착지 IP주소가 들어감
- IP는 IP주소라는 32비트로 된 식별번호를 사용하여 컴퓨터를 식별
- IP주소는 8비트마다 점(.)으로 구분하고 10진수로 표기

<br>

### IP주소 확인 방법

- 윈도우 Key > 검색 > 명령 프롬포트(CMD) 실행 > 'ipconfig /all' 입력 후 엔터
- 이더넷 어댑터 이더넷의 IPv4주소를 확인하면 됨

<br>
<br>
<br>
<br>

## VPN(Virtual Private Network) ?

인터넷망과 같은 공중망을 사설망처럼 이용해 회선 비용을 크게 절감 할 수 있는 기업통신 서비스

<br>

### VPN 사용이유

- IP추적기 차단 효과
- 인터넷 접속 데이터 암호화
- 다양한 위험에 대한 보안 강화
- 웹사이트 액세스 제한 해제
- 고용 와이파이 사용 보안

<br>
<br>
<br>
<br>

<span style="color:gray">참고자료</span>

- https://m.blog.naver.com/dktmrorl/222121510562
- https://webclub.tistory.com/458
