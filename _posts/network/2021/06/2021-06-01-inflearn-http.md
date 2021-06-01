---
layout: single
date: 2021-06-01
title : "[HTTP] 인프런-HTTP 정리"
description: "Inflearn HTTP Lecture 김영한 인프런 강의 정리"
categories:
  - Network
tags:
  - Inflearn
  - Internet
  - HTTP
  - IP
  - TCP
  - UDP
  - PORT
  - DNS
---

## 강의 내용 정리
* 인프런 : 모든 개발자를 위한 HTTP 웹 기본 지식 (김영한)
* [강의 출처](https://www.inflearn.com/course/http-%EC%9B%B9-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC)

## 인터넷 네트워크

### 인터넷 통신

**IP**
* Internet Protocol
* 흔히 말하는 IP는 IP 주소를 지칭

**역할**
* 지정한 IP 주소에 데이터를 전달
* 패킷이라는 통신 단위로 데이터 전달

**서버 패킷 전달**
* 네트워크 망이 복잡하기 때문에 송, 수신시 다른 망 경로(노드)로 전송될 수 있음

---

**IP 프로토콜의 한계**
* 비연결성(통신 대상이 서비스 불능)
  * 패킷을 받을 대상이 없거나 서비스 불능 상태여도 패킷이 전송됨
* 비신뢰성(패킷 유실 또는 전달 순서 문제)
  * 중간에 패킷이 사라지거나 순서대로 오지 않는 경우?
* 프로그램 구분
  * 같은 IP 주소를 사용하는 서버에서 통신하는 앱이 2개 이상이라면?
* 이를 극복하기 위한 프로토콜이 TCP

---

### TCP, UDP

**IP 프로토콜 4계층**
* 애플리케이션 계층 (HTTP, FTP)
* 전송 계층 (TCP, UDP)
* 인터넷 계층 (IP)
* 네트워크 인터페이스 계층

---

**프로토콜 계층**
* 애플리케이션
  * 웹 브라우저
  * 네트워크 게임
  * 소켓 라이브러리
* OS
  * TCP, UDP
  * IP
* 네트워크 인터페이스
  * LAN 드라이버, 장비
* Ethernet frame (맥 주소 등 정보 포함)

---

**패킷 정보**
* 패킷은 패키지 + 버킷
* IP 패킷
  * 출발지 IP, 목적지 IP
  * 기타
* TCP/IP 패킷
  * 출발지 PORT, 목적지 PORT
  * 전송 제어, 순서, 검증 정보
  * 기타

---

**TCP 특징**
* 전송 제어 프로토콜 (Transmission Control Protocol)
* 연결 지향
  * TCP 3 way handshake (가상 연결)
    * 논리적인 연결 (일종의 약속일 뿐)
  * 연결과정
    1. SYN (클라이언트에서 접속 요청)
    2. SYN + ACK (서버에서 접속 요청 + 요청 수락) 
    3. ACK (클라이언트에서 요청 수락)
       * 최근에는 마지막 ACK 전송할 때 데이터도 함께 전송
* 데이터 전달 보증
  * 데이터를 올바르게 받은 경우 응답 전송
* 순서 보장
  * 기본적으로 패킷 순서가 올바르지 않으면 재전송 요청 처리
    * 하지만 이는 네트워크 환경에 따라 다를 수 있음
* 신뢰 가능한 프로토콜
* 현대 네트워크에서는 대부분 TCP 프로토콜이 사용됨

---

**UDP 특징**
* 사용자 데이터그램 프로토콜 (User Datagram Protocol)
* TCP와 다르게 아래 기능들이 없기 때문에 흔히 백지에 비유
  * 연결지향 (TCP 3 way handshake)
  * 데이터 전달 보증
  * 순서 보장
* 단순하기 때문에 빠름
* IP 프로토콜과 거의 유사함 (PORT, 체크섬 정도만 추가됨)
  * 따라서 애플리케이션에서 추가 작업이 필요함

---

### PORT
통신시 사용되는 엔드포인트 (운영 체제 통신의 종단점)
* 하나의 클라이언트에서 여러 애플리케이션을 사용해 여러 곳을 동시에 연결해야 한다면?
* 같은 IP 주소 내에서 프로세스를 구분하기 위해 사용됨

**PORT 할당**
* 0 ~ 65535는 할당 가능
* 0 ~ 1023는 잘 알려진 포트, 가급적 사용하지 않는 것이 좋음
  * FTP (20, 21)
  * TELNET (23)
  * HTTP (80)
  * HTTPS (443)

---

### DNS
IP 주소를 찾아주는 시스템(Domain Name System)
* IP 주소는 숫자기 때문에 외우기 어려움
* IP 주소는 변경될 가능성이 농후

---

## URI, 웹 브라우저 요청 흐름

### URI
Uniform Resource Identifier
* Uniform
  * 리소스를 식별하는 통일된 방식
* Resource
  * 자원, URI로 식별할 수 있는 모든 것 (제한 없음)
* Identifier
  * 다른 항목과 구분하는데 필요한 정보

---

**URI, URL, URN 차이**
* URI
  * locator, name으로 (또는 둘다) 추가 분류될 수 있음
  * URI는 URL, URN을 포함
* URL
  * Uniform Resource Locator
  * 리소스 위치를 의미
  * 문법
    * `scheme://[userinfo@]host[:port][/path][?query][#fragment]`
    * `https://www.google.com:443/search?q=hello&hl=ko`
      * scheme(protocol) : `https`
        * (사전에 약속된) 자원에 접근하는 방식
      * userinfo
        * URL에 사용자 정보를 포함해 인증할 때 사용 (거의 사용되지 않음)
      * host : `www.google.com`
      * port : `443`
        * http는 80, https 443 포트를 사용함 (이와 같이 사용하면 생략 가능)
      * path : `/search`
        * 리소스 경로
        * 계층적 구조
      * query parameter : `q=hello&hl=ko`
        * `?`으로 시작하고 `&`로 추가 가능
        * 쿼리 파라미터, 쿼리 스트링 등으로 지칭
        * `key=value` 형태
      * fragment
        * HTML 내부 북마크 등에서 사용
        * 서버에 전송하는 정보가 아님
* URN
  * Uniform Resource Name
  * 리소스명을 의미
  * URN만으로 실제 리소스를 찾는 방법은 보편화 되어 있지 않음

---

### 웹 브라우저 요청 흐름
1. DNS를 통해 IP 주소, 포트 정보를 획득
2. 획득한 정보를 사용하여 HTTP 요청 메시지 생성
   ~~~
   요청 데이터 포맷 예시
   GET /serach?q=hello&hl=ko HTTP/1.1
   Host: www.google.com
   ~~~
3. 웹 브라우저가 소켓 라이브러리를 통해 전달
   * TCP/IP 연결
   * 데이터 전달
   * HTTP 메시지 포함하여 TCP/IP 패킷 생성
4. 서버로 패킷 전송
5. 서버는 수신한 패킷 처리
6. HTTP 응답 메시지 생성
   ~~~
   응답 데이터 포맷 예시
   HTTP/1.1 200 OK
   Content-Type: text/html;charset=UTF-8
   Content-Length: 3423
   
   <html>
       <body>...</body>
   </html>
   ~~~
7. 서버도 마찬가지로 패킷 처리 후 반환
8. 웹 브라우저는 수신한 데이터를 화면에 렌더링

---

## HTTP
Hyper Text Transfer Protocol

### HTTP 기본
* 초창기 하이퍼 텍스트 송수신을 위해 만들어졌으나 현재는 대부분에 통신을 HTTP로 함
  * HTML, TEXT
  * 이미지, 음성, 영상, 파일 등
  * JSON, XML (API)
  * 그 외 거의 모든 형태의 데이터 전송 가능
  * 서버 간 데이터 통신

---

**버전별 특징**
* 0.9 (1991)
  * GET 메서드만 지원, HTTP 헤더 없음
* 1.0 (1996)
  * HTTP 메서드 및 헤더 추가
* 1.1 (1997)
  * 현재 가장 많이 사용되는 버전
  * RFC2068(1997) > RFC2616(1999) > RFC7230 ~ 7235(2014)
* 2 (2015)
  * SPDY 기반
  * 성능 개선
  * HTTP 헤더 데이터 압축
  * 서버 푸시 기능
  * 요청을 HTTP 파이프라인으로 처리
  * 하나의 TCP 연결로 여러 요청 처리 가능
* 3 (개발 진행중)
  * TCP 대신 UDP를 사용하여 성능 개선
  * QUIC 기반

---

**기반 프로토콜**
* HTTP 1.1, 2 버전은 TCP 기반
* HTTP 3 버전은 UDP 기반

---

#### 특징
* 클라이언트-서버 구조
  * 요청-응답 구조
  * 클라이언트가 서버에 요청을 보내고 서버의 응답을 대기
  * 서버가 요청에 대한 결과를 만들어 응답
* Stateless (무상태성)
  * 서버가 클라이언트의 상태 정보를 보존하지 않음 (반대는 Stateful)
    * 간혹 모든 것을 무상태로 설계할 수 없는 경우도 존재
    * 로그인 등은 상태 유지가 필요
      * 일반적으로 쿠키, 세션 등을 사용해 상태 유지
    * 상태 유지는 가급적 최소화
  * 장점
    * 서버의 확장성이 높음 (스케일 아웃 환경)
  * 단점 
    * 클라이언트의 추가 데이터 전송 필요
* Connectionless (비연결성)
  * 클라이언트와 계속 연결된 상태라면 서버의 리소스가 많이 소모됨
  * HTTP는 기본적으로 비연결 모델
  * 일반적으로 초 단위 이하의 빠른 속도로 응답
  * 장점
    * 서버 리소스를 효율적으로 사용 가능
  * 단점
    * 매 통신마다 새로운 TCP(3 way handshake) 연결이 필요해 비효율적
    * 수많은 리소스(HTML, JS, CSS 등) 다운로드가 필요하기 때문
      * HTTP Persistent Connections(지속 연결)로 해당 문제 해결
      * HTTP 2, 3 버전에서 더 많은 최적화

---

#### HTTP 메시지
* HTTP 메시지 구조
  ~~~
  start-line   : 시작 라인
  header       : 헤더
  empty line   : 공백 라인 (CRLF)
  message body : 메시지 바디
  ~~~
* 공식 스펙
  ~~~
  MTTP-message = start-line
                 * ( header-field CRLF )
                 CRLF
                 [ message-body ]
  ~~~
* 요청 메시지
  * 요청 메시지도 body 본문을 가질 수 있음
* 응답 메시지
  * 요청 메시지랑 시작 라인이 다름
* 단순, 확장 가능
  * HTTP 스펙과 메시지는 단순함
  * 크게 성공하는 표준 기술은 단순하면서도 확장 가능함

---

**HTTP 요청 메시지 시작 라인**
* start-line = (request-line / status-line)
* request-line = `method SP(공백) request-target SP HTTP-version CRLF(엔터)`
  ~~~
  GET /serach?q=hello&hl=ko HTTP/1.1
  ~~~
  * HTTP 메서드 (GET: 조회)
    * 서버가 수행할 동작 지정
    * GET, POST, PUT, DELETE, 기타
  * 요청 대상 (/serach?q=hello&hl=ko)
    * absolute-path[?query] 절대경로[?쿼리]
    * 절대 경로 = `/`로 시작하는 경로
    * `http://..?x=y`와 같이 다른 유형의 경로 지정 방법도 존재
  * HTTP Version

---

**HTTP 응답 메시지 시작 라인**
* start-line = (request-line / status-line)
* status-line = `HTTP-version SP status-code SP reason-phrase CRLF`
  ~~~
  HTTP/1.1 200 OK
  ~~~
  * HTTP 버전
  * HTTP 상태 코드 (요청, 성공 등과 같은 정보 표현)
    * 200 (성공)
    * 400 (클라이언트 요청 오류)
    * 500 (서버 내부 오류)
  * reason-phrase (짧은 상태 코드 설명)

---

**HTTP 헤더**
* header-field = `field-name : OWS field-value OWS` (OWS: 띄어쓰기 허용)
* field-name은 대소문자 구문 없음
  * 값은 대소문자 구분
* HTTP 전송에 필요한 모든 부가 정보
  * 메시지 바디 내용 및 크기
  * 압축
  * 인증
  * 요청 클라이언트(브라우저) 정보
  * 서버 앱 정보
  * 캐시 관리 정보
  * 기타
* 표준 헤더가 너무 많음
* 필요에 따라 임의의 헤더 추가 가능

---

**HTTP 메시지 바디**

실제 전송 데이터
  * HTML, 이미지, 영상, 기타 JSON 데이터 등 byte로 표현 가능한 모든 데이터

---

### HTTP 메서드
* HTTP API 설계
  * 리소스의 의미?
    * 행위 자체가 리소스가 아님
  * 회원 조회, 등록 기능에서 회원이라는 개념 자체가 리소스
    * 회원이라는 리소스만 식별 > 회원 리소스를 URI에 매핑
  * 리소스와 행위를 분리
    * 행위를 HTTP 메서드로 표현
* 종류
  * GET
    * 리소스 조회
  * POST
    * 리소스 생성 및 등록, 요청 데이터 처리
  * PUT
    * 리소스를 대체, 없다면 생성
    * 디렉토리에 파일을 넣는 것과 비슷
  * PATCH
    * 리소스의 부분을 변경 (회원 정보 변경 등)
  * DELETE
    * 리소스 삭제
  * HEAD
    * GET과 동일하지만 메시지 부분 제외하고 상태와 헤더만 반환
  * OPTIONS
    * 대상 리소스에 대한 통신 가능한 옵선(메서드)을 설명 (주로 CORS에서 사용됨)
  * CONNECT
    * 대상 리소스로 식별되는 서버에 대한 터널을 설정함
  * TRACE
    * 대상 리소스에 대한 경로를 따라 메시지 루프백 테스트 수행
* 최근에는 Resource를 Representation으로 표현하여 사용

---

#### GET
* 리소스 조회
* 쿼리 스트링을 통해 데이터 전달
* 스펙상 메시지 바디를 이용해 데이터 전달 가능
  * 하지만 지원하지 않는 곳이 많아 실무에서는 권장되지 않음
* 요청
  ~~~
  GET /members/100 HTTP/1.1
  Host: localhost:8080
  ~~~
* 응답
  ~~~
  HTTP/1.1 200 OK
  Content-Type: application/json
  Content-Length: 34
  
  {
      "username": "young",
      "age": 20
  }
  ~~~

---

#### POST
* 요청 데이터 처리
* POST 요청 스펙
  * 대상 리소스가 요청에 포함된 표현을 리소스의 고유한 의미 체계에 따라 처리하도록 요청
* 메시지 바디를 통해 서버로 요청 데이터 전달
  * 서버는 메시지 바디를 통해 들어온 데이터를 처리하는 모든 기능 수행
* 주로 전달된 데이터로 신규 리소스 등록, 프로세스 처리에 사용됨
  * HTML 양식에 입력된 필드와 같은 데이터 블록을 데이터 처리 프로세스에 제공
    * HTML FORM에 입력된 정보로 회원 가입, 주문 등 처리
  * 게시판, 뉴스 그룹, 메일링 리스트, 블로그 등 유사한 기사 그룹에 메시지 게시
    * 게시판, 댓글 작성
  * 서버가 식별하지 않은 새 리소스 생성
    * 신규 주문 생성
  * 기존 리소스에 데이터 추가
    * 문서에 내용 추가
* 리소스 URI에 POST 요청이 오면 데이터를 어떻게 처리할 지 리소스마다 개별적인 설정 필요
* 정리
  * 새 리소스 생성 및 등록
  * 요청 데이터 처리
    * 단순한 데이터 변경이 아니고 프로세스를 처리해야 하는 경우
      * `주문 > 결제 완료 > 배달 시작 > 배달 완료`처럼 프로세스의 상태가 변경되는 경우
      * 이때 새로운 리소스가 생성되지 않을 수 있음
    * `POST /orders/{orderId}/start-delivery` (컨트롤 URI)
  * 다른 메서드로 처리하기 어렵거나 애매한 경우
    * 조회 시 조회 데이터(JSON 등)로 인해서 GET 메서드를 사용하기 어려운 경우
* 요청
  ~~~
  POST /members HTTP/1.1
  Content-Type: application/json
  
  {
      "username": "hello",
      "age": 20
  }
  ~~~
* 응답
  ~~~
  HTTP/1.1 201 Created
  Content-Type: application/json
  Content-Length: 34
  Location: /members/100
  
  {
      "username": "young",
      "age": 20
  }
  ~~~

---

#### PUT
* 해당 리소스를 대체
  * 리소스가 없으면 생성, 있으면 대체 (덮어 쓰기)
* 클라이언트가 리소스를 식별 (POST와 차이점)
  * 클라이언트가 리소스 위치(경로)를 알고 URI 지정
  * 만약 특정 필드가 없는 경우 해당 필드 삭제 처리

---

#### PATCH
* 해당 리소스의 부분 변경
* 만약 특정 필드가 없는 경우에도 해당 필드 보존
* 간혹 PATCH를 사용하지 못하는 경우 POST를 대신 사용

---

#### DELETE
* 해당 리소스 제거

---

**HTTP 메서드 속성**
* 안전 (Safe Methods)
  * GET, HEAD 등은 호출해도 리소스를 변경하지 않음
  * 그 외 다른 부분은 안전하지 않음 (해당 리소스만)
* 멱등 (Idempotent Methods)
  * 외부의 개입이 없다면 몇번을 호출하든지 결과가 동일함
    * GET
    * PUT
    * DELETE
  * POST는 멱등이 아님
  * 멱등의 활용
    * 자동 복구 메커니즘
    * 서버가 TIMEOUT 등 정상 응답을 주지 못한 경우, 같은 요청 재시도 가능 여부 판단 시 활용
* 캐시 가능 (Cacheable Methods)
  * GET, HEAD, POST, PATCH 캐시 가능 (실제로는 GET, HEAD 정도만 캐싱)
    * GET, HEAD 등은 URI만으로만 캐싱 키를 설정
    * POST, PATCH는 본문 내용까지 캐싱 키로 설정해야 하기 때문에 구현이 어려움

---

**HTTP 메서드 활용**
* 쿼리 스트링을 통한 데이터 전송
  * GET
  * 정렬 필터 (검색어)
* 메시지 바디를 통한 데이터 전송
  * POST, PUT, PATCH
  * 회원 가입, 상품 주문 등 리소스 등록과 변경

---

**클라이언트에서 서버로 데이터 전송**
* 정적 데이터 조회
  * 이미지, 정적 텍스트 문서 등
  * 조회는 GET 사용
  * 일반적으로 쿼리 스트링 없이 리소스 경로만으로 단순 조회 가능
* 동적 데이터 조회
  * 검색, 게시판 목록 내 정렬 필터 (검색어)
  * 필터링, 정렬 조건 등에 주로 사용
  * 조회는 GET 사용 (쿼리 스트링)
    * 실무에서 GET 요청 시 메시지 바디 사용을 권장하지 않음
* HTML Form을 통한 데이터 전송
  * 회원 가입, 상품 주문 등 데이터 변경
  * `Content-Type: application/x-www-form-urlencoded`
    * Form 내용을 메시지 바디에 담아 전송 (key, value 형태)
    * 전송 데이터를 url 인코딩 처리
  * `Content-Type: multipart/form-data;`
    * 파일 업로드 같은 바이너티 데이터 전송시 사용됨
    * 다른 종류의 여러 파일, Form 내용도 함께 전송 가능
  * HTML Form 전송은 GET, POST만 지원
* HTTP API를 통한 데이터 전송
  * 회원 가입, 상품 주문 등 데이터 변경
  * 서버 <-> 서버
  * 앱
    * 아이폰, 안드로이드
  * 웹 클라이언트 (Ajax)
    * HTML에서 Form 형태 전송 대신 JS AJAX 통신 사용
  * POST, PUT, PATCH
    * 메시지 바디를 통해 데이터 전송
  * GET
    * 쿼리 스트링으로 데이터 전달
  * `Content-Type: application/json;`을 주로 사용 (표준에 가까움)
    * TEXT, XML, JSON 등을 사용할 수 있음

---

### HTTP 설계 예시
* HTTP API - 컬렉션
  * POST 등록 (회원 관리 API 제공)
* HTTP API - 스토어
  * PUT 등록 (정적 컨텐츠, 원격 파일 등 관리)
* HTML Form 사용
  * GET, POST만 지원 (웹 페이지 회원 관리)

---

**회원 관리 시스템 (POST 기반)**
* 회원 목록 `/members` -> GET
* 회원 등록 `/members` -> POST
* 회원 조회 `/members/{id}` -> GET
* 회원 수정 `/members/{id}` -> PATCH, PUT, POST
* 회원 삭제 `/members/{id}` -> DELETE
* 특징
  * 클라이언트는 등록될 리소스의 URI를 모름
    * 회원 등록 `/members` -> POST
    * `POST /members`
  * 서버가 새로 등록된 리소스 URI를 생성해 반환
    ~~~
    HTTP/1.1 201 Created
    
    Location: /members/100
    ~~~  
  * 컬렉션(Collection)
    * 서버가 관리하는 리소스 디렉토리
    * 서버가 리소스의 URI를 생성하고 관리
    * 여기서 컬렉션은 /members

---

**파일 관리 시스템 (PUT 기반)**
* 파일 목록 `/files` -> GET
* 파일 조회 `/files/{filename}` -> GET
* 파일 등록 `/files/{filename}` -> PUT
* 파일 삭제 `/files/{filename}` -> DELETE
* 파일 대량 등록 `/files` -> POST
* 특징
  * 클라이언트가 리소스 URI를 알고 있어야 함
    * 파일 등록 `/files/{filename}` -> PUT 
    * `PUT /files/star.jpg`
  * 클라이언트가 직접 리소스의 URI를 지정
  * 스토어(Store)
    * 클라이언트가 관리하는 리소스 저장소
    * 클라이언트가 리소스의 URI를 알고 관리
    * 여기서 스토어는 `/files`

---

**회원 관리 시스템(HTML Form 사용)**
* 회원 목록 `/members` -> GET
* 회원 등록 폼 `/members/new` -> GET
* 회원 등록 `/members/new`, `/members` -> POST
  * POST 요청과 GET 요청의 URI를 맞추는 것도 고려
    * 예를 들어 유효성 검사 중 문제가 발생한 경우  
      POST 요청의 최종 데이터를 담아 회원 등록 Form으로 다시 보내야 할 때  
      경로가 다르면 리프레시 등으로 원래 Form으로 돌아가기 어려움
* 회원 조회 `/members/{id}` -> GET
* 회원 수정 폼 `/members/{id}/edit` -> GET
* 회원 수정 `/members/{id}/edit`, `/members/{id}` -> POST
* 회원 삭제 `/members/{id}/delete` -> POST
* 특징
  * 순수 HTML Form은 GET, POST만 지원 (제한적)
  * 컨트롤 URI (동사 사용)
    * GET, POST만 사용할 수 밖에 없는 제약 극복을 위해 사용
    * POST 요청과 `/new`, `/edit`, `/delete` 등의 컨트롤 URI를 함께 사용하여 처리
    * 추가적으로 HTTP 메서드로 해결하기 애매한 경우 사용
  * AJAX 등 기술을 통해 해결

---

**참고하면 좋은 URI 설계 개념**
* 문서 (document)
  * 단일 개념(파일 하나, 객체 인스턴스, 데이터베이스 row)
  * 예) `/members/100`, `/files/star.jpg`
