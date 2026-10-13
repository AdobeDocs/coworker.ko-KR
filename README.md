---
source-git-commit: e5bf2a0a2ee55513b32442f70d01dc5825ac9d6a
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# CX Enterprise Coworker 설명서

Adobe CX Enterprise Coworker 설명서 세트에 대한 Source.

## 구성 게시 중

`.github/workflows/`에서 공유 문서 유효성 검사 및 미러링 워크플로를 사용합니다.
가져오기 요청에 대해 유효성 검사 워크플로우가 실행되고 `main`(으)로 푸시합니다.
미러링 워크플로우는 `main`에 푸시할 때 실행됩니다.

Markdown 규칙 무시에는 `markdownlint_custom.json`을(를) 사용하고 URL 제외에는 `linkcheckexclude.json`을(를) 사용합니다.
`pipeline.opts` 파일이 `cx-enterprise-ai.en`의 링크 검사 구성을 따릅니다.
`source,dest` 열을 사용하여 `redirects.csv`(으)로 URL 리디렉션을 추가합니다.
