---
date: '2026-02-22'
description: Aspose.Email for Java를 사용하여 Outlook에서 팔로우업 플래그를 설정하는 방법을 배우고, 플래그 설정,
  읽기 및 수신자에 대한 플래그 제거를 포함합니다.
keywords:
- Manage Outlook follow-up flags
- Set follow-up flags in Outlook with Aspose.Email for Java
- Integrate email task management with Aspose.Email
title: Aspose.Email for Java를 사용하여 Outlook 팔로업 플래그 설정 방법
url: /ko/java/calendar-appointments/aspose-email-java-outlook-follow-up-flags/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for Java를 사용하여 Outlook Follow Up Flag 설정 방법

## 소개
중요한 이메일을 추적하는 데 어려움을 겪어본 적이 있다면 Outlook의 **outlook follow up flag**가 얼마나 유용한지 아실 겁니다. 이 가이드에서는 Aspose.Email for Java를 사용하여 프로그래밍 방식으로 **outlook follow up flag를 설정하는 방법**을 보여주고, **수신자를 위한 outlook follow up flag 설정** 및 작업이 완료되었을 때 **outlook follow up flag를 제거하는 방법**도 다룹니다. 끝까지 읽으면 Java 코드에서 작업 추적, 알림 및 감사 로그를 자동화할 수 있게 됩니다.

**배울 내용**
- Outlook 메시지에 follow‑up flag를 생성하고 적용하기.  
- 특정 수신자를 위한 follow‑up flag 설정하기.  
- flag를 완료된 상태로 표시하고 나중에 제거하기.  
- 보고 또는 규정 준수를 위해 flag 옵션 읽기.  

코드에 들어가기 전에 환경을 준비합시다.

## 빠른 답변
- **“how to set follow‑up”가 의미하는 바는?** Outlook 항목에 시작일, 알림 및 마감일이 포함된 flag를 추가하는 것입니다.  
- **필요한 라이브러리는?** Aspose.Email for Java (v25.4 이상).  
- **라이선스가 필요합니까?** 예, 전체 기능을 사용하려면 체험판 또는 구매 라이선스가 필요합니다.  
- **수신자 전용 flag를 설정할 수 있나요?** 물론입니다 – `FollowUpManager.setFlagForRecipients`를 사용하세요.  
- **나중에 flag를 제거할 수 있나요?** 예, `FollowUpManager.clearFlag`를 호출하면 됩니다.

## Outlook Follow Up Flag란?
Outlook follow up flag는 시작일, 알림 및 마감일을 메일 항목에 첨부할 수 있는 내장 작업 표시기로, 일반 이메일을 추적 가능한 작업 항목으로 변환하여 팀이 보류 중인 작업을 놓치지 않도록 도와줍니다.

## 왜 Aspose.Email for Java를 사용하나요?
Aspose.Email은 Outlook이 설치되지 않은 환경에서도 작동하는 순수 Java API를 제공하므로, .msg 파일을 조작하고 flag를 설정하며 작업을 관리할 수 있어 **automate outlook tasks**, 백엔드 서비스 또는 프로젝트‑관리 도구와의 통합에 이상적입니다.

## 전제 조건
- **Aspose.Email for Java** 버전 25.4 이상 (또는 **aspose email java**).  
- **JDK 16+**가 설치되어 있어야 합니다.  
- Maven 호환 IDE (IntelliJ IDEA, Eclipse 등).  
- 기본 Java 지식 및 이메일 개념에 대한 이해.

## Aspose.Email for Java 설정
### Maven 구성
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이선스 획득
Aspose.Email은 프로덕션 사용을 위해 라이선스가 필요합니다:

- **무료 체험** – 30일 평가.  
- **임시 라이선스** – 연장 테스트.  
- **정식 라이선스** – 영구 구독.

Initialize the license before any email operation:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## Outlook Follow Up Flag 설정 (기능 1)
### 단계 1: 메시지 생성 및 초기화
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*먼저 `MailMessage`를 만들고, 발신자/수신자를 설정한 뒤, flag 조작을 위해 `MapiMessage`로 변환합니다.*

### 단계 2: Follow‑Up 날짜 정의 (Outlook Flag 알림)
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*여기서는 `Calendar` 클래스를 사용해 시작일, 알림(**outlook flag reminder**) 및 마감일을 설정합니다.*