* 컬렉션 (collection)
  * 서버가 관리하는 리소스 디렉터리
  * 서버가 리소스의 URI를 생성하고 관리
  * 예) `/members`
* 스토어 (store)
  * 클라이언트가 관리하는 자원 저장소
  * 클라이언트가 리소스의 URI를 알고 관리
  * 예) `/files`
* 컨트롤러 (controller), 컨트롤 URI
  * 문서, 컬렉션, 스토어로 해결하기 어려운 추가 프로세스 실행
  * 동사를 직접 사용
  * 예) `/members/{id}/delete`
* [참고 문서](https://restfulapi.net/resource-naming/)

---

### HTTP 상태코드
클라이언트가 보낸 요청의 처리 상태를 응답(반환) 시 표현하는 기능
* 클라이언트가 인식할 수 없는 상태 코드를 서버가 반환하는 경우
* 상위 상태코드로 해석하여 처리
* 따라서 새로운 상태코드라도 클라이언트를 변경하지 않아도 됨
* 예시
  * 299 ??? -> 2xx (Successful)
  * 451 ??? -> 4xx (Client Error)
  * 599 ??? -> 5xx (Server Error)

---

**1xx**

요청이 수신되어 처리중 (Informational)
* 거의 사용되지 않음

---

**2xx**

요청 정상 처리 (Successful)
* 200 (OK)
  * 요청 처리 완료
* 201 (Created)
  * 요청 성공으로 새로운 리소스 생성 완료
* 202 (Accepted)
  * 요청 접수는 완료, 처리는 완료되지 않음 (배치 처리 등)
* 204 (No Content)
  * 요청 처리 완료, 응답 페이로드 본문에 반환할 데이터가 없음 (문서 저장 기능 등)

---

**3xx**

요청을 완료하려면 유저 에이전트의 추가 조치 필요 (Redirection)

* 300 (Multiple Choices)
  * 거의 사용되지 않음
* 301 (Moved Permanently)
  * 영구적인 리다이렉션
  * 리다이렉트 시 요청 메서드가 GET으로 변경됨, 본문이 제거될 수 있음
* 302 (Found)
  * 일시적인 리다이렉션
  * 리다이렉트 시 요청 메서드가 GET으로 변경됨, 본문이 제거될 수 있음
* 303 (See Other)
  * 일시적인 리다이렉션
  * 302와 기능은 같음
  * 리다이렉트 시 요청 메서드가 GET으로 (반드시) 변경됨
* 304 (Not Modified)
  * 캐싱 목적으로 사용
  * 리소스가 변경되지 않음을 명시, 클라이언트는 로컬 캐시 데이터를 재사용
  * 응답 시 메시지 바디를 포함하면 안됨
  * 조건부 GET, HEAD 요청 시 사용
* 307 (Temporary Redirect)
  * 일시적인 리다이렉션
  * 302와 기능은 같음
  * 리다이렉트 시 요청 메서드와 본문 유지 (요청 메서드를 절대 변경하면 안됨)
* 308 (Permanent Redirect)
  * 영구적인 리다이렉션
  * 301과 기능은 같음
  * 리다이렉트 시 요청 메서드와 본문 유지
    * 처음 요청이 POST면 리다이렉트 시에도 POST 유지
  * 일반적으로 URL이 변경되면 처리할 데이터 포맷도 바뀌는 경우가 대부분  
    따라서 308보다는 301로 처리하는 경우가 많음

**URL 리다이렉션 또는 리다이렉트**
* URL 넘겨주기
* 웹 브라우저는 3xx 응답을 받을 때 `Location` 헤더가 존재하면 Location 위치로 자동 이동
* 종류
  * 영구적인 리다이렉션 (특정 리소스의 URI가 영구적으로 이동됨)
    * 원래의 URL이 사용되지 않음을 표현, 검색 엔진 등에서도 변경 인지
    * 예) `/members` -> `/users`
    * 예) `/events` -> `/new-event`
    * 301, 308 등
  * 일시적인 리다이렉션 (일시적으로 변경)
    * 일시적인 변경이기 때문에 검색 엔진 등에서 URL을 변경하면 안됨
    * 주문 완료 후 주문 내역 화면으로 이동
    * PRG : Post/Redirect/Get
    * 302, 303, 307 등
  * 특수한 리다이렉션
    * 결과 대신 캐시 사용

