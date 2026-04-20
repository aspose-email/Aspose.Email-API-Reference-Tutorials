---
date: '2026-03-20'
description: Aspose.Email for Java를 사용하여 매일 반복 및 예외가 포함된 Outlook 캘린더를 Java로 만드는 방법을
  배우고, 캘린더를 PST 파일로 저장하는 방법을 알아보세요.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: 일일 반복 및 예외가 있는 Outlook 캘린더 Java 만들기
url: /ko/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Outlook calendar java를 일일 반복 및 예외와 함께 만드는 방법

반복 이벤트를 효율적으로 관리하는 것은 어려울 수 있습니다. 특히 **outlook calendar java**가 일일 반복 패턴과 가끔 발생하는 예외를 지원해야 할 때 더욱 그렇습니다. 이 튜토리얼에서는 Outlook calendar Java 객체를 생성하고, 일일 반복을 설정하며, 예외 인스턴스를 추가하고, 마지막으로 Aspose.Email for Java를 사용해 **save calendar to PST** 하는 방법을 배웁니다. 끝까지 따라오면 Java 기반 일정 서비스에 바로 삽입할 수 있는 재사용 가능한 코드 스니펫을 얻을 수 있습니다.

## 빠른 답변
- **어떤 라이브러리?** Aspose.Email for Java  
- **주요 작업?** 일일 반복 및 예외가 있는 Outlook calendar Java 생성  
- **필수 JDK?** Java 16 이상  
- **예외에 파일을 첨부할 수 있나요?** `MapiCalendarExceptionInfo` 사용  
- **캘린더는 어디에 저장되나요?** `PersonalStorage`를 통해 PST 파일에  

## Outlook calendar java란?
Outlook calendar Java 객체(구현은 MAPI 캘린더)는 Microsoft Outlook 약속과 동일한 표준을 따릅니다. 풍부한 반복 규칙, 예외 처리, 참석자 및 첨부 파일을 저장할 수 있어 엔터프라이즈급 일정 관리에 적합합니다.

## 왜 Aspose.Email for Java를 사용하나요?
Aspose.Email은 순수 Java API를 제공하여 Outlook을 설치하지 않아도 MAPI 객체를 다룰 수 있게 해줍니다. 이 **aspose email tutorial java** 접근 방식은 서버 측에서 PST 파일을 생성하고, 자동 회의 시리즈를 만들며, 반복 로직을 완벽히 제어할 수 있게 합니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요.
- **Aspose.Email 라이브러리**: 버전 25.4 (또는 이후) – Maven 또는 직접 다운로드로 이용 가능.  
- **Java Development Kit (JDK)**: JDK 16 이상.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans, 또는 Java 호환 편집기.

### Required Libraries and Dependencies

Maven을 사용해 Aspose.Email을 프로젝트에 통합하려면 `pom.xml`에 다음 의존성을 추가하세요:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### License Acquisition

Aspose.Email을 사용하려면 라이선스가 필요합니다:
- **무료 체험** – 비용 없이 모든 기능 사용 가능.  
- **임시 라이선스** – 평가 기간 연장을 위해 요청.  
- **정식 라이선스** – 프로덕션 배포를 위해 구매.

## Setting Up Aspose.Email for Java

먼저 환경을 설정합니다:

1. JDK 16이 설치되어 있고 `JAVA_HOME`이 설정되어 있는지 확인합니다.  
2. Maven 의존성을 추가하거나(JAR를 다운로드) 프로젝트에 포함합니다.  

다음은 라이선스 파일을 로드하는 작은 코드 스니펫입니다:

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

## Implementation Guide

### Creating Outlook calendar java with Daily Recurrence and Exceptions

#### Overview
이 기능을 사용하면 반복 약속을 자동화하면서 특정 인스턴스를 건너뛰거나 수정할 수 있습니다.

#### Step‑by‑Step Implementation

