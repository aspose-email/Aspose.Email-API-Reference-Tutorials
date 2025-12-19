---
date: '2025-12-19'
description: Aspose.Email for Java를 사용하여 Outlook에서 팔로우업 플래그를 설정하는 방법을 배우고, Outlook
  팔로우업 플래그를 효율적으로 설정하고 제거하는 방법을 포함합니다.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Aspose.Email for Java를 사용하여 Outlook에서 팔로우업 플래그 설정 방법
url: /ko/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook에서 Aspose.Email for Java를 사용하여 Follow‑Up 플래그 설정 방법

## Introduction
중요한 메일을 추적하는 데 어려움을 겪어본 적이 있다면 Outlook의 Follow‑up 플래그가 얼마나 유용한지 아실 겁니다. 이 가이드에서는 Aspose.Email for Java를 사용해 **Follow‑up 플래그를 프로그래밍 방식으로 설정하는 방법**을 보여드리고, 수신자에게 **Outlook Follow‑up 플래그를 설정**하는 방법과 작업이 완료되었을 때 **Outlook Follow‑up 플래그를 제거**하는 방법도 다룹니다. 끝까지 읽으시면 Java 코드만으로 작업 추적, 알림, 감사 로그 등을 자동화할 수 있게 됩니다.

**학습 내용**
- Outlook 메시지에 Follow‑up 플래그를 생성하고 적용하기.  
- 특정 수신자에게 Follow‑up 플래그 설정하기.  
- 플래그를 완료 상태로 표시하고 이후에 제거하기.  
- 보고서 또는 규정 준수를 위해 플래그 옵션 읽어오기.  

코드 작성을 시작하기 전에 환경을 준비해 보겠습니다.

## Quick Answers
- **“how to set follow-up”는 무엇을 의미하나요?** 시작일, 알림일, 마감일이 포함된 플래그를 Outlook 항목에 추가하는 것입니다.  
- **필요한 라이브러리는?** Aspose.Email for Java (v25.4 이상).  
- **라이선스가 필요한가요?** 예, 전체 기능을 사용하려면 평가판이든 구매 라이선스든 필요합니다.  
- **수신자 전용 플래그를 설정할 수 있나요?** 물론입니다 – `FollowUpManager.setFlagForRecipients`를 사용하면 됩니다.  
- **나중에 플래그를 제거할 수 있나요?** 예, `FollowUpManager.clearFlag`를 호출하면 됩니다.

## What is a Follow‑Up Flag?
Follow‑Up 플래그는 이메일을 작업으로 표시하고, 선택적으로 시작일, 알림일, 마감일을 첨부할 수 있는 Outlook 기능입니다. 이를 통해 본인과 팀이 보류 중인 작업을 놓치지 않도록 도와줍니다.

## Why use Aspose.Email for Java?
Aspose.Email은 Outlook이 설치되지 않은 환경에서도 순수 Java API로 .msg 파일을 조작하고 플래그를 설정하며 작업을 관리할 수 있게 해줍니다. 백엔드 서비스, 자동화 워크플로, 프로젝트 관리 도구와의 연동에 최적화되어 있습니다.

## Prerequisites
- **Aspose.Email for Java** 버전 25.4 이상.  
- **JDK 16+** 설치.  
- Maven 호환 IDE (IntelliJ IDEA, Eclipse 등).  
- 기본 Java 지식 및 이메일 개념에 대한 이해.

## Setting Up Aspose.Email for Java
### Maven Configuration
`pom.xml`에 다음 의존성을 추가합니다:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition
Aspose.Email은 상용 환경에서 라이선스가 필요합니다:

- **Free trial** – 30일 평가판.  
- **Temporary license** – 연장 테스트용.  
- **Full license** – 영구 구독.

이메일 작업을 수행하기 전에 라이선스를 초기화합니다:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Implementation Guide

### How to Set Follow‑Up Flags (Feature 1)
#### Overview
이 섹션에서는 Outlook 메시지를 생성하고, 시작/알림/마감 날짜를 정의한 뒤 Follow‑up 플래그를 적용하는 과정을 단계별로 안내합니다.

#### Step 1: Create and Initialize the Message
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*먼저 `MailMessage`를 만든 뒤 발신자/수신자를 설정하고, 플래그 조작을 위해 `MapiMessage`로 변환합니다.*

