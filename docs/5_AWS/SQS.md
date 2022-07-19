---
layout: default
title: SQS
parent: AWS
nav_order: 3
has_children: true
has_toc: true
---

# S3: Simple Queue Service

[Imgur](https://imgur.com/RTCvBR4.png)

안전하고, 지속적인, 가용성있는 Queue를 제공한다.

이걸 사용하면 분산 소프트웨어 시스템과 컴포넌트들을 분리시키거나 통합할 수 있다.

SQS는 dead-letter queues와 cost allocation tags를 제공한다.

또한 AWS SDK가 지원하는 아무 언어를 사용해도 접근가능한 일반화된 웹 서비스 API를 제공한다.

SQS는 standard 형식이나 FIFO 형식의 Queue Type을 제공한다.

# SQS의 이점

1. Security
    
    관리자가 SQS에 메시지를 보내고 SQS로부터 메시지를 받을 사람을 정할 수 있다.
    
2. Durability
    
    SQS는 메시지들을 여러서버에 보관하고
    
    standard queue는 at-least-once message delivery를 지원한다.
    
    FIFO queue는 exactly-once message delivery를 지원한다.
    
3. Availability
    
    메시지의 생산 및 소비의 높은 가용성과 동시성을 위해 redundant infrastructure를 사용한다.
    
4. Scalability
    
    각각의 buffered request를 독립적으로 처리하여, 별도의 프로비저닝없이 로드 증가 및 급증에 대처할 수 있도록 투명하게 확장된다.
    
5. Reliability
    
    메시지가 처리되는 동안 SQS에 고정시키기 때문에, 다수의 producer가 보내고 다수의 유저들이 동시에 메시지를 받을 수 있다.
    
6. Customization
    
    Queue들이 서로 같을 필요는 없다; For Example:
    
    1. queue의 default delay를 설정할 수 있다.
    2. S3나 DynamoDB를 활용해, 구체적으로는 SQS가 S3 객체를 참조하도록 하거나, 다른 방법으로는 큰 용량의 메시지를 여러 개의 작은 메시지로 나눔으로써, 각 메시지의 용량을 256KB 이상으로 사용할 수 있다.

# SQS와 MQ, SNS의 차이점

- 잘 모르는 분야라서 좀 어렵다.

SQS와 SNS는 높은 확장성과 간단한 사용법, message broker세팅이 필요하지 않은 queue와 topic service이다. - 거의 무한한 확장성과 간단한 API를 활용할 수 있는 새로운 어플리케이션 서비스에 추천됨?

MQ는 message broker와 호환할 수 있는 managed message broker service이다.

JMS와 같은 API나 AMQP, MQTT, OpenWire, STOMP와 같은 Protocol에 호환되는 message broker가 있는 어플리케이션을 이주할 때 사용하는 것을 추천한다?

# Queue Type

## Standard

> 빠르지만 정렬되지 않음
> 
- 처리율이 중요할 때

### 무제한 Throughput

1초에 거의 무한한 API 호출을 지원한다.

### At-Least-Once Delivery

하나의 메시지는 적어도 1회 Deliver되지만, 때때로 1개 이상의 메시지 복사본이 Deliver된다.

### Best-Effort Ordering

때때로, 메시지들은 도착한 순서대로 들어오지 않는 경우가 있다.

## FIFO

> 상대적으로 느리지만 Queue의 역할은 충실함
> 
- 이벤트의 순서가 중요할 때

### 높은 처리량

batching을 사용하면 3000 message/sec의 throughput을 가진다.

### Exactly-Once Processing

각 메시지는 큐로 다시 복제되지 않고 단 한번 처리된 며, 소비자가 처리하고 삭제할 때까지 유지된다.

### FIFO Delivery

메시지가 도착 순서대로 받아지는 것이 보장된다.