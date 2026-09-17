---
date: '2026-09-17'
description: Outlook 캘린더를 Java로 일일 반복 및 예외와 함께 만드는 방법을 배우고, Aspose.Email for Java를
  사용하여 캘린더를 PST에 저장하는 방법을 알아보세요.
keywords:
- create outlook calendar
- outlook calendar daily recurrence
- java calendar exceptions
- Aspose.Email Java
- MAPI PST generation
lastmod: '2026-09-17'
og_description: Aspose.Email을 사용하여 Java에서 Outlook 캘린더를 만드는 방법을 안내합니다. 일일 반복, 예외 처리
  및 PST 저장을 단계별로 배울 수 있습니다.
og_image_alt: Code example creating Outlook calendar with recurrence and PST export
  using Aspose.Email for Java
og_title: Java에서 Outlook 캘린더를 일일 반복 및 예외와 함께 만들기
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create outlook calendar java with daily recurrence and
    exceptions, and save calendar to PST using Aspose.Email for Java.
  headline: Create outlook calendar java with daily recurrence and exceptions
  type: TechArticle
- questions:
  - answer: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.
    question: Does the library support time‑zone aware appointments?
  - answer: Use the `DeletedInstanceDates` collection on the recurrence pattern to
      mark specific dates as removed.
    question: Can I programmatically delete a single occurrence from a recurring series?
  - answer: PST files follow the Unicode format limits (up to 2 GB by default), but
      you can configure larger sizes via `PersonalStorage` settings.
    question: Are there limits on the size of a PST file created with Aspose.Email?
  - answer: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`,
      and add them to the `Recipients` collection of the `MapiMessage`.
    question: How do I add attendees to a meeting request?
  - answer: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.
    question: Is there support for recurring tasks (not just appointments)?
  type: FAQPage
tags:
- outlook calendar
- Aspose.Email
- Java scheduling
- PST file
title: Java로 Outlook 캘린더를 일일 반복 및 예외와 함께 만들기
url: /ko/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 일일 반복 및 예외가 있는 Outlook 캘린더 Java 만들기

반복 이벤트를 효율적으로 관리하는 것은 어려울 수 있으며, 특히 일일 반복 패턴과 가끔 발생하는 예외를 지원하는 **outlook calendar java**가 필요할 때 그렇습니다. 이 튜토리얼에서는 Outlook 캘린더 Java 객체를 생성하고, 일일 반복을 구성하며, 예외 인스턴스를 추가하고, 마지막으로 Aspose.Email for Java를 사용하여 **save calendar to PST**를 수행하는 방법을 배웁니다. 끝까지 읽으면 Java 기반 일정 서비스에 삽입할 수 있는 재사용 가능한 코드 스니펫을 얻게 됩니다.

## 빠른 답변
- **어떤 라이브러리?** Aspose.Email for Java  
- **주요 작업?** 일일 반복 및 예외가 있는 Outlook 캘린더 Java 만들기  
- **필수 JDK?** Java 16 or higher  
- **예외에 파일을 첨부할 수 있나요?** Yes, using `MapiCalendarExceptionInfo`  
- **캘린더는 어디에 저장되나요?** In a PST file via `PersonalStorage`  

## Outlook 캘린더 Java란?
Outlook 캘린더 Java 객체는 Outlook 약속을 프로그래밍 방식으로 표현한 것으로, MAPI(Messaging Application Programming Interface) 사양을 기반으로 하며, 제목, 위치, 시작/종료 시간, 반복 규칙, 참석자 및 첨부 파일과 같은 속성을 포함합니다. 이 객체는 Outlook 없이도 조작, 직렬화 및 PST 파일에 저장할 수 있습니다.

## 왜 Aspose.Email for Java를 사용하나요?
Aspose.Email for Java를 사용하면 Outlook을 설치하지 않고도 MAPI 객체를 다룰 수 있습니다. 이 라이브러리는 **50+ MAPI properties**를 지원하고, 일반적인 약속 데이터를 위해 **2 seconds** 이하의 시간에 **2 GB**까지의 유니코드 PST 파일을 생성할 수 있으며, Java 16+을 지원하는 모든 플랫폼에서 실행됩니다. 순수 Java 접근 방식은 서버 측 캘린더 생성, 자동 회의 시리즈 및 반복 로직에 대한 완전한 제어를 가능하게 합니다.

## 전제 조건

Before we begin, ensure you have the following setup:
- **Aspose.Email Library**: Version 25.4 (or later) – Maven 또는 직접 다운로드를 통해 제공됩니다.  
- **Java Development Kit (JDK)**: JDK 16 이상.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans 또는 Java 호환 편집기.

### 필요한 라이브러리 및 종속성

Maven을 사용하여 Aspose.Email을 프로젝트에 통합하려면, `pom.xml`에 다음 종속성을 추가하십시오:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이선스 획득

To use Aspose.Email, you'll need a license:
- **무료 체험** – 비용 없이 모든 기능을 탐색합니다.  
- **임시 라이선스** – 연장 평가를 위해 요청합니다.  
- **정식 라이선스** – 프로덕션 배포를 위해 구매합니다.

## Aspose.Email for Java 설정

First, set up your environment:

1. JDK 16이 설치되고 `JAVA_HOME`이 설정되었는지 확인합니다.  
2. Maven 종속성(또는 JAR 파일)을 프로젝트에 추가합니다.  

다음은 라이선스 파일을 로드하는 방법을 보여주는 작은 코드 스니펫입니다:

```java
import com.aspose.email.*;

