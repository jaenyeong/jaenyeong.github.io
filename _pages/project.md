---
layout: single
permalink: /projects/
date: 2021-04-16
title: "지금까지 수행한 모든 프로젝트"
description: ""
subject: blog
toc_label: "All Projects"
toc_icon: "laptop-code"
toc_sticky: true
---

## Career

|  Company     | Working Date      | Period    |
|:------------:|:-----------------:|:---------:|
| 에이치디정션 | 2021.07 ~ 현재    | --------- |
| 스페이스컬쳐 | 2019.09 ~ 2020.01 | 5개월     |
| ADOP         | 2018.09 ~ 2019.09 | 1년       |
| 브이스테이션 | 2018.05 ~ 2018.08 | 3개월     |
| 미림미디어랩 | 2017.04 ~ 2018.01 | 10개월    |
| 진코퍼레이션 | 2015.02 ~ 2016.07 | 1년 6개월 |

## 스페이스컬쳐

### 공간기록 (가구 인테리어 디자인 플랫폼) 개발
(2019.09 ~ 2020.01) 5개월

> **설명**
> * 오늘의집 앱을 벤치마킹한 가구 제품 거래 서비스 개발
> * 인테리어 디자이너가 고객에게 인테리어를 제안하며 제품을 추천하는 플랫폼
>
> **담당 업무**
> * TDD를 활용해 REST API 서버 개발
>   * Bootpay API를 활용하여 결제 검증, 취소 기능 개발
>   * FireStore(구글 실시간 DB)에 채팅 데이터 보관 처리
>   * 그 외 카트, 상품, 주문 등 주요 기능 CRUD API 개발 및 단위 테스트 작성
>   * 서버 내부 구조 리팩터링
> * AWS 인프라 구축, 운영(비용 관리)
> * DB 스키마 설계
> * Spring Boot Log, DB 등 초기 설정
> 
> **사용 기술**
> * Java(Spring Boot), MyBatis, Gradle, JUnit
> * AWS(EC2, RDS-Aurora)
> * Bitbucket
> * Bootpay API, FireStore

---

## ADOP

### Portal (인사 관리 시스템) 유지보수
(2019.08 ~ 2019.08) 1개월

> **설명**
> * 복지비, 휴가 등을 처리하는 사내 인사 관리 시스템 유지보수
> 
> **담당 업무**
> * AWS S3 SDK를 활용하여 전자 결재 시 영수증 파일 업로드 기능 수정
> * 직원별 연차에 따라 휴가 일수를 다르게 처리하는 기능 버그 수정
>
> **사용 기술**
> * PHP(CI), AWS(EC2, RDS-Aurora, S3), JavaScript(jQuery)

---

### Insight (광고 수익 정산 서비스) 유지보수
(2019.04 ~ 2019.07) 4개월

> **설명**
> * 광고 수익 정산 관리를 위한 사내 서비스 유지보수, 운영
>
> **담당 업무**
> * 신규 기능 추가, 기존 기능 버그 수정
>   * 국가별 환율에 따라 부가세 계산, 매체별 배분율 계산 등 수익 정산 기능 유지보수
>   * 정산 이월, 지급일 변경, 메일 전송 등 기능 유지보수
>   * 광고 수익 데이터 파일 업로드 기능 구현
>   * 기능별 중복 코드 리팩터링을 통해 구조 개선 및 쿼리 튜닝
> * DB 서버의 AWS RDS 스케일 업 (r4 > r5), S3 백업 기능 설정
>
> **사용 기술**
> * Java(Spring Boot), MyBatis, Gradle, JavaScript(jQuery)
> * AWS(EC2, RDS-Aurora, ACM)
> * Bitbucket, Jenkins

---

### AWS 관리
(2019.02 ~ 2019.03) 2개월

