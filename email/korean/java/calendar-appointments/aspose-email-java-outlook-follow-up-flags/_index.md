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
# Outlook에서 Aspose.Email for Java를 사용하여 후속 플래그 설정 방법

## 소개
중요한 메일을 추적하는 데 어려움을 겪어본 적이 있다면 Outlook의 후속 조치가 어떻게 사용할 수 있는지 아실 것입니다. 이 가이드에서는 Aspose.Email for Java를 다루기 **Follow-up 표시를 프로그래밍 방식으로 설정하는 방법**을 보여주기, 수신자에게 **Outlook Follow-up 표기를 설정**하는 방법 작업과 이하기 때문에 **Outlook Follow-up 표시를 제거**하는 방법을 다뤄야 합니다. Java로 작업 추적, 알림, 감사 표시 등을 할 수 있도록 하면 됩니다.

**학습 내용**
- Outlook 메시지에 후속 알림을 생성하고 적용하기.
- 특정 수신자에게 후속 등록 등록을 설정합니다.
- 신고를 완료한 상태로 표시하고 이후에 제거하기.
- 규정 준수를 위해 플래그 옵션을 읽어주세요.

코드 작성을 시작하기 전에 환경을 준비했습니다.

## 빠른 답변
- **“후속 조치 설정 방법”은 무엇을 의미합니까?** 시작일, 알림일, 날짜가 포함된 플래그를 Outlook 항목에 추가하는 것입니다.
- **필요한 라이브러리는?** Aspose.Email for Java (v25.4 이상).
- **라이선스가 필요한가요?** 예를 들어, 전체 기능을 사용하려면 평가판이든 구매가 필요합니다.
- **수신자 승리로 환영받을 수 있나요?** 물론입니다 – `FollowUpManager.setFlagForRecipients`를 사용하면 됩니다.
- **나중에 등록을 취소할 수 있나요?** 예, `FollowUpManager.clearFlag`를 호출하면 됩니다.

## 후속 플래그란 무엇입니까?
후속 조치 알림은 이메일을 작업으로 표시하고, 선택적으로 시작일, 알림일, 종료일을 첨부할 수 있는 Outlook 기능입니다. 그 사이에 내부자와 팀이 함께 존재하도록 허용합니다.

## Java용 Aspose.Email을 사용하는 이유는 무엇입니까?
Aspose.Email은 Outlook이 설치되지 않은 환경에서도 순수 Java API로 .msg 파일을 수락하고 플래그를 설정하여 작업을 관리할 수 있게 되었습니다. 백엔드 서비스, 자동화 작업플로, 프로젝트 관리 도구와의 작업에 최적화되어 있습니다.

## 전제 조건
- **Aspose.Email for Java** 버전 25.4이상.
- **JDK16+** 설치.
- Maven 호환 IDE(IntelliJ IDEA, Eclipse 등).
- 기본적으로 Java 지식과 이메일 개념에 대한 이해.

## Java용 Aspose.Email 설정
### 메이븐 구성
`pom.xml`에 다음 의존성을 추가합니다:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이선스 취득
Aspose.Email은 기기의 위상이 필요합니다:

- **무료 평가판** – 30일 평가판.
- **임시 라이센스** – 연장 테스트용.
- **정규 라이센스** – 영구 가입.

이메일로 작업을 수행하기 위한 활동을 합니다:

```java
License license = new License();
license.setLicense("path/to/Aspose.Total.Java.lic");
```

## 구현 가이드

### 후속 플래그를 설정하는 방법(기능 1)
#### 개요
이 섹션에서는 Outlook 메시지를 생성하고, 시작/알림/마감 날짜를 정의한 뒤에 후속 조치를 기념하는 과정을 완료하는 동안 안내합니다.

#### 1단계: 메시지 생성 및 초기화
```java
MailMessage mailMsg = new MailMessage();
mailMsg.setSender(new MailAddress("AETest12@gmail.com"));
mailMsg.getTo().addMailAddress(new MailAddress("receiver@gmail.com"));
mailMsg.setBody("This message will test if follow up options can be added to a new mapi message.");
MapiMessage mapi = MapiMessage.fromMailMessage(mailMsg);
```
*먼저 `MailMessage`를 만든 뒤 발신자/수신자를 설정하고, 플래그 조작을 위해 `MapiMessage`로 변환합니다.*

#### 2단계: 후속 조치 날짜 정의

```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 14, 40, 0);
Date dtStartDate = calendar.getTime();
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
calendar.add(Calendar.DATE, 1);
Date dtDueDate = calendar.getTime();
```
*`Calendar` 클래스를 실행 시작일, 알림일, 종료일을 설정합니다.*

#### 3단계: 후속 조치 옵션 적용
```java
FollowUpOptions options = new FollowUpOptions("Follow Up", dtStartDate, dtDueDate, dtReminderDate);
FollowUpManager.setOptions(mapi, options);
```
*`FollowUpOptions`에 모든 공식 세부 정보를 포함, `FollowUpManager.setOptions`로 적용합니다.*

#### 4단계: 메시지 저장
```java
mapi.save(outputDir + "SetFollowUpflag_out.msg");
```
*플래그가 포함된 `.msg` 파일로메시지를 저장합니다.*

