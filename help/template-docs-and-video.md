---
# TEMPLATE ONLY. Delete this line and the "hide" line below when you copy this file.
hide: true

# TITLE AND DESCRIPTION (shared)
# Title: title case, 60 characters or fewer.
# Description: one or two sentences, about 150-160 characters. Start with "Learn how to..." for tasks or "Learn about..." for concepts.
title: 제목 사례 페이지 제목
description: Adobe CX Enterprise Coworker으로 [작업을 수행]하는 방법에 대해 알아봅니다. [작업을 초대하는 두 번째 문장.]

# VIDEO TEAM FIELDS (owned by the video team)
# Remove all four lines if the page has no video.
doc-type: Feature Video
duration: 180
last-substantial-update: 2026-01-01T00:00:00.000Z
jira: KT-00000

# DOCUMENTATION FIELDS (owned by the documentation team)
role: User
level: Beginner
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 951c534c04e9d431b4db71e3d999685629821194
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%
---
<!--
TEMPLATE GUIDANCE. Delete this comment block before you commit a new page.

PURPOSE
Use this layout when one page presents both a video and written documentation.
If a page is documentation only or video only, you do not need this template.

THE ONE RULE
Every H2 section has exactly one owner: Documentation or Video. Each section
starts with an "Owner" comment. Keep those comments in the finished page. Edit
only the sections you own. If you need a change in the other team's section,
ask the owner or leave a comment on the pull request.

HOW TO USE THIS FILE
1. Copy this file into the folder for your topic. Use a descriptive, lowercase,
   hyphenated file name, for example manage-data-lake-retention.md.
2. Delete the two "TEMPLATE ONLY" lines in the front matter.
3. Replace everything in [brackets]. Delete any section you do not need.
4. Keep the section order: intro, video, then documentation.
5. Add a TOC entry for the page, if it is meant to appear in the table of contents.

KEEPING CONTENT FROM BEING OVERWRITTEN
- Do not embed the video inside a documentation section, and do not put steps
  inside the video section. Keep each format under its own heading.
- Give every H2 an explicit anchor, such as {#before-you-begin}, so links stay
  stable when a heading is reworded.
- Make the documentation complete without the video. Steps must work for a reader
  who never presses play (accessibility, search, and localization depend on it).
- Do not restate the steps in the video summary. Summarize what the video shows.
- Updating the video (new video ID, new duration) changes the video section and
  the video fields in the front matter only. Updating the steps changes the
  documentation sections only. Make each kind of change in its own commit.
- Each team edits its own front matter fields (see the comments above).
-->

# 문장의 경우 페이지 제목 {#page-id}

<!-- Owner: Documentation -->

[독자가 무엇을 할 수 있고 왜 그것이 중요한지 나타내는 한두 문장입니다. 메모, 목록 또는 경고로 페이지를 시작하지 마십시오.]

## 비디오 보기 {#watch-the-video}

<!-- Owner: Video. Documentation: do not edit this section. -->

[비디오에 표시되는 내용과 재생 대상을 나타내는 한두 문장입니다.]

<!--
Replace VIDEO_ID with the ID from the video team, and remove this comment wrapper.
Add {transcript=true} after the closing parenthesis if a transcript is available.

>[!VIDEO](https://video.tv.adobe.com/v/VIDEO_ID?learn=on)
-->

[선택 사항: 비디오에서 다루지 않는 내용이나 표시되는 인터페이스 버전에 대한 참고 사항.]

## 시작하기에 앞서 {#before-you-begin}

<!-- Owner: Documentation -->

[읽기 전에 독자에게 필요한 권한, 라이선스, 응용 프로그램이나 샌드박스에 대한 액세스 권한 또는 관련 페이지를 먼저 표시합니다. 필수 구성 요소가 적용되지 않으면 이 섹션을 삭제합니다.]

* [필수 구성 요소 1.]
* [필수 구성 요소 2.]

## [명령형 동사를 사용하는 작업 제목] {#task-heading}

<!-- Owner: Documentation -->

[작업을 소개하거나 작업이 종속된 개념을 설명하는 한 문장입니다.]

1. [동작을 사용하여 각 단계를 시작하고 마침표로 끝냅니다.]
1. [굵게 인터페이스 레이블(예: **[!UICONTROL 보내기]**]
1. [각 단계를 세 번의 클릭 또는 결정으로 유지합니다.]

   [인터페이스를 표시하는 단계 뒤에 있는 줄의 선택적 스크린샷입니다. 표시된 목표 또는 기능을 설명하는 대체 텍스트가 있는 Markdown 이미지 구문을 사용하십시오.]

1. [마지막 단계.]

### [선택적 하위 작업 또는 옵션 제목] {#subtask-heading}

<!-- Owner: Documentation -->

[H2에 둘 이상의 부분이 있는 경우에만 H3을 사용하십시오.]

## 프롬프트 예 {#example-prompts}

<!-- Owner: Documentation. Delete this section if it does not apply. -->

* &quot;[독자가 복사하고 조정할 수 있도록 메시지를 표시합니다.]&quot;
* &quot;[다른 프롬프트.]&quot;

## 문제 해결 {#troubleshooting}

<!-- Owner: Documentation. Delete this section if it does not apply. -->

[독자가 볼 수 있는 문제를 설명한 다음 해결 방법을 설명합니다.]

## 이 항목에 대한 추가 도움말 {#more-help}

<!-- Owner: Documentation -->

* [대상 페이지를 설명하는 링크 텍스트]
* [다른 대상 페이지를 설명하는 링크 텍스트]