### 단계 3: Follow‑Up 옵션 적용
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions` 객체에 모든 flag 세부 정보가 들어 있으며, 이를 `FollowUpManager.setOptions`로 적용합니다.*

### 단계 4: 메시지 저장
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*flag가 첨부된 상태로 메시지가 `.msg` 파일로 저장됩니다.*

## 수신자를 위한 Flag 설정 방법 (기능 2)
### 개요
때때로 flag가 **수신자에게만** 표시되도록 해야 할 때가 있습니다. 이 예제에서는 먼저 메시지를 초안으로 표시한 다음 flag를 추가합니다.

#### 단계 1: 초안으로 표시
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*메시지를 전송되지 않은 상태로 표시하면 Outlook이 초안으로 인식합니다.*

#### 단계 2: 수신자 Flag 설정
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*이제 flag가 수신자에게만 보이며, 전형적인 **flag for recipients** 시나리오입니다.*

## Outlook Follow Up Flag를 완료된 상태로 표시하는 방법 (기능 3)
### 단계 1: 메시지 로드
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

### 단계 2: 완료된 상태로 표시하고 저장
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*flag 상태가 “Completed”로 변경되고 업데이트된 파일이 저장됩니다.*

## Outlook Follow Up Flag 제거 방법 (기능 4)
### 단계 1: 로드하고 Flag 제거
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*flag가 없는 상태로 메시지가 저장됩니다.*

## Flag 옵션 읽는 방법 (기능 5)
### 단계 1: 옵션 가져오기
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*`options` 객체에 이제 시작일, 마감일, 알림 날짜와 flag 제목이 포함되어 있어, **read flag options**가 필요할 때 보고에 유용합니다.*

## 실용적인 적용 사례
- **Task‑Management Integration:** 플래그가 달린 이메일을 Jira, Trello, Azure Boards와 동기화.  
- **Automated Reminders:** 보류 중인 follow‑up에 대한 일일 알림 이메일 생성.  
- **Compliance Audits:** 규제 보고를 위해 flag 데이터를 내보내기.

## 성능 고려 사항
- **Date Calculations:** 루프 내부가 아니라 배치당 한 번 날짜를 계산합니다.  
- **Resource Management:** 메시지를 저장한 후 모든 스트림이나 파일 핸들을 닫습니다.  
- **Memory Usage:** 대용량 메일함을 청크 단위로 처리해 힙 압력을 피합니다.

## 일반적인 문제와 해결책
| Issue | Cause | Fix |
|-------|-------|-----|
| Outlook에 flag가 표시되지 않음 | Message가 적절한 `MessageFlags` 없이 저장됨 | 수신자 flag 적용 전에 `setMessageFlags`를 `MSGFLAG_UNSENT`로 설정하세요. |
| Save가 `AccessDeniedException`을 발생시킴 | 잘못된 파일 경로 또는 쓰기 권한 없음 | 출력 디렉터리가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하세요. |
| 날짜가 하루 차이 | 시간대 불일치 | `TimeZone.getTimeZone("GMT")` 또는 로컬 시간대를 일관되게 사용하세요. |

## 자주 묻는 질문
**Q: Aspose.Email for Java란 무엇인가요?**  
A: Outlook이 설치되지 않아도 이메일 파일(MSG, EML 등)을 생성, 읽기 및 조작할 수 있는 순수 Java API입니다.

**Q: 무료 체험 라이선스는 어떻게 얻나요?**  
A: [Aspose 웹사이트](https://releases.aspose.com/email/java/)를 방문하여 30일 체험판을 다운로드하세요.

**Q: 하나의 메시지에 여러 개의 follow‑up flag를 설정할 수 있나요?**  
A: Outlook은 메시지당 하나의 flag만 지원하지만, 추가 작업 데이터를 사용자 정의 MAPI 속성에 저장할 수 있습니다.

**Q: flag를 설정한 후 메시지가 저장되지 않습니다. 무엇을 확인해야 하나요?**  
A: `outputDir` 경로가 유효하고 해당 위치에 쓰기 권한이 있는지 확인하세요.

**Q: 여러 메시지에서 한 번에 flag를 제거하려면 어떻게 해야 하나요?**  
A: 메시지 컬렉션을 순회하면서 각 `MapiMessage`에 `FollowUpManager.clearFlag`를 호출하세요.

## 리소스
- [Documentation](https://reference.aspose.com/email/java/)
- [Download Aspose.Email for Java](https://releases.aspose.com/email/java/)
- [Aspose.Email Free Trial](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Email for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}