**1. Set Up Event Start Date**  
시리즈가 시작될 날짜를 결정합니다:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Create the MAPI Calendar Object**  
위치, 제목 및 설명을 제공합니다:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Define a Daily Recurrence Pattern**  
이벤트가 매일 반복되도록 설정합니다:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. Add an Exception to the Recurrence**  
제외하거나 변경할 날짜를 지정합니다:

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

### Attaching Files to Calendar Exceptions

#### Overview
예외 인스턴스에 지원 문서(예: 안건)를 첨부할 수 있습니다.

**1. Create and Attach a File**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### Saving Outlook calendar java to PST (save calendar to pst)

#### Overview
캘린더를 PST 파일에 저장해 Outlook이나 다른 클라이언트가 읽을 수 있게 합니다.

**1. Create and Save Calendar to PST**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## Practical Applications
- **기업 일정 관리** – 회의 시리즈 자동화, 휴일 자동 건너뛰기.  
- **프로젝트 관리** – 가끔 날짜가 바뀌는 반복 마일스톤 추적.  
- **이벤트 기획** – 일부 세션이 취소되거나 재조정되는 다일 컨퍼런스 관리.

### Integration Possibilities
Aspose.Email을 CRM 플랫폼, 작업 관리 API 또는 맞춤 워크플로 엔진과 결합해 엔드‑투‑엔드 자동화를 구현합니다.

## Performance Considerations
- **리소스 해제** – 파일 핸들을 해제하려면 항상 `PersonalStorage`의 `dispose()`를 호출합니다.  
- **스트림 사용** – 전체 PST를 메모리에 로드하지 않도록 `ByteArrayOutputStream` 또는 파일 스트림을 선호합니다.  
- **비동기 작업** – 대량 캘린더 생성 시 UI 응답성을 유지하려면 백그라운드 스레드에서 생성 로직을 실행합니다.

## Conclusion
이 가이드를 따라 하면 **create outlook calendar java** 객체를 일일 반복으로 만들고, 예외를 추가하며, 파일을 첨부하고, **save calendar to PST** 하는 방법을 알게 됩니다. 이러한 기능을 활용하면 Outlook을 직접 다루지 않고도 강력한 일정 기능을 구축할 수 있습니다.

### Next Steps
- 주간 또는 월간 반복 패턴을 실험해 보세요.  
- 참석자, 알림, 카테고리 등 추가 MAPI 속성을 탐색하세요.  
- 보다 고급 시나리오를 위해 Aspose.Email의 포괄적인 API 문서를 검토하세요.

## Frequently Asked Questions

**Q: Does the library support time‑zone aware appointments?**  
A: Yes, you can set the `StartTimeZone` and `EndTimeZone` properties on `MapiCalendar`.  

**Q: Can I programmatically delete a single occurrence from a recurring series?**  
A: Use the `DeletedInstanceDates` collection on the recurrence pattern to mark specific dates as removed.  

**Q: Are there limits on the size of a PST file created with Aspose.Email?**  
A: PST files follow the Unicode format limits (up to 2 GB by default), but you can configure larger sizes via `PersonalStorage` settings.  

**Q: How do I add attendees to a meeting request?**  
A: Create `MapiRecipient` objects, set their `RecipientType` to `MapiRecipientType.MAPI_TO`, and add them to the `Recipients` collection of the `MapiMessage`.  

**Q: Is there support for recurring tasks (not just appointments)?**  
A: Yes, Aspose.Email also provides `MapiTask` with similar recurrence capabilities.  

**Q: Can I use this guide as part of an aspose email tutorial java series?**  
A: Absolutely – the steps shown here are a core part of any Aspose.Email Java tutorial that deals with calendar creation.  

## Resources
- [Aspose.Email for Java 문서](https://reference.aspose.com/email/java/)
- [Aspose.Email 다운로드](https://releases.aspose.com/email/java/)
- [라이선스 구매](https://purchase.aspose.com/buy)
- [무료 체험 버전](https://releases.aspose.com/email/java/)
- [임시 라이선스 요청](https://purchase.aspose.com/temporary-license/)
- [Aspose 지원 포럼](https://forum.aspose.com/c/email/10)

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}