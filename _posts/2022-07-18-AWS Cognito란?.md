---
layout: post
current: post
cover: assets/images/blog-icon.png
navigation: True
title:  "[AWS] Cognito 란?"
date:  2022-07-14 11:00:00 +0900
tags:  AWS
class: post-template
subclass: 'post tag-fiction'
author: kritias
---
 
# AWS Cognito

## Introduction

![Cognito_Logo.jpeg](_data/asset/images/AWS/Cognito_Logo.jpeg)

Cognito는 웹 및 모바일 앱에 대한 인증, 권한 부여 및 사용자 관리를 제공한다.

유저는 유저 이름과 암호를 사용해 직접 로그인하거나 타사 계정을 연동한 로그인을 할 수 있다.

### 주요 구성 요소

아래 두 서비스는 별도로 사용할 수도 있고, 같이 사용할 수도 있다.

1. 사용자 풀
2. 자격 증명 풀

#### 사용자 풀

- 앱 사용자의 가입 및 로그인 옵션을 제공하는 사용자 디렉터리

#### 자격증명 풀

- 사용자에게 기타 AWS 서비스에 엑세스할 수 있는 권한을 부여한다.

### 주요 시나리오

사용자 인증 후 다른 AWS서비스에 대한 사용자 엑세스 권한을 부여하는 것

1. Cognito User Pool을 이용해 로그인한 뒤, 인증을 완료하고 user pool token을 받는다.
2. Cognito Identity Pool을 이용해 user pool token을 AWS Credential로 변환한다.
3. 유저는 AWS Credential을 이용해 S3나 DynamoDB와 같은 다른 AWS에 접속할 수 있다.