**PRG (Post/Redirect/Get)**
* POST 주문 후에 새로고침으로 인한 중복 주문 방지
* 주문 후 결과 화면을 GET 메서드로 리다이렉트
* 이후부터 새로고침을 해도 결과 화면을 GET으로 조회
* 중복 주문 대신 결과 화면만 GET으로 다시 요청
* 예시
  * POST 요청에 대한 응답으로 302 코드와 URL을 반환하여 자동 리다이렉트
  * 이후부터 결과 화면에서 새로고침을 하더라도 GET 요청을 하게 됨

**정리**
* 일시적인 리다이렉트 시 302, 303, 307 중 어떤 것을 사용해야 하는가?
  * 302 (Found)
    * GET으로 변할 수 있음 (가능성)
  * 303 (See Other)
    * GET으로 변경 (확실)
  * 307 (Temporary Redirect)
    * 메서드가 변경되면 안됨
* History
  * 처음 302 설계 의도는 HTTP 메서드를 유지하는 것
  * 하지만 웹 브라우저들이 대부분 GET 메서드로 변경 (일부 예외 존재)
  * 302 스펙이 모호해져 303, 307이 등장 (301을 위해 308 등장)
* 실무
  * 303, 307 등을 권장하지만 이미 302를 대부분 기본값으로 사용하는 상황
  * 자동 리다이렉션 시 GET 메서드로 변경해도 괜찮다면 그냥 302 사용 가능

