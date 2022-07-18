---
layout: default
title: Lambda
parent: AWS
nav_order: 1
has_children: true
has_toc: true
---

# Lambda
{: .no_toc }

서버를 [Provisioning](https://www.notion.so/Provisioning-98dfc3c7549848a18fb7bfdece06e2f5) 하거나 관리하지 않고도 코드를 실행할 수 있게 해주는 클라우드 컴퓨팅 서비스.

고가용성 컴퓨팅 인프라에서 아래와 같은 거의 모든 컴퓨팅 기능을 수행함

1. 코드 실행
2. 서버와 운영체제 유지 관리
3. 용량 프로비저닝 및 자동 조정
4. 코드 및 보안 패치 배포
5. 코드 모니터링 및 로깅

### 사용

Lambda 함수에 코드를 구성하고, 필요 시에만 함수를 실행하여, 사용한 컴퓨팅 시간만큼 비용을 지불함

Lambda API를 활용해 Lambda 함수를 호출하거나 다른 AWS 서비스의 이벤트에 응답할 수 있다.

예시

1. [`AWS S3`](https://www.notion.so/AWS-S3-5452e294144943b4aa4f942cbb945e65)및 DynamoDB를 위한 데이터 처리 트리거 빌드
2. AWS Kinesis에 저장된 스트리밍 데이터 처리
3. AWS 규모, 성능, 보안으로 작동하는 고유한 백엔드 생성

## 주요 기능

### 동시성 및 크기 조정 컨트롤

### 컨테이너 이미지로 정의된 함수

### 코드 서명

### Lambda Extension

### 함수 블루프린트

### 데이터베이스 엑세스

### 파일시스템 엑세스

## 사전 지식

Linux OS 명령, 프로세스와 스레드, 파일 권한

클라우드, IP 네트워킹 개념

IPC로서의 HTTP, 메시징, 대기열, 알림 및 동시성과 같은 분산 컴퓨팅 이해

보안 서비스 및 개념, AWS IAM 및 엑세스 제어 원칙, AWS KMS 및 퍼블릭 키 인프라

AWS API Gateway, S3, SQS, DynamoDB 서비스

Linux를 이용한 EC2 구성