### 수신자에 대한 Outlook 후속 조치 플래그를 설정하는 방법(기능2)
#### 개요
기념일을 수신자에게 표시해야 할 때가 있습니다. 이 예제에서는 메시지를 초안으로 만든 후 축하를 추가합니다.

#### 1단계: 초안으로 표시
```java
mapi.setMessageFlags(MapiMessageFlags.MSGFLAG_UNSENT);
```
*메시지를 전송하지 않은 상태로 표시하면 Outlook이 초안으로 인식됩니다.*

#### 2단계: 수신자 플래그 설정
```java
Calendar calendar = Calendar.getInstance(TimeZone.getTimeZone("GMT"));
calendar.set(2013, Calendar.MAY, 16, 16, 40, 0);
Date dtReminderDate = calendar.getTime();
FollowUpManager.setFlagForRecipients(mapi, "Follow up", dtReminderDate);
```
*플래그가 이제 수신자에게만 확인됩니다.*

### Outlook 후속 작업 플래그를 완료됨으로 표시하는 방법(기능 3)
#### 개요
작업이 완료되면 플래그를 표시할 수 있습니다.

#### 1단계: 메시지 로드
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
```

#### 2단계: 완료로 표시하고 저장
```java
FollowUpManager.markAsCompleted(mapi);
mapi.save(outputDir + "MarkedCompleted_out.msg");
```
*플래그 상태가 "완료"로 변경되고 업데이트된 파일이 저장됩니다.*

### Outlook 후속 작업 플래그를 제거하는 방법(Feature4)
#### 개요
플래그가 더 이상 필요하지 않은 경우 완전히 제거할 수 있습니다.

#### 1단계: 플래그 로드 및 지우기
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpManager.clearFlag(mapi);
mapi.save(outputDir + "FollowUpFlagRemoved_out.msg");
```
*플래그가 없는 상태로 메시지가 저장됩니다.*

### 후속 플래그 옵션을 읽는 방법(Feature5)
#### 개요
또는 보고를 위해 축하 메시지를 작성해 주시기 바랍니다.

#### 1단계: 검색 옵션
```java
MapiMessage mapi = MapiMessage.fromFile(dataDir + "message.msg");
FollowUpOptions options = FollowUpManager.getOptions(mapi);
```
*'옵션'에 시작일, 종료일, 알림일 및 명칭 지정이 포함됩니다.*

## 실제 적용
- **작업 관리 통합:** 명시가 이메일을 Jira, Trello, Azure Boards로 지정했습니다.
- **자동 알림:** 정말 후속 조치에 대해 매일 알림 메일 자동 생성.
- **규정 준수 감사:** 표시를 위해 선언 데이터를 포함합니다.

## 성능 고려 사항
- **날짜 계산:** 루프 내부가 아니라 배치당 한 번만 데이트를 합니다.
- **자원 관리:** 메시지를 저장한 후 스트림이나 파일 핸들을 닫습니다.
- **메모리 사용량:** 대표 메일함은 청크 단위로 처리해 힙 압력을 알려드립니다.

## 일반적인 문제 및 해결 방법
| 이슈 | 원인 | 수정 |
|-------|-------|------|
| Outlook에 플래그가 표시되지 않음 | 적절한 `MessageFlags` 없이 메시지가 저장됨 | 수신자 플래그를 추가하기 전에 `MSGFLAG_UNSENT`와 함께 `setMessageFlags`를 적용하세요. |
| 저장 시 `AccessDeniedException` 발생 | 잘못된 파일 경로 또는 쓰기 권한 누락 | 출력 디렉터리가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하세요. |
| 날짜가 하루씩 틀렸습니다 | 시간대 불일치 | `TimeZone.getTimeZone("GMT")` 또는 로컬 영역을 일관되게 사용하세요. |

## 자주 묻는 질문
**Q: Java용 Aspose.Email이 무엇인가요?**
A: Outlook이 포함된 파일 파일(MSG, EML 등)을 생성·읽기·조작할 수 있는 순수 Java API입니다.

**Q: 무료 평가판 라이센스를 얻으려면 어떻게 해야 합니까?**
A: [Aspose 웹사이트](https://releases.aspose.com/email/java/)에서 30일 평가판을 다운로드하세요.

**Q: 단일 메시지에 여러 후속 조치 플래그를 설정할 수 있나요?**
A: Outlook은 메시지당 하나의 플래그만 지원하지만, 추가 작업 데이터를 사용자 정의 MAPI 속성에 디버깅할 수 있습니다.

**Q: 플래그를 설정한 후 내 메시지가 저장되지 않습니다. 무엇을 확인해야 합니까?**
A: `outputDir` 경로가 어떻습니까, 해당 위치에 쓰기 권한이 있는지 확인하세요.

**Q: 한 번에 여러 메시지에서 플래그를 제거하려면 어떻게 해야 합니까?**
A: 메시지 컬렉션을 순회하면서 `MapiMessage`에 `FollowUpManager.clearFlag`를 호출하면 됩니다.

## 참고 자료
- [문서](https://reference.aspose.com/email/java/)
- [Aspose.Email for Java 다운로드](https://releases.aspose.com/email/java/)
- [Aspose.Email 무료 체험판](https://purchase.aspose.com/purchase/free-trial/aspose-email-java)

---

**최종 업데이트:** 2025년 12월 19일
**테스트 환경:** Aspose.Email for Java 25.4 (jdk16)
**개발자:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}