---

**4xx**

클라이언트 오류, 잘못된 문법 등으로 서버의 요청 처리 실패 (Client Error)
> * 오류의 원인이 클라이언트에게 있는 경우
> * 이미 잘못된 요청이기 때문에 똑같은 재시도 또한 실패함

* 400 (Bad Request)
  * 클라이언트의 잘못된 요청으로 처리할 수 없음
  * 클라이언트는 요청 검토 후 다시 요청해야 함 (요청 구문, 메시지 등 오류)
  * 예) 잘못된 요청 파라미터를 전송하는 경우, API 스펙이 맞지 않는 경우
* 401 (Unauthorized)
  * 해당 리소스 요청에 대한 인증이 필요함
  * 해당 상태코드 반환 시 `WWW-Authenticate` 헤더를 통해 인증 방법을 함께 반환
  * 이름(인가되지 않음)과 다르게 인증의 문제
  * 참고
    * 인증(Authentication)
      * 본인이 누구인지 확인 (로그인)
    * 인가(Authorization)
      * 권한부여 (어드민 권한처럼 특정 리소스에 접근할 수 있는 권한, 인증 후 절차)
* 403 (Forbidden)
  * 서버의 승인 거부
  * 일반적으로 인가 권한이 부족한 경우에 사용
  * 예) 일반 사용자가 어드민 권한이 필요한 리소스에 접근하는 경우