> **설명**
> * 사내 서비스의 AWS 인스턴스 리소스(트래픽, CPU 사용량 등) 모니터링, 비용 최적화
>
> **담당 업무**
> * 사용되는 AWS 인스턴스 리소스를 AWS CloudWatch 콘솔을 통해 모니터링, 장애 대응
>   * 특정 서비스의 트래픽 부하로 스케일링 그룹 AZ의 리소스 부족으로 스케일 아웃 실패
>   * AMI로 다른 AZ의 인스턴스 직접 생성하여 로드밸런서에 연결하여 대응
>   * 스케일링 그룹의 다른 AZ를 추가하여 향후 장애 방지
> * 사용되지 않는 서비스 모듈 약 10개 정리
> * 메가존 빌링 서비스를 사용하여 AWS 인스턴스 비용 관리, 최적화
>   * 사용되지 않는 서비스 모듈 및 AWS 리소스 정리, 인스턴스의 유형을 변경하여 유지 비용 절감
> * 비용 절감 목적으로 SpotInst(베스핀 기업의 스팟인스턴스 관리 서비스) 사용 테스트
>   * 해당 서비스의 불안정한 상태 때문에 적용 실패
>
> **사용 기술**
> * EC2(AMI, ELB, Auto Scaling), RDS(Aurora), CloudWatch, CloudFront, IAM

---

### AMP 변환 서비스 개발
(2018.09 ~ 2019.01) 5개월

> **설명**
> * AMP(Accelerated Mobile Pages)는 일반 페이지보다 빠른 속도로 렌더링 되는 페이지
> * 변환 모듈 개발, AMP 서버 유지보수 (광고 삽입하여 수익 창출)
>
> **담당 업무**
> * 고객사(매체)가 제공하는 RSS를 AMP 데이터로 변환하는 모듈 개발
>   * Jsoup를 사용하여 크롤링 구현, 리눅스 crontab으로 반복 실행 처리
>   * Bitbucket(web hook)과 Jenkins(execute shell)를 사용하여 배포 자동화
> * AMP 퍼블리싱 서버 유지보수
>   * 매체별 규격에 맞춰 AMP 유효성 확인, AMP(+AMP Story) 템플릿 수정
>   * 각 기사 페이지 CDN(AWS CloudFront) 적용하여 렌더링 속도 개선
>   * 구글 SEO(Search Engine Optimization) 가이드 적용, 문서화
>     * 구글 검색시 AMP가 상단에 노출이 되면서 요청 트래픽이 발생하여 광고 수익 창출
> * 비슷한 유형의 크롤러 모듈 약 6개 병합, 소스 형상관리 및 배포 측면에서 관리 포인트 축소
>   * 이로 인해 사용하지 않게된 AWS EC2 인스턴스 약 3개 삭제, 월 기준 약 $200 절감 효과
>
> **사용 기술**
> * Java, Jsoup, MyBatis, Gradle, JavaScript(Vue.js), PHP(CI)
> * AWS(EC2, RDS-Aurora, CloudFront)
> * Bitbucket, Jenkins

---

## 브이스테이션

### SSO (통합 아이디) 개발
(2018.05 ~ 2015.08) 3개월

> **설명**
> * 여러 개의 해외 직구 쇼핑몰 서비스 간 SSO (Single Sign On) 기능 설계
> 
> **담당 업무**
> * DB 스키마 설계
> * Oauth2.0 기준으로 인증 프로세스 설계, Resource 서버 구현
>
> **사용 기술**
> * PHP(CI), JavaScript(Node.JS), AWS(EC2, RDS-PostgreSQL)

---

## 미림미디어랩

### 미디어박스 (콘텐츠 동영상 재생 플랫폼) 개발
(2017.04 ~ 2018.01) 10개월

