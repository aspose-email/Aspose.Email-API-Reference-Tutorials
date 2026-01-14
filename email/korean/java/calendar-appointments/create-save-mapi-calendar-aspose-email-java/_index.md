---
date: '2026-01-01'
description: Aspose.Email for Java를 사용하여 MAPI 캘린더를 Java로 생성하고 캘린더를 PST에 저장하는 방법을 배웁니다.
  코드, 반복 일정 및 수신자를 포함한 단계별 가이드.
keywords:
- Create MAPI Calendar Java
- Aspose.Email Java Calendar
- Java PST File Save
title: Aspose.Email를 사용한 Java MAPI 캘린더 생성 방법 – 캘린더를 PST에 저장
url: /ko/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email을 사용하여 MAPI 달력 java 만들기 – 구성을 PST에 생성하기

## 소개

Java 기능을 작동시키고 있습니까? **Aspose.Email for Java**를 사용하면 **MAPI 캘린더 생성** java 항목을 작성하고, 반복을 정의하고, 디자인을 추가하며, **PST에 캘린더를 저장** 파일을 몇 가지 줄로만 코딩할 수 있습니다. 이 강의실 설정부터 배포 가능한 전체 항목 생성까지 전체 과정을 안내합니다.

### 무엇을 배울 것인가
- Aspose.Email을 사용하여 **MAPI 캘린더 java** 생성 방법을 생성합니다.
- 매일, 매주 또는 사용자 정의 반복 패턴을 구성합니다.
- 초대에 수신자(주최자, 참석자) 추가.
- Outlook 호환성을 위해 **PST에 일정 저장** 로 항목을 영구 저장합니다.

이제 개발 환경을 준비하시기 바랍니다.

## 빠른 답변
- **어떤 라이브러리?** Java용 Aspose.Email
- **주요 목표?** MAPI 달력 Java 만들기 및 **PST에 달력 저장**
- **전제 조건?** Java 8+, Maven, Aspose.Email 인스턴스
- **일반적인 구현 시간은?** 기본 이벤트에 10‑15분
- **반복을 추가할 수 있나요?** 예 – 매일, 주간, 월간 등.

## Java의 MAPI 달력이란 무엇입니까?
MAPI(Messaging Application 프로그래밍 인터페이스)를 통해 Outlook과 호환되도록 하겠습니다. Aspose.Email을 사용하면 이러한 프로그래밍 방식을 구성할 수 있어 Exchange, Outlook 또는 PST 파일을 사용하는 모든 클라이언트와 클러스터하게 통합할 수 있습니다.

## 캘린더 자동화에 Aspose.Email을 사용하는 이유는 무엇입니까?
- **전체 Outlook 호환성** – 생성된 항목은 Outlook, OWA 및 모바일 클라이언트에서 작동합니다.
- **풍부한 반복 지원** – 기본적으로 매일, 매주, 월간 및 사용자 정의 패턴을 지원합니다.
- **외부 종속성 없음** – 순수 Java 능력으로 COM 능력이 필요하지 않습니다.
- **고성능** – 주최자 PST 파일 및 다수 작업을 처리합니다.

## 전제 조건

시작하기 전에 다음 사항을 확인하세요.

### 필수 라이브러리
- **Java용 Aspose.Email**: 버전 25.4 이상.

### 환경 설정 요구 사항
- IntelliJ IDEA 또는 Eclipse와 같은 Java IDE.
- Maven이 설치되어야 합니다.

### 지식 전제조건
- 기본적으로 Java 프로그래밍 기술.
- 이해를 통해 개념을 이해한다.

## Java용 Aspose.Email 설정

`pom.xml`에 Aspose.Email Maven 종속성을 추가합니다.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이선스 취득

Aspose.Email은 무료 평가판을 제공하지만 라이선스를 통해 모든 기능을 잠금 해제할 수 있습니다.