public class InitializeAspose {
    public static void main(String[] args) {
        // Set up a license if available
        License license = new License();
        try {
            license.setLicense("path/to/your/license.lic");
        } catch (Exception e) {
            System.out.println("License not found, using trial version.");
        }
    }
}
```

## 구현 가이드

### 일일 반복 및 예외가 있는 Outlook 캘린더 Java 만들기

#### 개요
이 기능을 사용하면 반복 약속을 자동화하면서 특정 인스턴스를 건너뛰거나 수정할 수 있습니다.

#### 단계별 구현

**1. 이벤트 시작 날짜 설정**  
시리즈가 언제 시작될지 결정합니다:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI 캘린더 객체 생성**  
`MapiCalendar` 클래스는 메모리 내에서 단일 캘린더 항목을 나타내는 최상위 객체입니다. 위치, 제목 및 설명을 제공합니다:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. 일일 반복 패턴 정의**  
`MapiCalendarRecurrencePattern` 클래스는 약속을 매일 반복하도록 하는 규칙을 저장합니다. 이벤트가 매일 반복되도록 구성합니다:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. 반복에 예외 추가**  
`MapiCalendarExceptionInfo`는 패턴에서 벗어나는 단일 발생을 설명합니다—제외되거나 변경될 수 있습니다. 제외(또는 변경)할 날짜를 지정합니다:

```java
Date exceptionDate = addDays(startDate, 3);

MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.setLocation("exceptionLocation");
exception.setSubject("exceptionSubject");
exception.setBody("exceptionBody");

exception.setOriginalStartDate(exceptionDate);
exception.setStartDateTime(exceptionDate);
exception.setEndDateTime(addHours(exceptionDate, 5));

pattern.getExceptions().addItem(exception);
pattern.getModifiedInstanceDates().addItem(exceptionDate);
pattern.getDeletedInstanceDates().addItem(exceptionDate);