* 404 (Not Found)
  * 요청 리소스를 찾을 수 없음
  * 클라이언트가 권한이 부족한 리소스에 접근 시도 시 해당 리소스를 숨기고 싶은 경우

---

**5xx**

서버 오류, 서버의 정상 요청 처리 실패 (Server Error)
> * 오류의 원인이 서버에게 있는 경우
> * 서버 처리 문제기 때문에 똑같은 재시도 시 결과가 달라질 수 있음

* 500 (Internal Server Error)
  * 서버 내부 문제로 발생한 오류
  * 그 외 서버에서 애매한 오류가 발생한 경우
* 503 (Service Unavailable)
  * 서버가 일시적인 과부하 또는 예정된 작업으로 잠시 요청을 처리할 수 없음
  * `Retry-After` 헤더 필드로 얼마뒤에 복구되는지 보낼 수도 있음

---

### HTTP 헤더

**헤더 필드**
* `field-name : OWS field-value OWS` (OWS : 띄어쓰기 허용)
* field-name은 대소문자 구문 없음

**용도**
* HTTP 전송에 필요한 모든 부가정보
  * 예시
    * 메시지 바디의 내용, 크기, 압축, 인증
    * 요청 클라이언트
    * 서버 정보
* 표준 헤더가 너무 많음
* 임의의 헤더 추가 가능

---

#### 헤더 분류
* General 헤더
  * 메시지 전체에 적용되는 정보 (요청, 응답과 무관한 헤더)
  * 예) Connection: close
* Request 헤더
  * 요청 정보
  * 예) User-Agent: Mozilla/5.0 (Macintosh; ..)
* Response 헤더
  * 응답 정보
  * 예) Server: Apache
* Entity 헤더
  * 엔티티 바디 정보
  * 예) Content-Type: text/html, Content-Length: 3423

---

#### 메시지 바디

**개정 전**
* 메시지 본문은 엔티티 본문을 전달하는데 사용
* 엔티티는 요청이나 응답 시 전달할 실제 데이터
* 엔티티 헤더
  * 엔티티 본문의 데이터를 해석할 수 있는 정보 제공
  * 데이터 유형, 길이, 압축 정보 등

**개정**
* RFC2616 폐기 -> RFC7230~7235
* 엔티티(Entity) -> 표현(Representation)
* Representation (표현 = 표현 메타데이터 + 표현 데이터)
  * Representation Meta data + Representation Data

**현재**
* 메시지 본문을 통해 표현 데이터 전달
  * 메시지 본문은 페이로드(payload)
