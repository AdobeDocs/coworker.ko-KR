---
title: Coworker를 사용하여 Adobe Content Analytics 구현 계획
description: Adobe CX Enterprise Coworker의 ACA 구현 안내서에서 맞춤화된 Adobe Content Analytics 구현 계획을 만드는 방법을 알아봅니다.
feature: AI Tools
role: Admin, User
level: Intermediate
doc-type: Feature Video
duration: 00:04:12
last-substantial-update: 2026-11-20T00:00:00.000Z
jira: KT-23165
autotag-review: '2026-11-20T18:22:53.302Z'
TQID: 'https://experienceleague.adobe.com/qi-9yx9JCMrLNmHdTH8iMsFfvRmGK3k7OVRb-w0gS5U'
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4c82db341547bf3009009a3fea4a88e294ce6c24
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%
---

# Adobe Content Analytics 구현 계획

기존 ACA(CJA) 배포에 Content Analytics을 추가하든 아니면 독립 실행형 설정으로 시작하든 관계없이 CX Enterprise Coworker의 Customer Journey Analytics 구현 안내서에서 맞춤화된 Adobe Content Analytics 구현 계획을 만드는 방법을 알아봅니다.

## 배울 내용

- Coworker가 가이드 검색 프로세스를 사용하여 라이센싱, 채널, SDK, 행동 데이터, ID 결합, 개인정보 보호 및 보고 요구 사항을 캡처하는 방법입니다.
- 안내서에서 구현 단계 시퀀스, 소유자 할당, 종속성 식별 및 중요 경로 타임라인을 추정하는 방법입니다.
- 기존 CJA 배포와 독립 실행형 Content Analytics 구현 간 계획이 어떻게 다른지 설명합니다.
- 진행 상황을 추적하고 가정을 수정하고 구현 작업을 CSV 및 Jira로 내보내는 방법입니다.

>[!VIDEO](https://video.tv.adobe.com/v/3508620/?learn=on&enablevpops)

## 기존 CJA 배포에 Content Analytics 추가

첫 번째 연습은 웹 및 모바일에서 이미 CJA을 사용하는 조직부터 시작됩니다. Adobe 태그 및 Web SDK은 웹 사이트를 지원하고, Mobile SDK은 앱을 지원하며, CJA 연결, 데이터 보기 및 데이터 스트림이 이미 있습니다.

Coworker는 이러한 답변을 바탕으로 성공적인 구현에 필요한 모든 작업과 구현 팀의 통제 범위를 벗어나는 종속성을 고려하는 계획을 생성합니다.

## 독립 실행형 Content Analytics 시작

두 번째 연습은 기존 CJA 배포 없이 시작됩니다.

Coworker는 Adobe 계정 팀과 행동 데이터 요구 사항 확인 및 웹 행동 데이터에 대한 스키마 및 데이터 세트 생성이 포함된 계획을 생성합니다. 안내식 마법사가 CJA 연결 및 데이터 보기를 만듭니다.

## 진행 상황 추적 및 계획 내보내기

이 비디오에서는 단계를 완료, 다시 열기 또는 지연으로 표시할 수 있는 대화형 1페이지 추적기를 보여 줍니다. 동료는 구현 세부 사항이 변경되고 해당 파일이 재생성될 때 계획을 업데이트할 수 있습니다.

안내서는 다음을 포함한 다른 내보내기 형식을 지원합니다.

- 단계, 노력, 소유자, 종속성 및 상태를 포함하는 **CSV:** 구현 단계입니다.
- **Jira:** 우선 순위 및 스토리 포인트를 포함하여 단계를 epics로, 단계를 스토리로 사용하는 백로그 준비 구조입니다.

## 주요 테이크아웃

Adobe Coworker의 ACA 구현 안내서 는 구현 요구 사항을 순차적이고 실행 가능한 플랜으로 전환합니다. 시작 환경에 적응하고 보안, 개인 정보 및 구성 종속성을 조기에 표시함으로써 팀이 Adobe Content Analytics 롤아웃을 조정하고 추적하는 데 도움이 됩니다.
