---
layout: single
permalink: /about/
date: 2022-09-17
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
안녕하세요. **Kotlin(Java), Spring Boot**를 주력으로 개발하는 6년 차 백엔드 개발자 김재녕입니다.  
저는 다음과 같은 경험을 통해 성장하고 있습니다.
* 기획, 설계, 개발, 테스트, CI/CD 등 개발 프로세스 전반을 직접 수행
* 사내 클라우드 관리 및 사용중인 리소스 최적화를 통한 비용 절감 경험
* 코드 리뷰 활성화 등 개발 문화 개선 기여

또한 배우는 것을 좋아해 [다양한 강의](https://jaenyeong.github.io/learns/)를 꾸준히 수강하면서 학습, 훈련하고 있으며 이를 활용해 당면한 문제들을 풀어나가고 있습니다.

---

## Skill
* **Language** : Kotlin(Java)
* **Framework** : Spring Boot, JPA, JUnit
* **Database** : MySQL
* **Cloud** : AWS (EC2, CloudFront, RDS-Aurora, S3)
* **Etc** : K8s, Kafka, Jenkins, Argo CD, Git

---

## Career

**에이치디정션 (2021.07 ~ 현재)**
> 백엔드 개발 : Kotlin(Spring Boot-JPA), NCP, Git(Github), K8s(Docker), Jenkins, Argo CD, Kafka
> * EMR 솔루션 API 서버 개발 및 외부 연계 작업 수행
> * 코드 리뷰 활성화, 테스트 코드 작성 권유 등 개발 문화 개선
> * CI/CD, SRE 병행

---

**스페이스컬쳐 (2019.09 ~ 2020.01)**
> 백엔드 개발 : Java(Spring Boot), AWS, Git(Bitbucket)
> * 인테리어 가구 추천 서비스의 API 서버 구축, 개발
> * AWS 인프라 구축, 비용 관리

---

**ADOP (2018.09 ~ 2019.09)**
> 백엔드 개발 : Java(Spring Boot), PHP(CI), AWS, Git(Bitbucket), Jenkins
> * 광고 수익 정산 비용 관리 서비스 레거시 리팩터링, 유지보수
> * 사내 AWS 인스턴스 관리, 비용 최적화
> * 매체 기사를 AMP로 변환하는 서비스 개발, 유지보수
> * 사내 인사 관리 서비스 유지보수

---

**브이스테이션 (2018.05 ~ 2018.08)**
> 백엔드 개발 : PHP(CI), Node.js, MySQL
> * 해외 직구 쇼핑몰 서비스 간 통합 아이디 기능 구축

---

**미림미디어랩 (2017.04 ~ 2018.01)**
> 백엔드 & 앱 개발 : Java(Spring Boot), AWS, TypeScript(Ionic), Git
> * 미디어박스(콘텐츠 동영상 재생 서비스) 앱과 API 서버 개발, 유지보수
>   * 한국방송통신전파진흥원 지원사업 방송 콘텐츠 부분 최우수상 수상

---

**진코퍼레이션 (2015.02 ~ 2016.07)**
> 윈도우 프로그램 개발 : VB6, C#, PowerBuilder, Java(Spring-JSP), Oracle
> * 자재 입출고 관리 및 피킹 및 검품 프로그램 개발 및 현장 통합 테스트 진행
>   * 장기 출장: 미국 LA(1개월), 경북 김천(6개월) 등

---

## Project

**데이터 ETL 구현 및 실시간 연계 파이프라인 개발**

에이치디정션 (2021.09 ~ 2022.09) 1년

> **설명**
> * HAPI FHIR(의료 데이터 국제 기술 표준)를 활용해 자사 서비스 데이터 ETL 기능 구현
> * 자사 서비스 데이터 기반 실시간 이벤트 처리 파이프라인 개발
>
> **담당 업무**
> * FHIR 라이브러리, JPA를 활용해 자사 서비스의 데이터 약 1만건에 대한 ETL 기능 구현
>   * 일괄 조회한 데이터를 청크하여 병렬로 변환, 전송 처리 구현
>   * 데이터 송수신 시 사용되는 암복호화 라이브러리 인터셉터 구현
>   * 범위 지정 ETL API, 조회 및 수정 API 구현
> * 기존 서비스 수정
>   * 엔티티 리스너를 활용해 기존 서비스의 이벤트 produce 기능 추가
>   * 엔티티 모듈 계층 의존관계로 인한 패키지 구조 리팩터링
> * 실시간 이벤트 처리 모듈 구현
>   * K8s Strimzi(Kafka)를 활용한 카프카 브로커 설정
>   * 이벤트 consume하여 해당 데이터 ETL 기능 구현
>   * Jenkins 빌드 파이프라인, ArgoCD 배포 설정
>
> **사용 기술**
> * Kotlin(Spring Boot), JPA, Gradle, Github, K8s, Jenkins, ArgoCD, Kakfa, HAPI FHIR 라이브러리

---

**AWS 관리**

ADOP (2019.02 ~ 2019.03) 2개월

> **설명**
> * 사내 서비스의 AWS 인스턴스 리소스(트래픽, CPU 사용량 등) 모니터링, 비용 최적화
> 
> **담당 업무**
> * 사용되는 AWS 인스턴스 리소스를 AWS CloudWatch 콘솔을 통해 모니터링, 장애 대응
>   * 특정 서비스의 스케일링 그룹 AZ의 리소스 부족으로 오토 스케일 아웃 실패
>   * AMI로 다른 AZ의 인스턴스 직접 생성하여 로드밸런서에 연결하여 대응
>   * 스케일링 그룹의 다른 AZ를 추가하여 향후 장애 방지
> * 메가존 빌링 서비스를 사용하여 AWS 인스턴스 비용 관리, 최적화
>   * 사용되지 않는 서비스 모듈 및 AWS 리소스 정리, 인스턴스의 유형을 변경하여 유지 비용 절감
> * 비용 절감 목적으로 SpotInst(베스핀 기업의 스팟인스턴스 관리 서비스) 사용 테스트
>   * 해당 서비스의 불안정한 상태 때문에 적용 실패
> 
> **사용 기술**
> * AWS - EC2(AMI, ELB, Auto Scaling), RDS(Aurora), CloudWatch, Cloud Front, IAM
> 
> **문제 해결 사례**
> * 트래픽이 평시와 비슷한 상태에서 DB CPU 사용량이 불특정한 주기로 급증하는 상태 확인
> * 먼저 슬로우 쿼리 로그에 기록된 쿼리를 모두 분석
>   * AWS RDS 클러스터 파라미터 그룹의 slow_query_log 설정
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

**AMP(Accelerated Mobile Pages) 변환 서비스 개발**

ADOP (2018.09 ~ 2019.01) 5개월

> **설명**
> * AMP는 일반 페이지보다 빠른 속도로 렌더링 되는 페이지
> * 변환 모듈 개발, AMP 서버 유지보수 (광고 삽입하여 수익 창출)
> 
> **담당 업무**
> * 고객사(매체)가 제공하는 RSS를 AMP 데이터로 변환하는 모듈 개발
>   * Jsoup를 사용하여 크롤링 구현, 리눅스 crontab으로 반복 실행 처리
>   * Bitbucket(web hook)과 Jenkins(execute shell)를 사용하여 배포 자동화
> * AMP 퍼블리싱 서버 유지보수
>   * 매체별 규격에 맞춰 AMP 유효성 확인, AMP(+AMP Story) 템플릿 수정
>   * CDN(AWS CloudFront) 적용하여 페이지 렌더링 속도 개선
>   * 구글 SEO(Search Engine Optimization) 가이드 적용, 문서화
> 
> **사용 기술**
> * Java(Jsoup), MyBatis, Gradle, PHP(CI), JavaScript(Vue.js), AWS(EC2, RDS-Aurora), Bitbucket, Jenkins
> 
> **개선**
> * 구현한 스크래핑 모듈과 비슷한 모듈 6개를 모아 멀티 모듈로 구성
>   * AWS 인스턴스 태그 및 트래픽을 기준으로 연관 모듈을 식별 및 분석
>   * 사용하지 않게 된 약 3개의 AWS EC2 인스턴스 삭제를 통해 월 기준 약 $200 절약
>   * 해당 작업을 통해 소스 관리, CI/CD 등 관리 포인트 개선
>     
> **배운 점**
> * 싱글 리포지터리 및 멀티 모듈 구조는 구글에서도 자주 차용되는 관리 형태
> * 멀티 모듈 구성시에는 하위 모듈에서 영향을 받기 때문에 상위 모듈은 변화가 적고 안정적이게 구성할 것

---

## Learn

**[카카오 엔지니어와 데이터 엔지니어링 입문 3기] (2022.09 ~ 진행 중)**

> 효율적인 데이터 파이프라인 설계 및 구축을 위해 수강
>
> 데이터 엔지니어링, 파이프라인 개념 학습 및 실습
> * AWS(S3, Athena, Kinesis), ELK, Kafka 등을 활용한 데이터 파이프라인 구현

---

**[도커/쿠버네티스 온라인 부트캠프 with 카카오엔터프라이즈 1기] (2021.08 ~ 2022.01)** 
> 사내 구성된 K8s 인프라를 잘 다루는 데 활용
>
> [도커/쿠버네티스 핵심 개념과 클러스터 구성 방법 학습](https://github.com/jaenyeong/Lecture_Docker-K8S)
> * ELK 등을 활용해 로그 모니터링 방법 학습
> * ArgoCD 등을 활용해 컨테이너 앱의 배포 및 제어 방법 학습

---

**[우아한테크캠프 Pro 1기] (2020.12 ~ 2021.01)**
> 코드 리뷰를 통해 각 미션을 진행하며 클린코드 작성 및 JPA 사용 방법, 아키텍처 설계 방법 등 학습
> * TDD를 통한 OOP 설계 및 테스트하기 쉬운 코드 작성 방법 학습
>   * [Racing Car](https://github.com/jaenyeong/java-racingcar), [Lotto](https://github.com/jaenyeong/java-lotto)
> * JPA를 통한 ORM 개념 학습
>   * [JWP-JPA](https://github.com/jaenyeong/jwp-jpa)
> * ATDD(Acceptance Test Driven Development)를 통해 다양한 케이스를 테스트하는 방법 학습
>   * [ATDD-Subway-admin](https://github.com/jaenyeong/atdd-subway-admin), [ATDD-Subway-service](https://github.com/jaenyeong/atdd-subway-service)
> * 테스트코드를 통해 기존 레거시 프로젝트 리팩터링
>   * [JWP-Refactoring](https://github.com/jaenyeong/jwp-refactoring)
> * AWS를 활용해 신뢰성 높은 서버 구축 방법 학습
> 
> 수강생(지원자 약 200명 중 약 40명 선발) 중 우수 수료생(20명)으로 최종 수료
> * 해당 자격을 통해 이력서, 기술면접 멘토링

---

## License

| 일자       | 자격증명       | 발급 기관                |
|:----------:|:--------------:|:------------------------:|
| 2018.07.10 | SQLD           | 한국 데이터 산업 진흥원  |
| 2016.11.21 | 정보 처리 기사 | 한국 산업 인력 공단      |

## Education
* [2020.03 ~ 2020.08] 국가평생진흥교육원 컴퓨터 공학과
* [2009.03 ~ 2015.02] 인하공업전문대학 컴퓨터 정보과

## ETC
* [수행한 프로젝트 전체 목록](https://jaenyeong.github.io/projects)
* [수강한 강의 전체 목록](https://jaenyeong.github.io/learns/)