* 표현은 요청, 응답 시 전달할 실제 데이터
* 표현 헤더
  * 표현의 데이터를 해석할 수 있는 정보 제공
  * 데이터 유형, 길이, 압축 정보 등
  * 표현 메타데이터와 페이로드 메시지를 구분

---

#### 표현
표현 헤더는 전송, 응답 둘다 사용
* Content-Type
  * 표현 데이터의 형식 (미디어 타입, 문자 인코딩)
  * 예시
    * text/html; charset=utf-8
    * application/json (기본이 UTF-8)
    * image/png
* Content-Encoding
  * 표현 데이터의 압축 방식
    * 데이터를 보내는 측에서 압축 후 인코딩 헤더 추가
    * 데이터를 받는 쪽에서 인코딩 헤더 정보로 압축 해제
  * 예시
    * gzip
    * deflate
    * identity (압축 안함)
* Content-Language
  * 표현 데이터의 자연 언어
  * 예시
    * ko
    * en
    * en-US
* Content-Length
  * 표현 데이터의 길이 (바이트 단위)
  * 명확하게 페이로드 헤더
  * Transfer-Encoding(전송 코딩) 사용 시 Content-Length 사용하면 안됨
    * Transfer-Encoding 안에 정보가 이미 있음

---

#### 협상

클라이언트가 선호하는 표현 요청 (요청 시에만 사용)
* Accept
  * 클라이언트가 선호하는 미디어 타입 전달
* Accept-Charset
  * 클라이언트가 선호하는 문자 인코딩
* Accept-Encoding
  * 클라이언트가 선호하는 압축 인코딩
* Accept-Language
  * 클라이언트가 선호하는 자연 언어

---

**협상 우선순위 1**
* Quality Values(q) 사용
* 0~1, 클수록 높은 우선순위 (생략하면 1)
* `Accept-Language: ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7`
  1. ko-KR;q=1 (q생략)
  2. ko;q=0.9
  3. en-US;q=0.8
  4. en:q=0.7

**협상 우선순위 2**
* 구체적인 것이 우선 순위가 높음
* `Accept: text/*, text/plain, text/plain;format=flowed, */*`
  1. text/plain;format=flowed
  2. text/plain
  3. text/*
  4. */*

**협상 우선순위 3**
* 구체적인 것을 기준으로 미디어 타입을 맞춤
* `Accept: text/*;q=0.3, text/html;q=0.7, text/html;level=1, text/html;level=2;q=0.4, */*;q=0.5`
* | Media Type        | Quality |
  |-------------------|---------|
  | text/html;level=1 | 1       |
  | text/html         | 0.7     |
  | text/plain        | 0.3     |
  | image/jpeg        | 0.5     |
  | text/html;level=2 | 0.4     |
  | text/html;level=3 | 0.7     |

---

**전송 방식**
* Transfer-Encoding
* Range, Content-Range

**상세**
* 단순 전송
  * 일반 전송
    ~~~
    HTTP/1.1 200 OK
    Content-Type: text/html;charset=UTF-8
    Content-Length: 3423
    
    <html>
        <body>...</body>
    </html>
    ~~~
* 압축 전송
  * Content-Encoding 사용
    ~~~
    HTTP/1.1 200 OK
    Content-Type: text/html;charset=UTF-8
    Content-Encoding: gzip
    Content-Length: 521

    lkj123kljoiasudlkjaweioluywlnfdo912u34ljko98udjkl
    ~~~
* 분할 전송
  * Transfer-Encoding 사용
    ~~~
    HTTP/1.1 200 OK
    Content-Type: text/plain
    Transfer-Encoding: chunked

    5
    Hello
    5
    World
    0
    \r\n
    ~~~
  * Content-Length 삽입하지 말 것
    * 분할 시 예상하기 어려움
    * 분할된 파트마다 길이를 별도로 표현
* 범위 전송
  * Range 사용 (특정 범위를 지정해서 전송 요청)
    ~~~
    GET /event
    Range: bytes=1001-2000
    ~~~
  * Content-Range 사용 (요청 범위 반환)
    ~~~
    HTTP/1.1 200 OK
    Content-Type: text/plain
    Content-Range: bytes 1001-2000 / 2000
    
    qweqwe1l2iu3019u2oehj1987askjh3q98y
    ~~~

---

#### 일반 정보
* From
  * 유저 에이전트의 이메일 정보
  * 일반적으로 자주 사용되지 않음
  * 검색 엔진 등에서 주로 사용
  * 요청 시 사용
* Referer
  * 이전 웹 페이지 주소
  * 유입 경로 분석 가능
  * referrer 오타
  * 요청 시 사용
* User-Agent
  * 유저 에이전트 애플리케이션 정보 (웹 브라우저 등)
  * 어떤 환경(브라우저)에서 장애가 발생하는지 분석 가능
  * 요청 시 사용
* Server
  * 요청을 처리하는 오리진 서버의 소프트웨어 정보
  * Server: Apache/2.2.22 (Debian)
  * Server: nginx
  * 응답 시 사용
* Date
  * 메시지가 생성된 날짜
  * `Date: Tue, 15 Nov 1994 08:12:31 GMT`
  * 응답 시 사용

---

#### 특별 정보
* Host
  * 요청한 호스트 정보(도메인)
  * 요청 시 사용
  * 필수 정보
  * 하나의 서버가 여러 도메인을 처리해야 하는 경우
  * 하나의 IP 주소에 여러 도메인이 적용되어 있는 경우
* Location
  * 페이지 리다이렉션
  * 201 (Created)
  * 3xx (Redirection)
* Allow
  * 허용 가능한 HTTP 메서드
  * 405 (Method Not Allowed) 반환 시 응답에 포함해야 함
    * 예) `Allow: GET, HEAD, PUT`
  * 일반적으로 실무에서 잘 사용되지 않음
* Retry-After
  * 유저 에이전트가 다음 요청을 하기까지 기다려야 하는 시간
  * 503 (Service Unavailable) 반환 시 언제까지 장애 상태인지 알려줄 수 있음
    * 예) `Retry-After: Fri, 31 Dec 1999 23:59:59 GMT` (날짜 표기)
    * 예) `Retry-After: 120` (초단위 표기)
  * 일반적으로 실무에서 사용하기 어려움

---

**인증**
* Authorization
  * 클라이언트 인증 정보를 서버에 전달
  * `Authorization: Basic xxxxxxxxxxxxxxxx`
* WWW-Authenticate
  * 리소스 접근시 필요한 인증 방법 정의
  * 401 (Unauthorized) 응답과 함께 사용
    * 예) `WWW-Authenticate: Newauth realm="apps", type=1, title="Login to \"apps\"", Basic realm="simple"`

---