#### Step 2: Define Follow‑Up Dates
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*`Calendar` 클래스를 사용해 시작일, 알림일, 마감일을 설정합니다.*

#### Step 3: Apply Follow‑Up Options
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` 객체에 모든 플래그 세부 정보를 담고, `FollowUpManager.setOptions`로 적용합니다.*

#### Step 4: Save the Message
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*플래그가 포함된 `.msg` 파일로 메시지를 저장합니다.*

### How to Set Outlook Follow‑Up Flag for Recipients (Feature 2)
#### Overview
때때로 플래그를 수신자에게만 표시해야 할 때가 있습니다. 이 예제에서는 메시지를 초안으로 만든 뒤 플래그를 추가합니다.

#### Step 1: Mark as Draft
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*메시지를 전송되지 않은 상태로 표시하면 Outlook이 초안으로 인식합니다.*

#### Step 2: Set Recipient Flag
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*플래그가 이제 수신자에게만 보이게 됩니다.*

### How to Mark an Outlook Follow‑Up Flag as Completed (Feature 3)
#### Overview
작업이 완료되면 프로그래밍 방식으로 플래그를 완료 상태로 표시할 수 있습니다.

#### Step 1: Load the Message
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### Step 2: Mark as Completed and Save
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*플래그 상태가 “Completed”로 변경되고 업데이트된 파일이 저장됩니다.*

### How to Remove Outlook Follow‑Up Flag (Feature 4)
#### Overview
플래그가 더 이상 필요 없을 경우 완전히 제거할 수 있습니다.

#### Step 1: Load and Clear Flag
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*플래그가 없는 상태로 메시지가 저장됩니다.*

### How to Read Follow‑Up Flag Options (Feature 5)
#### Overview
감사 또는 보고를 위해 기존 플래그 설정을 읽어야 할 때가 있습니다.

#### Step 1: Retrieve Options
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` 객체에 시작일, 마감일, 알림일 및 플래그 제목이 포함됩니다.*

## Practical Applications
- **Task‑Management Integration:** 플래그가 지정된 이메일을 Jira, Trello, Azure Boards와 동기화.  
- **Automated Reminders:** 보류 중인 Follow‑up에 대해 매일 알림 메일 자동 생성.  
- **Compliance Audits:** 규제 보고를 위해 플래그 데이터를 내보내기.

## Performance Considerations
- **Date Calculations:** 루프 내부가 아니라 배치당 한 번만 날짜를 계산합니다.  
- **Resource Management:** 메시지를 저장한 후 스트림이나 파일 핸들을 반드시 닫습니다.  
- **Memory Usage:** 대용량 메일함은 청크 단위로 처리해 힙 압력을 최소화합니다.

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| Flag not appearing in Outlook | Message saved without proper `MessageFlags` | Apply `setMessageFlags` with `MSGFLAG_UNSENT` before adding recipient flags. |
| Save throws `AccessDeniedException` | Incorrect file path or missing write permissions | Ensure the output directory exists and the application has write rights. |
| Dates are off by one day | Time‑zone mismatch | Consistently use `TimeZone.getTimeZone("GMT")` or your local zone. |

## Frequently Asked Questions
**Q: What is Aspose.Email for Java?**  
A: Outlook이 설치되지 않아도 이메일 파일(MSG, EML 등)을 생성·읽기·조작할 수 있는 순수 Java API입니다.

**Q: How do I obtain a free trial license?**  
A: [Aspose 웹사이트](https://releases.aspose.com/email/java/)에서 30일 평가판을 다운로드하세요.

**Q: Can I set multiple follow‑up flags on a single message?**  
A: Outlook은 메시지당 하나의 플래그만 지원하지만, 추가 작업 데이터를 사용자 정의 MAPI 속성에 저장할 수 있습니다.

**Q: My message isn’t saved after setting a flag. What should I check?**  
A: `outputDir` 경로가 유효한지, 해당 위치에 쓰기 권한이 있는지 확인하세요.

**Q: How can I remove flags from many messages at once?**  
A: 메시지 컬렉션을 순회하면서 각 `MapiMessage`에 `FollowUpManager.clearFlag`를 호출하면 됩니다.

## Resources
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2025-12-19  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}