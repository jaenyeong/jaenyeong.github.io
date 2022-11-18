---
layout: single
permalink: /about/
date: 2022-11-17
title: ""
description: "About Me Engineer Programmer Developer Resume CV Curriculum Vitae Skill Project Experience 엔지니어 개발자 이력서"
subject: blog
toc_label: "about me"
toc_icon: "code"
toc_sticky: true
---

## 6년 차 백엔드 개발자 김재녕
* jaenyeong.dev@gmail.com
* [Github](https://github.com/jaenyeong)

**Kotlin, Spring Boot**를 주력으로 개발하며 다음과 같은 경험을 통해 성장하고 있습니다.
* 설계, 구현, 테스트, CI/CD 구축 까지 개발 프로세스 전반을 직접 수행
* 클라우드 비용 관리 및 리소스 최적화를 통한 비용 절감

또한 배우는 것을 좋아해 다양한 강의를 꾸준히 수강하면서 학습, 훈련하고 있으며 이를 활용해 당면한 문제들을 풀어나가고 있습니다.

---

## Skill
* **Language** : Kotlin, Java
* **Framework** : Spring Boot, JPA, JUnit
* **Database** : MySQL
* **Cloud** : AWS (EC2, ALB, CloudFront, RDS-Aurora, S3)
* **Etc** : K8s, Jenkins, Argo CD, Git

---

## Career

### 에이치디정션 (2021.07 ~ 현재) 백엔드 개발

Kotlin(Spring Boot, JPA), K8s, NCP, Jenkins, ArgoCD, Git(Github)
* EMR API 서버 개발 및 외부 연계 작업
* 스테이지 서버 구축 및 운영 장애 대응
* 코드 리뷰 및 테스트 코드 작성 활성화 등 개발 문화 개선

### 스페이스컬쳐 (2019.09 ~ 2020.01) 백엔드 개발

Java(Spring Boot, MyBatis), AWS, Git(Bitbucket)
* 인테리어 가구 추천 서비스의 API 서버 구축, 개발
* AWS 인프라 구축, 비용 관리

### ADOP (2018.09 ~ 2019.09) 백엔드 개발

Java(Spring Boot, MyBatis), PHP(CI), AWS, Jenkins, Git(Bitbucket)
* 광고 수익 정산 서비스 및 인사 관리 서비스 운영 및 유지보수
* 매체 기사를 AMP로 변환하는 서비스 개발, 유지보수
* AWS 인스턴스 및 비용 관리, 최적화

### 미림미디어랩 (2017.04 ~ 2018.01) 백엔드 & 앱 개발

Java(Spring Boot), AWS, TypeScript(Ionic), Git
* 미디어박스(콘텐츠 동영상 재생 서비스) 앱과 API 서버 개발, 유지보수
  * 한국방송통신전파진흥원 지원사업 방송 콘텐츠 부분 최우수상 수상

### 진코퍼레이션 (2015.02 ~ 2016.07) 윈도우 프로그램 개발

VB6, C#, PowerBuilder, Java(Spring-JSP), Oracle
* 자재 입출고 관리 시스템, 피킹 및 검품 프로그램 개발

---

## Project

### 트루닥(EMR) 서비스 운영 및 장애 대응, 인프라 관리

에이치디정션 (2022.09 ~ 2022.11) 2개월

**담당 업무**
* 동시 요청으로 인한 QueryDSL 멀티 스레드 초기화 시 Qclass 순환 참조로 발생하는 데드락 장애 대응  
  @Configuration 클래스 내에 패키지 스캔 설정을 추가, 서버 로딩 시 싱글 스레드로 초기화 처리
* 스프링부트 최대 메모리 설정이 약 `4GB`로 K8s 파드 설정(`2.5Gib`)보다 높아 발생한 파드 OOM Kill(137) 장애 대응  
  파드의 limit 설정 변경(`4.5Gib`)과 동시에 request 설정을 동일하게 수정
* `Xen citrix`를 통해 Stage 서버 노드 구축 및 각 모듈 K8s 서비스 파드 배포

**사용 기술**
* Kotlin(Spring Boot), JPA, Gradle, K8s, Jenkins, ArgoCD, NCP, Github

---

### HAPI FHIR를 활용한 데이터 ETL 구현 및 실시간 연계 파이프라인 개발

에이치디정션 (2021.09 ~ 2022.08) 1년

**설명**
* HAPI FHIR(의료 데이터 국제 기술 표준) 프레임워크 활용

**담당 업무**
* 자사 서비스의 데이터 약 1만건에 대한 ETL 구현  
  이때 발생하는 DB 커넥션 타임아웃을 컬렉션의 parallel, @Async 조합으로 병렬 처리하여 해결
* 데이터 송수신 암복호화 FHIR 라이브러리 전용 인터셉터 구현
* 기존 서비스 모듈에 카프카 이벤트 생성 기능 추가  
  데이터 정합성을 위해 제로페이로드 형태로 이벤트 추가하여 컨슈머에서 다시 조회 처리  
  동시에 엔티티 레이어 모듈 의존 관계 때문에 패키지 구조 리팩터링 진행
* 실시간 이벤트 처리 카프카 컨슈머 모듈 구현
* Jenkins 빌드 파이프라인, ArgoCD 배포 설정

**사용 기술**
* Kotlin(Spring Boot), JPA, Gradle, K8s, Jenkins, ArgoCD, Kakfa(K8s Strimzi), HAPI FHIR

---

### AWS 비용 관리 및 리소스 상태 모니터링, 장애 대응

ADOP (2019.02 ~ 2019.03) 2개월

**설명**
* 사내 서비스의 AWS 인스턴스 리소스(트래픽, CPU 사용량 등) 모니터링, 비용 최적화

**담당 업무**
* 스케일 아웃 시 AZ 내 가용 리소스가 부족한 상황 대응  
  Auto Scaling 그룹 설정의 다른 AZ 추가 및 VM 노드 직접 삽입하여 처리
* 슬로우 쿼리 확인 및 처리 (log_queries_not_using_indexes 설정)
* 태그나 대시보드를 기준으로 사용되지 않는 서비스 모듈 및 AWS 리소스 정리  
  또는 사용하는 인스턴스 유형 변경

**사용 기술**
* AWS - EC2(AMI, ELB, Auto Scaling), RDS(Aurora), CloudWatch, Cloud Front, IAM

---

### AMP 변환 서비스 개발 및 서버 유지보수

(2018.09 ~ 2019.01) 5개월

**설명**
* AMP(Accelerated Mobile Pages)는 일반 페이지보다 빠른 속도로 렌더링 되는 페이지

**담당 업무**
* Jsoup를 사용하여 고객사(매체)가 제공하는 RSS를 AMP 데이터로 변환하는 크롤링 모듈 개발  
  리눅스 crontab으로 반복 실행 처리  
  Bitbucket(web hook)과 Jenkins(execute shell)를 사용하여 배포 자동화
* AMP 퍼블리싱 서버 매체별 규격에 맞춰 AMP 유효성 확인, AMP(+AMP Story) 템플릿 수정  
  구글 SEO(Search Engine Optimization) 가이드 적용, 문서화
* 구현한 스크래핑 모듈과 비슷한 모듈 6개를 모아 멀티 모듈로 구성하면서 관리 포인트 개선  
  이때 약 3개의 EC2 인스턴스 삭제를 통해 월 기준 약 $200 절약

**사용 기술**
* Java(Jsoup, MyBatis), JavaScript(Vue.js), PHP(CI)
* AWS(EC2, RDS-Aurora, CloudFront), Bitbucket, Jenkins

---

## Learn

**카카오 엔지니어와 데이터 엔지니어링 입문 3기 (2022.09 ~ 2022.10)**

* ETL 설계 시 제로페이로드 등 참고

**도커/쿠버네티스 온라인 부트캠프 with 카카오엔터프라이즈 1기 (2021.08 ~ 2022.01)**

* 실습을 통한 클러스터, 파드 구성 및 제어 방법 학습

**우아한테크캠프 Pro 1기 (2020.12 ~ 2021.01)**

* TDD 및 ATDD(Acceptance Test Driven Development), JPA, 레거시 리팩터링 학습
* 수강생(지원자 약 200명 중 약 40명 선발) 중 우수 수료생(20명)으로 최종 수료

[자세히 보기](https://jaenyeong.github.io/learns/)

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
개발 문화 개선에도 관심이 많아 아래와 같은 경험이 있습니다.
* 코드 리뷰 리딩 및 정책 제안
* 테스트 코드 작성 활성화 권장