- **무료 평가판**: 제한 없이 30일 동안 테스트합니다.
- **임시 라이센스**: 추가 시간이 필요하면 [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/)에서 요청하세요.
- **구매**: [구매 페이지](https://purchase.aspose.com/buy)에서 영구 기계를 신청합니다.

### 기본 초기화

종속성을 추가한 후 라이선스 파일을 사용하여 라이브러리를 초기화합니다.

```java
com.aspose.email.License license = new com.aspose.email.License();
license.setLicense("path_to_your_license.lic");
```

## 구현 가이드

이제 설정이 완료되었으므로 **MAPI 캘린더 java를 생성**하고 **캘린더를 PST에 저장**해 보겠습니다.

### 되풀이 기능이 포함된 MAPI 달력 만들기

#### 개요

선별된 이벤트를 조정하고, 일일 반복을 적용하고, 새로 추가하도록, 최종적으로 PST 파일에 저장합니다.

#### 단계별 구현

1. **날짜 및 반복 패턴 초기화** 

먼저 시작 시간을 정의하고 매일 반복되도록 설정합니다.

```java
import java.util.Date;

// Add hours to current date to get the start time
Date startDate = addHours(new Date(), 12);

MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
```

*설명*: `MapiCalendarEventRecurrence`는 반복 세부 정보를 보유합니다; `MapiCalendarDailyRecurrencePattern`을 통해 매일 패턴을 선택합니다.

2. **수신자 설정** 

모임 초대를 받아야 하는 사람을 추가합니다.

```java
import com.aspose.email.MapiRecipientCollection;
import com.aspose.email.MapiRecipientType;

MapiRecipientCollection recColl = new MapiRecipientCollection();
recColl.add("recipient@gmail.com", "Attendee Name", MapiRecipientType.MAPI_TO);
```

*설명*: `MapiRecipientCollection`은 각 인사를 저장합니다; `MAPI_TO`는 기본 수신자 표시입니다.

3. **MAPI 일정 항목 만들기** 

필요한 모든 세부 정보를 포함하여 달력 개체를 만듭니다.

```java
import com.aspose.email.MapiCalendar;

MapiCalendar calendar = new MapiCalendar(
   "Organizer Name", 
   "Meeting Subject", 
   "Meeting Location", 
   startDate, 
   addHours(startDate, 1), // End time is one hour after start
   "Event Description",
   recColl,
   recurrence
);
```

*설명*: 생성하는 조직자, 제목, 위치, 시작/종료 시간, 설명, 수신자 목록 및 반복을 기대합니다.

4. **PST 파일에 저장** 

마지막으로 **캘린더를 PST에 저장**하여 캘린더를 유지합니다.

```java
import com.aspose.email.PersonalStorage;
import com.aspose.email.FolderInfo;
import com.aspose.email.StandardIpmFolder;

PersonalStorage pst = PersonalStorage.create("calendar.pst", 0);
FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.CALendars);

// Save the MAPI Calendar item
calendarFolder.addMapiMessageItem(calendar);
```

*설명*: `PersonalStorage.create`는 새 PST 파일을 생성하고, `addMapiMessageItem`은 "Calendar" 폴더에 항목을 연결합니다.

### 문제 해결 팁
- 배치를 확인하세요; 무효화된 기능을 제한합니다.
- 초대를 거부하는 것을 방지하려면 수신자 주소를 이메일로 남겨두십시오.
- 작업 후 PST(`pst.dispose()`)를 늦아 파일 핸들을 휴가합니다.

## 실제 적용

다음은 **MAPI 캘린더 java 생성** 및 **PST에 캘린더 저장** 가 빛을 발하는 일반적인 시나리오입니다:

1. **자동 회의 예약** – 프로젝트 팀을 기념하여 초대를 계속 생성합니다.
2. **이벤트 관리 플랫폼** – 컨퍼런스 세션을 Outlook과 호환되는 항목으로 내보냅니다.
3. **CRM 통합** – CRM 시스템의 고객 약속을 PST 파일을 통해 Outlook을 통해 직접 확인해 보세요.

## 성능 고려 사항

- **리소스 관리**: 사용 후 `PersonalStorage`를 사용하여 파일 잠금을 방지합니다.
- **일괄 처리**: 많은 경우의 메모리 문제를 다루기 위해 다루기 위해 항목을 변경하거나 청크 단위로 처리합니다.

## 결론

이제 **MAPI 달력을 생성합니다. java** 준비를 준비하고, 반복을 구성하고, 인사를 추가하며, Aspose.Email을 사용하여 **캘린더를 PST에 저장** 하는 방법을 배웠습니다. 이 접근 방식은 Java의 Outlook 호환성을 높이려는 작업을 플로팅하도록 지원합니다.

더 자세히 알아보려면 공식 [문서](https://reference.aspose.com/email/java/)를 확인하세요.

## FAQ 섹션

### Q: 주간 반복 패턴을 만들 수 있나요?
- **답**: 네! 주간 반복을 정의하려면 `MapiCalendarWeeklyRecurrencePattern`을 사용하세요.

### Q: 이벤트 반복 시 예외를 어떻게 처리하나요?
- **답변**: 반복 객체에서 `setExceptions()`를 호출하여 패턴에서 벗어나는 날짜를 지정하세요.

### 질문: 기존 캘린더 항목을 업데이트할 수 있나요?

- **답변**: 물론입니다. PST 파일에서 항목을 불러와 속성을 수정하고 다시 저장하면 됩니다.

### 질문: PST 파일을 암호화할 수 있나요?

- **답변**: 네, Aspose.Email을 사용하면 PST 파일을 생성할 때 `PersonalStorage`에 암호를 설정할 수 있습니다.

### 질문: 캘린더 이벤트에 첨부 파일을 추가해야 하는 경우는 어떻게 해야 하나요?

- **답변**: 저장하기 전에 `calendar.getAttachments().addFileAttachment("path/to/file")`를 사용하세요.

## 리소스

- [Aspose.Email 문서](https://reference.aspose.com/email/java/)
- [Java용 Aspose.Email 다운로드](https://releases.aspose.com/email/java/)
- [라이선스 구매](https://purchase.aspose.com/buy)
- [무료 평가판](https://releases.aspose.com/email/java/)
- [임시 라이선스 요청](https://purchase.aspose.com/temporary-license/)
- [Aspose 지원 포럼](https://forum.aspose.com/c/email/10)

---

**최종 업데이트:** 2026-01-01
**테스트 환경:** Aspose.Email for Java 25.4 (JDK 16)
**작성자:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
