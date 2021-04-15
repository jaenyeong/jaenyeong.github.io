---
layout: single
permalink: /about/
date: 2021-04-16
title: "엔지니어를 향해 걷는 개발자"
description: "About Me Engineer Programmer Developer Resume CV Curriculum Vitae Skill Project Experience 엔지니어 개발자 이력서"
subject: blog
toc_label: "about me"
toc_icon: "code"
toc_sticky: true
---

## Info
* **Name**   : 김재녕
* **e-mail** : jaenyeong.dev@gmail.com
* **Github** : [깃허브](https://github.com/jaenyeong)

---

## Introduce
안녕하세요. **Java, Spring Boot, AWS**를 주력으로 개발해온 5년 차 백엔드 개발자 김재녕입니다.  
저는 SI, 스타트업 등 다양한 환경에서 개발자로서 경험을 쌓아왔습니다.  
* 기획, 설계, 개발, 테스트, 배포 등 개발 프로세스 전반을 직접 수행
* 기업 내 서비스와 인프라를 꾸준히 관리하여 유지 비용 절감
* 대규모 시스템 개발 프로젝트에 참여, 현장 시스템 통합 테스트 진행

위 경험을 기반으로 고객에게 편의를 제공할 수 있는 **리액티브 시스템**을 구축하려 노력하고 있습니다.

그리고 이를 위해 평소에도 꾸준히 책을 읽거나 강의 수강을 통해 학습, 훈련하고 있으며 
이렇게 얻은 지식을 업무에 활용하며 당면한 문제들을 풀어나가고 있습니다.

---

## Skill
* **Language** : Java
* **Framework** : Spring Boot, MyBatis, JUnit
* **Database** : MySQL
* **Cloud** : AWS (EC2, CloudFront, RDS-Aurora, S3)
* **Tool** : IntelliJ IDEA
* **Etc** : Gradle, Git(GitHub), Jenkins

---

## Career

### 스페이스컬쳐 (2019.09 ~ 2020.01)
**백엔드 개발** : Java(Spring Boot), AWS, Git(Bitbucket)

> * 인테리어 가구 추천 서비스의 API 서버 구축, 개발
> * AWS 인프라 구축, 비용 관리

---

### ADOP (2018.09 ~ 2019.09)
**백엔드 개발** : Java(Spring Boot), PHP(CI), AWS, Git(Bitbucket), Jenkins, Jira

> * 광고 수익 정산 비용 관리 서비스 레거시 리팩터링, 유지보수
> * 사내 AWS 인스턴스 관리, 비용 최적화
> * 매체 기사를 AMP로 변환하는 서비스 개발, 유지보수
> * 사내 인사 관리 서비스 유지보수

---

### 브이스테이션 (2018.05 ~ 2018.08)
**백엔드 개발** : PHP(CI), Node.js, MySQL

> * 해외 직구 쇼핑몰 서비스 간 통합 아이디 기능 구축

---

### 미림미디어랩 (2017.04 ~ 2018.01)
**앱 & 백엔드 개발** : Java(Spring Boot), AWS, TypeScript(Ionic), Git

> * 미디어박스(콘텐츠 동영상 재생 서비스) 앱과 API 서버 개발, 유지보수
> * 한국방송통신전파진흥원에서 지원사업 방송 콘텐츠 부분 최우수상 수상 (미디어박스)

---

### 진코퍼레이션 (2015.02 ~ 2016.07)
**윈도우 응용 프로그램 개발** : VB6, C#, PowerBuilder, Java(Spring-JSP), Oracle

> * 피킹 및 검품 프로그램과 자재 입출고 관리 시스템 개발, 유지보수
> * 현장 통합 테스트 진행, 프로그램 세팅
>   * 미국 LA 해외 출장(1개월), 경북 김천 출장(6개월) 등

---

## Project

### 공간기록 (가구 인테리어 디자인 플랫폼) 개발
스페이스컬쳐 (2019.09 ~ 2020.01) 5개월

> **설명**
> * 오늘의집 앱을 벤치마킹한 가구 제품 거래 서비스 개발
> * 인테리어 디자이너가 고객에게 인테리어를 제안하며 제품을 추천하는 플랫폼
> 
> **담당 업무**
> * TDD를 활용해 REST API 서버 개발
>   * Bootpay API를 활용하여 결제 검증, 취소 기능 개발
>   * FireStore를 활용하여 채팅 기능 API 개발
>   * 그 외 카트, 상품, 주문 등 주요 기능 CRUD API 개발 및 단위 테스트 작성
>   * DDD를 기반으로 서버 구조 리팩터링
> * Spring Boot Log, DB 등 초기 설정
> * DB 스키마 설계
> * AWS 인프라 구축, 운영(비용 관리)
> 
> **사용 기술**
> * Java(Spring Boot, Log4j2), MyBatis, Gradle, JUnit, AWS(EC2, RDS-Aurora), Bitbucket, Bootpay API, FireStore

---

### Insight (광고 수익 정산 서비스) 유지보수
ADOP (2019.04 ~ 2019.07) 4개월

> **설명**
> * 광고 수익 정산 관리를 위한 사내 서비스 유지보수, 운영
> 
> **담당 업무**
> * 신규 기능 추가, 기존 기능 버그 수정
>   * 국가별 환율에 따라 부가세 계산, 매체별 배분율 계산 등 수익 정산 기능 유지보수
>   * 정산 이월, 지급일 변경, 메일 전송 등 기능 유지보수
>   * 광고 수익 데이터 파일 업로드 기능 구현
>   * 기능별 중복 코드 리팩터링, 구조 개선과 쿼리 튜닝
>   * 그 외 운영팀의 사용 편의성을 위한 추가 요구사항 반영
> * Bitbucket(web hook)과 Jenkins(execute shell), 리눅스 crontab을 통한 배포 자동화
> 
> **사용 기술**
> * Java(Spring Boot, Logback), MyBatis, Gradle, JUnit, JavaScript(jQuery), AWS(EC2, RDS-Aurora, ACM), Bitbucket, Jenkins

---

### AWS 관리
ADOP (2019.02 ~ 2019.03) 2개월

> **설명**
> * 사내 서비스의 AWS 인스턴스 리소스(트래픽, CPU 사용량 등) 모니터링, 비용 최적화
> 
> **담당 업무**
> * 사용되는 AWS 인스턴스 리소스를 AWS CloudWatch 콘솔을 통해 모니터링, 장애 대응
>   * 특정 서비스의 트래픽 부하로 스케일링 그룹 AZ의 리소스 부족으로 스케일 아웃 실패
>   * AMI로 다른 AZ의 인스턴스 직접 생성하여 로드밸런서에 연결하여 대응
> * 사용되지 않는 서비스 모듈 약 10개 정리
> * 메가존 빌링 시스템을 사용하여 AWS 인스턴스 비용 관리 및 최적화
>   * 사용되지 않는 AWS 리소스(EC2, EBS 등) 삭제하여 월 기준 약 30달러 절약
>   * 인스턴스의 유형 변경 또는 예약 인스턴스 사용으로 비용 절감
> * 비용 절감 목적으로 SpotInst(베스핀 기업의 스팟인스턴스 관리 서비스) 사용 테스트
>   * 해당 서비스의 불안정한 상태 때문에 적용 실패
> 
> **사용 기술**
> * AWS - EC2(AMI, ELB, Auto Scaling), RDS(Aurora), CloudWatch, Cloud Front, IAM
> 
> **문제 해결 사례**
> * 특정 DB 인스턴스의 CPU 사용량이 불특정한 주기로 급증하는 상태 확인
> * 트래픽은 평소와 같아 슬로우 쿼리라고 판단, 슬로우 쿼리 로그에 기록된 쿼리를 모두 분석
>   * 클러스터 파라미터 그룹에서 slow_query_log 설정
> * 실행 계획이 풀 테이블 스캔인 슬로우 쿼리를 찾아 해당 테이블에 인덱스 생성하여 처리
> 
> **배운 점**
> * slow_query_log 설정으로 슬로우 쿼리를 로그로 남길 시 딱 슬로우 쿼리만이 기록될 거라 예상
> * 하지만 쿼리의 실행 계획이 아닌 실제 쿼리 실행 시간을 기준으로 슬로우 쿼리가 판단됨
> * 따라서 동시에 실행되는 쿼리도 영향을 받아 실제 빠른 쿼리라도 로그에 남는 경우 발생
>   * long_query_time 옵션으로 슬로우 쿼리 기준 시간 설정 가능
>   * 하지만 슬로우 쿼리를 식별할 기준 시간의 정확한 측정이 어려움
> * 단순히 인덱스를 사용하지 않는 쿼리는 log_queries_not_using_indexes로 확인 가능

---

### AMP 변환 서비스 개발
ADOP (2018.09 ~ 2019.01) 5개월

> **설명**
> * AMP(Accelerated Mobile Pages)는 일반 페이지보다 빠른 속도로 렌더링 되는 페이지
> * 변환 모듈 개발, AMP 서버 유지보수 (광고 삽입하여 수익 창출)
> 
> **담당 업무**
> * 고객사(매체)가 제공하는 RSS를 AMP 데이터로 변환하는 배치 모듈 개발
>   * Jsoup를 사용하여 크롤링 구현, 리눅스 crontab으로 반복 실행 처리
>   * Bitbucket(web hook)과 Jenkins(execute shell)를 사용, 배포 자동화
> * 구글 SEO(Search Engine Optimization) 가이드 적용, 문서화
>   * 구글 검색시 상단 노출, AMP별 요청 트래픽 발생으로 광고 수익 창출
> * AMP 퍼블리싱 서버 유지보수, 운영
>   * 매체별 규격에 맞춰 AMP 유효성 확인, AMP(+AMP Story) 템플릿 수정
>   * 각 기사 페이지 CDN(AWS CloudFront) 적용하여 렌더링 속도 개선
> 
> **사용 기술**
> * Java(Jsoup), MyBatis, Gradle, PHP(CI), JavaScript(Vue.js), AWS(EC2, RDS-Aurora), Bitbucket, Jenkins
> 
> **문제 해결 사례**
> * 구현한 스크래핑 모듈과 비슷한 모듈이 기존에 다수 존재하는 것을 개발 후에 알게됨
> * 각각 다른 AWS EC2 인스턴스에 배포된 상태로 인해 소스 및 배포 관리 또한 어려움
> * AWS 태그를 기준으로 트래픽과 해당 모듈들의 로직을 확인하여 스크래핑 모듈 식별
> * 스크래핑 모듈 약 6개를 하나의 모듈로 병합하여 관리 포인트 축소
> * 사용하지 않는 온디맨드 EC2 인스턴스 약 3개 삭제하여 약 $200 절약 (월 기준)
> 
> **배운 점**
> * 소스 병합이 어렵다면 빌드툴(Gradle)을 활용해 멀티 모듈로 구성하면 관리 포인트를 줄일 수 있음
> * 각 모듈의 기능, 의존 라이브러리를 공유하여 이전보다 깔끔한 구조가 됨
>   * 다만 이때 상위 모듈이 안정적이지 않다면 하위 모듈이 영향을 받아 계속 변경되게 됨
>   * 따라서 안정적인 기능, 레이어 등을 의존하는 구조로 구성해야 함
>   * 필요하다면 추상화 컴포넌트를 새로 생성해 의존성 역전 원칙을 적용

---

### 미디어박스 (콘텐츠 동영상 재생 플랫폼) 개발
미림미디어랩 (2017.04 ~ 2018.01) 10개월

> **설명**
> * 유튜브 앱을 벤치마킹한 콘텐츠 동영상 재생 플랫폼 서비스 개발
> * 사용자가 선택한 콘텐츠 각본에 따라 다른 영상이 재생되는 플랫폼
> 
> **담당 업무**
> * Ionic을 사용해 하이브리드 앱 개발
>   * 채널, 시청 기록, 구독, 코멘트 등 각 화면 구현, 데이터 송수신(렌더링)
> * REST API 서버 개발
>   * 채널, 시청 기록, 구독, 코멘트 등 각 기능 CRUD API 구현
> * DB 스키마 설계
> 
> **사용 기술**
> * Java(Spring Boot, Logback), MyBatis, Gradle, TypeScript(Ionic), AWS(EC2, RDS), Vimeo API
> 
> **문제 해결 사례**
> * 사전에 트래픽 부하 테스트를 진행하지 않은 채 서비스 오픈
> * 앱에서 영상 시청 트래픽 부하로 인해 서비스 장애 발생
> * 이를 개발한 팀원이 원인을 찾지 못해 페어 프로그래밍으로 함께 확인
>   * Vimeo 서버에 영상 데이터 호출 시 특정 시간 내 API 호출 제한으로 장애 발생
>   * ehCache(캐시 라이브러리)를 사용하여 서버에 영상 데이터를 캐싱 처리하여 해결
> * 이후부터 코드 리뷰 등 업무 공유 시간을 통해 해당 문제와 유사한 문제들을 사전 방지
> 
> **배운 점**
> * 이와 같은 경우 추가로 CDN 등으로 캐싱 서버를 두어 캐싱처리 하는 것이 효율적
>   * 서버에 데이터를 직접 요청 시 트래픽이 증가하여 다른 서비스(API)에 영향을 줄 수 있음
>   * 또한 용량이 큰 데이터를 서버에서 직접 캐싱하는 것은 성능(메모리)에 지장을 초래함

---

### 그 외 나머지 프로젝트
* [수행한 모든 프로젝트](https://jaenyeong.github.io/projects)

---

## Learn

### 우아한테크캠프 Pro 1기
Next Step & 우아한 형제들 (2020.12 ~ 2021.01)

> * 일반 사용자가 사용하는 서비스 개발에 필요한 지식과 기술 학습
>   * TDD(클린코드, 리팩터링), ATDD, JPA, AWS 등 학습
>   * 각 미션마다 리뷰어의 코드리뷰를 통해 코칭
> * 수강생(지원자 약 200명 중 약 40명 선발) 중 우수 수료생(20명)으로 최종 수료
>   * Next Step 멤버십을 통해 이력서, 기술면접 멘토링 교육 수강
> * [JWP-Refactoring](https://github.com/jaenyeong/jwp-refactoring)
> * [ATDD-Subway-service](https://github.com/jaenyeong/atdd-subway-service)
> * [ATDD-Subway-admin](https://github.com/jaenyeong/atdd-subway-admin)
> * [JWP-JPA](https://github.com/jaenyeong/jwp-jpa)
> * [Lotto](https://github.com/jaenyeong/java-lotto)
> * [Racing Car](https://github.com/jaenyeong/java-racingcar)

---

### 나홀로 DDD Workshop
Fastcampus (2019.09 ~ 2019.09)

> * 도메인, 애그리게이트 등 개념과 기존 DB 위주 개발시 패러다임 불일치 문제점 등 학습
> * 공간기록 프로젝트의 기획, 설계 단계에서 적용
> * [DDD 학습 1](https://github.com/jaenyeong/Lecture_DDD-190921)
> * [DDD 학습 2](https://github.com/jaenyeong/Lecture_DDD-190922)

---

### 클린코드를 위한 TDD, 리팩터링 3기
Next Step (2018.11 ~ 2018.12)

> * TDD의 대한 개념과 클린코드의 중요성, 테스트 코드를 통한 안전한 리팩터링 방법 학습 
> * 공간기록 프로젝트에서 수강 내용을 활용해 클린코드를 작성
>   * 객체지향 설계와 단위 테스트 작성으로 기존보다 유연하고 안정적으로 기능 구현

---

### 스프링부트를 활용한 쇼핑몰 프로젝트 1기
Fastcampus (2018.07 ~ 2018.09)

> * Spring Boot의 AOP, IoC, PSA의 개념, 아키텍처, 설정 방법 등 학습
> * Insight, 공간기록 등 Spring Boot를 사용하는 모든 프로젝트에서 수강 내용 활용
> * [Spring Boot 학습](https://github.com/jaenyeong/Lecture_SpringBoot)

---

### 그 외 나머지 강의
* [수강한 모든 강의](https://jaenyeong.github.io/learns)

---

## License

| 일자       | 자격증명       | 발급 기관                |
|:----------:|:--------------:|:------------------------:|
| 2018.07.10 | SQLD           | 한국 데이터 산업 진흥원  |
| 2016.11.21 | 정보 처리 기사 | 한국 산업 인력 공단      |

## Education
* [2020.03 ~ 2020.08] 국가평생진흥교육원 컴퓨터 공학과
* [2009.03 ~ 2015.02] 인하공업전문대학 컴퓨터 정보과