### 쿠키
* Set-Cookie
  * 서버에서 클라이언트로 쿠키 전달(응답)
* Cookie
  * 클라이언트가 서버에서 받은 쿠키를 저장, HTTP 요청시 서버로 전달
  
**Stateless - 쿠키 사용 이유**
* 요청에 대한 응답 후 연결은 끊어짐
* 연결이 끊어지면 이전 요청을 기억하지 못함
* 매 요청마다 정보를 넘기는 것은 문제
  * 모든 요청에 사용자 정보가 포함되도록 개발해야 함
  * 브라우저를 완전 종료 후 다시 실행하면?
    * 이때 웹 스토리지 사용 가능

---

**쿠키 사용 예시**
* `set-cookie: sessionId=abcde1234; expires=Sat, 26-Dec-2020 00:00:00 GMT; path=/; domain=.google.com; Secure`
* 사용처
  * 사용자 로그인 세션 관리
  * 광고 정보 트래킹
* 쿠키 정보는 항상 서버에 전송됨
  * 네트워크 트래픽 추가 유발
  * 최소한의 정보만 사용(세션 id, 인증 토큰)
  * 서버에 전송하지 않고, 웹 브라우저 내부에 데이터를 저장 시 웹 스토리지 사용
    * localStorage, sessionStorage 등 참고
* 주의점
  * 쿠키, 웹 스토리 상관 없이 보안에 민감한 데이터는 저장하면 안됨
    * 주민번호, 신용카드 번호 정보 등

---

**쿠키 생명주기**
* `Set-Cookie: expires=Sat, 26-Dec-2020 04:39:21 GMT`
  * 일반적으로 GMT 표기
  * 만료일이 되면 쿠키 삭제
* `Set-Cookie: max-age=3600` (3600초)
  * 0이나 음수를 지정하면 쿠키 삭제
* 세션 쿠키
  * 만료 날짜를 생략하면 브라우저 종료할 때까지만 유지
* 영속 쿠키
  * 만료 날짜를 입력하면 해당 날짜까지 유지
  
---

**쿠키 접근 도메인**
* 예) `domain=example.org`
* 명시 (명시한 문서 기준 도메인 + 서브 도메인 포함)
  * `domain=example.org`를 지정해서 쿠키 생성
    * `example.org` 쿠키 접근
    * `dev.example.org`도 쿠키 접근
* 생략 (현재 문서 기준 도메인만 적용)
  * `example.org`에서 쿠키를 생성하고 domain 지정을 생략
    * `example.org` 에서만 쿠키 접근
    * `dev.example.org`는 쿠키 미접근

---

**쿠키 접근 경로**
* 예) `path=/home`
* 이 경로를 포함한 하위 경로 페이지만 쿠키 접근
* 일반적으로 `path=/` 루트로 지정
* 예)
  * `path=/home` 지정
  * `/home` -> 가능
  * `/home/level1` -> 가능
  * `/home/level1/level2` -> 가능
  * `/hello` -> 불가능

---

**쿠키 접근 보안**
* Secure
  * 기본적으로 쿠키는 http, https를 구분하지 않고 전송
  * Secure를 적용하면 https인 경우에만 전송
* HttpOnly
  * XSS 공격 방지
  * 자바스크립트에서 접근 불가(document.cookie)
  * HTTP 전송에만 사용
* SameSite
  * XSRF(CSRF( 공격 방지
  * 요청 도메인과 쿠키에 설정된 도메인이 같은 경우만 쿠키 전송
  * 브라우저의 지원 정도를 확인 후 사용할 것

---

### 캐시
* 캐시 미적용
  ~~~
  HTTP/1.1 200 OK
  Content-Type: image/jpeg
  Content-Length: 34012

  lkj123kljoiasudlkjaweioluywlnfdo912u34ljko98udjkla slkjdfl;qkawj9;o4ruawsldkal;skdjfa;ow9ejkl3123123
  ~~~
  * 데이터 변경이 없어도 네트워크를 통해 계속 데이터를 다운로드 함
  * 네트워크는 매우 느리고 비쌈
  * 브라우저 로딩 속도가 느림
  * 느린 사용자 경험
* 캐시 적용
  ~~~
  HTTP/1.1 200 OK
  Content-Type: image/jpeg
  cache-control: max-age=60
  Content-Length: 34012
  
  lkj123kljoiasudlkjaweioluywlnfdo912u34ljko98udjkla slkjdfl;qkawj9;o4ruawsldkal;skdjfa;ow9ejkl3123123
  ~~~
  * 요청 전 캐싱 유효 시간 확인하여 캐시 사용
    * 유효 시간 초과한 경우만 다시 요청, 캐시 갱신
  * 브라우저 로딩 속도가 빠름
  * 빠른 사용자 경험

---

**캐시 시간 초과**
* 캐시가 만료된 후에 데이터 갱신 여부에 따라 캐싱된 데이터 재사용 가능
  * 검증 헤더를 사용하여 데이터(기존-서버)간 갱신 유무를 비교
  
**Last-Modified 적용 후 캐시 시나리오**
* 검증 헤더 추가
  ~~~
  HTTP/1.1 200 OK
  Content-Type: image/jpeg
  cache-control: max-age=60
  Last-Modified: 2020년 11월 10일 10:00:00
  Content-Length: 34012
  
  lkj123kljoiasudlkjaweioluywlnfdo912u34ljko98udjklasl kjdfl;qkawj9;o4ruawsldkal;skdjfa;ow9ejkl3123123
  ~~~
* 캐시가 만료된 후 다시 요청 (조건부 요청)
  ~~~
  GET /star.jpg
  if-modified-since: 2020년 11월 10일 10:00:00
  ~~~
* 갱신된 것이 없을 때 304 (Not Modified) 반환
  * 메시지 바디가 없음 (갱신된 것이 없기 때문에)
    ~~~
    HTTP/1.1 304 Not Modified
    Content-Type: image/jpeg
    cache-control: max-age=60
    Last-Modified: 2020년 11월 10일 10:00:00
    Content-Length: 34012
    ~~~

**정리**
* 캐시 유효 시간을 초과해도 갱신된 것이 없다면 304 반환
  * 304 (Not Modified) + 헤더 메타 정보만 응답 (바디X)
  * 클라이언트는 서버가 보낸 응답 헤더 정보로 캐시의 메타 정보를 갱신
  * 클라이언트는 캐시에 저장되어 있는 데이터 재활용
  * 결과적으로 네트워크 다운로드가 발생하지만 용량이 적은 헤더 정보만 다운로드
* 매우 실용적

---

**검증 헤더와 조건부 요청**
* 검증 헤더
  * 캐시 데이터와 서버 데이터를 비교하여 같은지 검증
  * Last-Modified
  * ETag (Last-Modified 태그의 단점 보완)
* 조건부 요청 헤더
  * 검증 헤더로 조건에 따른 분기
  * If-Modified-Since: Last-Modified 사용
  * If-None-Match: ETag 사용
  * 조건이 만족하면 200 (OK)
  * 조건이 만족하지 않으면 304 (Not Modified)

---

**Last-Modified, If-Modified-Since**
* 데이터 미변경 예시
  * 캐시: 2020년 11월 10일 10:00:00 vs 서버: 2020년 11월 10일 10:00:00
  * 304 (Not Modified), 헤더 데이터만 전송 (바디 미포함)
  * 전송 용량 0.1M (헤더 0.1M, 바디 1.0M)
* 데이터 변경 예시
  * 캐시: 2020년 11월 10일 10:00:00 vs 서버: 2020년 11월 10일 11:00:00
  * 200 (OK), 모든 데이터 전송(BODY 포함)
  * 전송 용량 1.1M (헤더 0.1M, 바디 1.0M)
* 단점
  * 1초 미만(0.x초) 단위로 캐시 조정이 불가능
  * 날짜 기반의 로직 사용
  * 데이터를 수정해서 날짜가 다르지만, 같은 데이터를 수정해서 데이터 결과가 똑같은 경우
  * 서버에서 별도의 캐시 로직을 관리하고 싶은 경우
  * 예) 스페이스나 주석처럼 크게 영향이 없는 변경에서 캐시를 유지하고 싶은 경우

---

**ETag, If-None-Match**
* ETag(Entity Tag)
* 캐시용 데이터에 임의의 고유한 버전 이름을 태깅
  * 예) ETag: "v1.0", ETag: "a2jiodwjekjl3"