> **설명**
> * 유튜브 앱을 벤치마킹한 콘텐츠 동영상 재생 플랫폼 서비스 개발
> * 사용자가 선택한 시나리오 진행에 따라 다른 영상이 재생되는 플랫폼
>
> **담당 업무**
> * Ionic을 사용해 하이브리드 앱 개발
>   * 채널, 시청 기록, 구독, 코멘트 등 각 화면 구현 및 데이터 핸들링(렌더링)
> * REST API 서버 개발
>   * 채널, 시청 기록, 구독, 코멘트 등 각 기능 CRUD API 구현
>   * ehCache 라이브러리를 사용하여 영상 데이터 캐싱 처리하여 불필요한 API 호출 개선
> * Spring Boot Log, DB 등 초기 설정
> * DB 스키마 설계
>
> **사용 기술**
> * Java(Spring Boot), MyBatis, Gradle, TypeScript(Ionic)
> * AWS(EC2, RDS-PostgreSQL)
> * Vimeo(동영상 파일 서버) API

---

## 진코퍼레이션

### 아모레퍼시픽 오산 물류센터 B2B 관리 시스템 관리
(2016.06 ~ 2016.07) 2개월

> **설명**
> * B2B 관리 시스템 유지 보수
> 
> **담당 업무**
> * 엑셀파일 업로드 기능 구현, 데이터 운송장 출력 기능 구현
>
> **사용 기술**
> * PowerBuilder, Oracle

---

### 아모레퍼시픽 김천 물류센터 B2C 시스템 개발
(2015.12 ~ 2016.05) 6개월

> **설명**
> * B2C(Business-to-Customer) 검품 프로그램 개발
>
> **담당 업무**
> * 검품 프로그램 개발
>   * RS232, RS485 시리얼 통신으로 저울, 스캐너, 프린터 등 장비 통신 기능 구현
>   * 피킹 제품 일치 여부 확인, 배송 정보 조회, 운송장 출력 등 기능 구현
> * 현장 통합 테스트 진행
>
> **사용 기술**
> * VB6, Oracle, MS Access
> 
> **기타**
> * 6개월 간 장기 출장 (경북 김천 상주)

---

### 아모레퍼시픽 오산 물류센터 PCS 유지보수
(2015.08 ~ 2015.11) 4개월

> **설명**
> * PCS(Picking Cart System) 유지보수
> 
> **담당 업무**
> * 피킹 프로세스 변경 및 운송장, 주문 내역서 등 출력 데이터, 포맷 변경
> * 제품과 랙 위치 레이아웃 등 화면 변경
>
> **사용 기술**
> * VB6, Oracle, MS Access

---

### 아모레퍼시픽 TMS 배송 앱 유지보수
(2015.07 ~ 2015.07) 1개월

> **설명**
> * TMS(Transport Management System) 내에 제품 배송 시 사용되는 배송 앱 유지보수
> 
> **담당 업무**
> * 앱 문자 송신 기능 버그 수정, 메시지 내용 변경
>
> **사용 기술**
> * Java(Android)

---

### 아모레퍼시픽 미국 물류센터 B2B 시스템 개발
(2015.03 ~ 2016.06) 4개월

> **설명**
> * B2B(Business-to-Business) 검품, 카트 피킹 프로그램 개발
> 
> **담당 업무**
> * 검품 프로그램 개발
>   * 피킹 제품 일치 여부 확인, 배송 정보 조회, 운송장 출력 등 기능 구현
> * 카트 피킹 프로그램 유지보수
>   * 제품 조회, 피킹 처리 기능 수정
> * 현장 통합 테스트 진행
>
> **사용 기술**
> * VB6, C#, Oracle, MS Access
> 
> **기타**
> * 1개월 간 해외 출장 (미국 LA)

---

### 아모레퍼시픽 BMS 시스템 개선
(2015.02 ~ 2015.02) 1개월

> **설명**
> * BMS(Buy-Move-Sell) 자재 입출고 관리 시스템 기능 추가
> 
> **담당 업무**
> * 자재 조회 및 입출고 기능 개발
>
> **사용 기술**
> * Java(Spring-JSP), Oracle
