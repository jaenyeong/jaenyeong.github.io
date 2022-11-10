---
layout: single
permalink: /about/
date: 2022-11-10
title: "탄력적인 앱을 지향하는 개발자"
description: "About Me Engineer Programmer Developer Resume CV Curriculum Vitae Skill Project Experience 엔지니어 개발자 이력서"
subject: blog
toc_label: "about me"
toc_icon: "code"
toc_sticky: true
---

## Info
* **Name**   : 김재녕
* **E-mail** : jaenyeong.dev@gmail.com
* **Github** : [깃허브](https://github.com/jaenyeong)

---

## Introduce
안녕하세요. **Kotlin, Spring Boot**를 주력으로 개발하는 6년 차 백엔드 개발자 김재녕입니다.  
저는 다음과 같은 경험을 통해 성장하고 있습니다.
* 기획, 설계, 개발, 테스트, CI/CD 구축 등을 직접 경험
* 클라우드 비용 관리 및 리소스 최적화를 통한 비용 절감
* 코드 리뷰 및 테스트 코드 작성 활성화 등 개발 문화 개선 기여

또한 배우는 것을 좋아해 [다양한 강의](https://jaenyeong.github.io/learns/)를 꾸준히 수강하면서 학습, 훈련하고 있으며 이를 활용해 당면한 문제들을 풀어나가고 있습니다.

---

## Skill
* **Language** : Kotlin(Java)
* **Framework** : Spring Boot, JPA, JUnit
* **Database** : MySQL
* **Cloud** : AWS (EC2, CloudFront, RDS-Aurora, S3)
* **Etc** : K8s, Jenkins, Argo CD, Git

---

## Career

**에이치디정션 (2021.07 ~ 현재) : 백엔드 개발**

Kotlin(Spring Boot, JPA), K8s, NCP, Jenkins, ArgoCD, Git(Github)
* EMR API 서버 개발 및 외부 연계 작업
* 스테이지 서버 구축 및 운영 장애 대응
* 코드 리뷰 및 테스트 코드 작성 활성화 등 개발 문화 개선

---

**스페이스컬쳐 (2019.09 ~ 2020.01) : 백엔드 개발**

Java(Spring Boot, MyBatis), AWS, Git(Bitbucket)
* 인테리어 가구 추천 서비스의 API 서버 구축, 개발
* AWS 인프라 구축, 비용 관리

---

**ADOP (2018.09 ~ 2019.09) : 백엔드 개발**

Java(Spring Boot, MyBatis), PHP(CI), AWS, Jenkins, Git(Bitbucket)
* 광고 수익 정산 서비스 및 인사 관리 서비스 운영 및 유지보수
* 매체 기사를 AMP로 변환하는 서비스 개발, 유지보수
* AWS 인스턴스 및 비용 관리, 최적화

---

**브이스테이션 (2018.05 ~ 2018.08) : 백엔드 개발**

PHP(CI), Node.js, MySQL
* 해외 직구 쇼핑몰 서비스 간 통합 아이디 기능 구축

---

**미림미디어랩 (2017.04 ~ 2018.01) : 백엔드 & 앱 개발**

Java(Spring Boot), AWS, TypeScript(Ionic), Git
* 미디어박스(콘텐츠 동영상 재생 서비스) 앱과 API 서버 개발, 유지보수
  * 한국방송통신전파진흥원 지원사업 방송 콘텐츠 부분 최우수상 수상

---

**진코퍼레이션 (2015.02 ~ 2016.07) : 윈도우 프로그램 개발**

VB6, C#, PowerBuilder, Java(Spring-JSP), Oracle
* 자재 입출고 관리 시스템, 피킹 및 검품 프로그램 개발

---

## Project

**데이터 ETL 구현 및 실시간 연계 파이프라인 개발**

에이치디정션 (2021.09 ~ 2022.09) 1년

**설명**
* HAPI FHIR(의료 데이터 국제 기술 표준)를 활용해 자사 서비스 데이터 ETL 기능 구현
* 이벤트 처리 파이프라인 개발

**담당 업무**
* 자사 서비스의 데이터 약 1만건에 대한 ETL API 구현
  * 데이터 송수신 암복호화 FHIR 라이브러리 전용 인터셉터 구현
* 기존 서비스 모듈에 이벤트 생성 기능 추가
  * 엔티티 모듈 계층 의존관계로 인한 패키지 구조 리팩터링
* 실시간 이벤트 처리 컨슈머 모듈 구현
* Jenkins 빌드 파이프라인 및 ArgoCD 배포 설정

**사용 기술**
* Kotlin(Spring Boot), JPA, Gradle, K8s, Jenkins, ArgoCD, Kakfa(K8s Strimzi), HAPI FHIR

**문제 해결 사례**
* 데이터 양에 따라 발생하는 커넥션 타임아웃을 비동기 병렬 처리로 해결

---

**AWS 관리**

ADOP (2019.02 ~ 2019.03) 2개월

**설명**
* 사내 서비스의 AWS 인스턴스 리소스(트래픽, CPU 사용량 등) 모니터링, 비용 최적화

**담당 업무**
* AWS CloudWatch 콘솔을 통해 리소스 상태 모니터링, 장애 대응
* 메가존 빌링 서비스를 사용하여 AWS 인스턴스 비용 관리, 최적화
  * 사용되지 않는 서비스 모듈 및 AWS 리소스 정리, 인스턴스의 유형을 변경하여 유지 비용 절감

**사용 기술**
* AWS - EC2(AMI, ELB, Auto Scaling), RDS(Aurora), CloudWatch, Cloud Front, IAM

**문제 해결 사례**
* 대시 보드 모니터링을 통해 슬로우 쿼리 확인, 처리
  * 단순히 인덱스를 사용하지 않는 쿼리는 log_queries_not_using_indexes로 확인 가능

---

**AMP 변환 서비스 개발**

(2018.09 ~ 2019.01) 5개월

**설명**
* AMP(Accelerated Mobile Pages)는 일반 페이지보다 빠른 속도로 렌더링 되는 페이지
* 변환 모듈 개발, AMP 서버 유지보수 (광고 삽입하여 수익 창출)

**담당 업무**
* 고객사(매체)가 제공하는 RSS를 AMP 데이터로 변환하는 모듈 개발
  * Jsoup를 사용하여 크롤링 구현, 리눅스 crontab으로 반복 실행 처리
  * Bitbucket(web hook)과 Jenkins(execute shell)를 사용하여 배포 자동화
* AMP 퍼블리싱 서버 유지보수
  * 매체별 규격에 맞춰 AMP 유효성 확인, AMP(+AMP Story) 템플릿 수정
  * 구글 SEO(Search Engine Optimization) 가이드 적용, 문서화
* 구현한 스크래핑 모듈과 비슷한 모듈 6개를 모아 멀티 모듈로 구성
  * 약 3개의 EC2 인스턴스 삭제를 통해 월 기준 약 $200 절약

**사용 기술**
* Java, Jsoup, MyBatis, Gradle, JavaScript(Vue.js), PHP(CI)
* AWS(EC2, RDS-Aurora, CloudFront)
* Bitbucket, Jenkins

**개선**
* 같은 작업을 수행하는 모듈 6개를 하나의 멀티 모듈로 리팩터링
  * 관리 포인트 개선과 더불어 약 3개의 EC2 인스턴스 삭제를 통해 월 기준 약 $200 절약

---

## Learn

**도커/쿠버네티스 온라인 부트캠프 with 카카오엔터프라이즈 1기 (2021.08 ~ 2022.01)** 

[도커/쿠버네티스 핵심 개념과 클러스터 구성 방법 학습](https://github.com/jaenyeong/Lecture_Docker-K8S)
* ELK 등을 활용해 로그 모니터링 방법 학습
* ArgoCD 등을 활용해 컨테이너 앱의 배포 및 제어 방법 학습

---

**우아한테크캠프 Pro 1기 (2020.12 ~ 2021.01)**

수강생(지원자 약 200명 중 약 40명 선발) 중 우수 수료생(20명)으로 최종 수료

* TDD 학습
  * [Racing Car](https://github.com/jaenyeong/java-racingcar), [Lotto](https://github.com/jaenyeong/java-lotto)
* JPA 학습
  * [JWP-JPA](https://github.com/jaenyeong/jwp-jpa)
* ATDD(Acceptance Test Driven Development) 학습
  * [ATDD-Subway-admin](https://github.com/jaenyeong/atdd-subway-admin), [ATDD-Subway-service](https://github.com/jaenyeong/atdd-subway-service)
* 테스트 코드를 활용한 레거시 리팩터링
  * [JWP-Refactoring](https://github.com/jaenyeong/jwp-refactoring)
* AWS를 활용해 신뢰성 높은 서버 구축 방법 학습

---

## License

| 일자       | 자격증명       | 발급 기관                |
|:----------:|:--------------:|:------------------------:|
| 2018.07.10 | SQLD           | 한국 데이터 산업 진흥원  |
| 2016.11.21 | 정보 처리 기사 | 한국 산업 인력 공단      |

---

## Education
* [2020.03 ~ 2020.08] 국가평생진흥교육원 컴퓨터 공학과
* [2009.03 ~ 2015.02] 인하공업전문대학 컴퓨터 정보과

---

## ETC
* [수행한 프로젝트 전체 목록](https://jaenyeong.github.io/projects)
* [수강한 강의 전체 목록](https://jaenyeong.github.io/learns/)