* 데이터가 변경되면 이 이름을 바꾸어서 변경함 (Hash를 다시 생성)
  * 예) ETag: "aaaaa" -> ETag: "bbbbb"
* 진짜 단순하게 ETag만 보내서 같으면 유지, 다르면 다시 다운로드

**ETag 적용 후 캐시 시나리오**
* 조건부 검증 헤더 추가
  ~~~
  HTTP/1.1 200 OK
  Content-Type: image/jpeg
  cache-control: max-age=60
  ETag: "aaaaaaaaaa"
  Content-Length: 34012
  
  lkj123kljoiasudlkjaweioluywlnfdo912u34ljko98udjklasl kjdfl;qkawj9;o4ruawsldkal;skdjfa;ow9ejkl3123123
  ~~~
* 캐시가 만료된 후 다시 요청 (조건부 요청)
  ~~~
  GET /star.jpg
  If-None-Match: "aaaaaaaaaa"
  ~~~
* 갱신된 것이 없을 때 304 (Not Modified) 반환
  * 메시지 바디가 없음 (갱신된 것이 없기 때문에)
    ~~~
    HTTP/1.1 304 Not Modified
    Content-Type: image/jpeg
    cache-control: max-age=60
    ETag "aaaaaaaaaa"
    Content-Length: 34012
    ~~~

**정리**
* 캐시 제어 로직을 서버에서 완전히 관리
* 클라이언트는 단순히 이 값을 서버에 제공 (클라이언트는 캐시 메커니즘을 모름)
* 예시
  * 서버는 배타 오픈 기간인 3일 동안 파일이 변경되어도 ETag를 동일하게 유지
  * 애플리케이션 배포 주기에 맞추어 ETag 모두 갱신

---

**캐시 제어 헤더**
* Cache-Control (캐시 지시어, 캐시 제어)
  * `Cache-Control: max-age`
    * 캐시 유효 시간, 초 단위
    * 일반적으로 긴 시간으로 설정
  * `Cache-Control: no-cache`
    * 데이터는 캐시해도 되지만, 항상 조건부 요청을 통해 `origin` 서버에 검증 받은 후 사용
    * 캐시 서버 무시
  * `Cache-Control: no-store`
    * 데이터에 민감한 정보가 있으므로 저장하면 안됨 (메모리에서 사용하고 최대한 빨리 삭제)
* Pragma (캐시 제어 - 하위 호환)
  * `Pragma: no-cache`
  * HTTP 1.0 하위 호환
* Expires (캐시 유효 기간 - 하위 호환)
  * 캐시 만료일 지정 하위 호환 (정확한 날짜로 지정)
  * HTTP 1.0 부터 사용
  * 지금은 더 유연한 `Cache-Control: max-age` 권장
  * `Cache-Control: max-age`와 함께 사용하면 `Expires`는 무시

**검증 헤더, 조건부 요청 헤더 정리**
* 검증 헤더
  * ETag: "v1.0", ETag: "asid93jkrh2l"
  * Last-Modified: Thu, 04 Jun 2020 07:19:24 GMT
* 조건부 요청 헤더
  * If-Match, If-None-Match
    * ETag 값 사용
  * If-Modified-Since, If-Unmodified-Since
    * Last-Modified 값 사용

---

**프록시 캐시**

Cache-Control
* `Cache-Control: public`
  * 응답이 public 캐시에 저장되어도 됨
* `Cache-Control: private` (기본값)
  * 응답이 해당 사용자만을 위한 것임, private 캐시에 저장해야 함
* `Cache-Control: s-maxage`
  * 프록시 캐시에만 적용되는 max-age
* `Age: 60` (HTTP 헤더)
  * 오리진 서버에서 응답 후 프록시 캐시 내에 머문 시간(초)

**캐시 무효화**
* 브라우저가 임의로 캐시 처리를 할 수 있기 때문에 해당 설정을 모두 적용하여 캐시 무효화
* 확실한 캐시 무효화 응답
* Cache-Control: no-cache, no-store, must-revalidate
  * `Cache-Control: no-cache`
    * 데이터는 캐시해도 되지만, 항상 조건부 요청을 통해 `origin` 서버에 검증 받은 후 사용
  * `Cache-Control: no-store`
    * 데이터에 민감한 정보가 있으므로 저장하면 안됨 (메모리에서 사용하고 최대한 빨리 삭제)
  * `Cache-Control: must-revalidate`
    * 캐시 만료 후 최초 조회 시 `origin` 서버에 검증해야 함
    * `origin` 서버 접근 실패 시 반드시 오류가 발생해야 함 - 504(Gateway Timeout)
    * must-revalidate는 캐시 유효 시간이라면 캐시 사용
* Pragma: no-cache
  * HTTP 1.0 하위 호환을 위해 적용

**no-cache, must-revalidate 비교**

장애 발생으로 `origin` 서버 접근 불가능한 경우
* no-cache는 캐시 서버 설정에 따라 오래된 데이터라도 반환 가능
* must-revalidate는 항상 오류를 발생(반환)해야 함 - 504 (Gateway Timeout)