calendar.setRecurrence(recurrence);
```

### 캘린더 예외에 파일 첨부

#### 개요
예외 인스턴스에 지원 문서(예: 안건)를 첨부할 수 있습니다.

**1. 파일 생성 및 첨부**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

## Outlook 캘린더 Java를 PST에 저장 (save calendar to pst)

#### 개요
Outlook 또는 기타 클라이언트가 읽을 수 있도록 캘린더를 PST 파일에 저장합니다.

**1. 캘린더를 생성하고 PST에 저장**  
`PersonalStorage` 클래스는 새 PST 파일을 생성하고 MAPI 항목을 추가하는 메서드를 제공합니다.

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## 실용적인 적용 사례
- **기업 일정 관리** – 회의 시리즈를 자동화하고 휴일을 자동으로 건너뜁니다.  
- **프로젝트 관리** – 가끔 날짜가 변경되는 반복 마일스톤을 추적합니다.  
- **이벤트 기획** – 일부 세션이 취소되거나 재조정되는 다일 컨퍼런스를 관리합니다.

### 통합 가능성
Aspose.Email를 CRM 플랫폼, 작업 관리 API 또는 맞춤형 워크플로 엔진과 결합하여 엔드‑투‑엔드 자동화를 구현합니다.

## 성능 고려 사항
- **리소스 해제** – 파일 핸들을 해제하려면 항상 `PersonalStorage`에서 `dispose()`를 호출합니다.  
- **스트림 사용** – 전체 PST를 메모리에 로드하는 것을 피하기 위해 `ByteArrayOutputStream` 또는 파일 스트림을 선호합니다.  
- **비동기 작업** – 대량 캘린더 생성을 위해 백그라운드 스레드에서 생성 로직을 실행하여 UI 응답성을 유지합니다.

## 결론
이 가이드를 따라 하면 이제 일일 반복이 있는 **create outlook calendar java** 객체를 만들고, 예외를 추가하고, 파일을 첨부하며, **save calendar to PST**를 수행하는 방법을 알게 됩니다. 이러한 기능을 통해 Outlook을 직접 사용하지 않고도 강력한 일정 기능을 구축할 수 있습니다.

### 다음 단계
- 주간 또는 월간 반복 패턴을 실험해 보세요.  
- 참석자, 알림 및 카테고리와 같은 추가 MAPI 속성을 탐색하세요.  
- 보다 고급 시나리오를 위해 Aspose.Email의 포괄적인 API 문서를 검토하세요.

## 자주 묻는 질문

**Q: 라이브러리가 시간대 인식 약속을 지원하나요?**  
A: 예, `MapiCalendar`의 `StartTimeZone` 및 `EndTimeZone` 속성을 설정할 수 있습니다.

**Q: 반복 시리즈에서 단일 발생을 프로그래밍 방식으로 삭제할 수 있나요?**  
A: 반복 패턴의 `DeletedInstanceDates` 컬렉션을 사용하여 특정 날짜를 제거된 것으로 표시합니다.

**Q: Aspose.Email로 생성된 PST 파일 크기에 제한이 있나요?**  
A: PST 파일은 기본적으로 2 GB까지인 Unicode 형식 제한을 따르지만, `PersonalStorage` 설정을 통해 더 큰 크기로 구성할 수 있습니다.

**Q: 회의 요청에 참석자를 어떻게 추가하나요?**  
A: `MapiRecipient` 객체를 생성하고, `RecipientType`을 `MapiRecipientType.MAPI_TO`로 설정한 뒤, `MapiMessage`의 `Recipients` 컬렉션에 추가합니다.

**Q: 반복 작업(약속이 아닌) 지원이 있나요?**  
A: 예, Aspose.Email는 유사한 반복 기능을 갖춘 `MapiTask`도 제공합니다.

**Q: 이 가이드를 Aspose.Email Java 튜토리얼 시리즈의 일부로 사용할 수 있나요?**  
A: 물론입니다 – 여기 제시된 단계는 캘린더 생성과 관련된 모든 Aspose.Email Java 튜토리얼의 핵심 부분입니다.

## 리소스
- [Aspose.Email for Java 문서](https://reference.aspose.com/email/java/)
- [Aspose.Email 다운로드](https://releases.aspose.com/email/java/)
- [라이선스 구매](https://purchase.aspose.com/buy)
- [무료 체험 버전](https://releases.aspose.com/email/java/)
- [임시 라이선스 요청](https://purchase.aspose.com/temporary-license/)
- [Aspose 지원 포럼](https://forum.aspose.com/c/email/10)

---

**마지막 업데이트:** 2026-09-17  
**테스트 환경:** Aspose.Email for Java 25.4 (JDK 16)  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Email – Java를 사용한 Outlook 캘린더 PST 내보내기](/email/java/calendar-appointments/create-save-mapi-calendar-aspose-email-java/)
- [Aspose.Email을 사용한 Java 캘린더 항목 만들기](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)
- [Aspose.Email for Java를 사용한 캘린더 공유 초대 만들기](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}