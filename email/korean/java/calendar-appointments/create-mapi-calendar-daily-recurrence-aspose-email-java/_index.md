---
date: '2025-12-20'
description: Aspose.Email for Java를 사용하여 MAPI 캘린더를 생성하고, 일일 반복 패턴을 관리하며, 예외를 처리하는
  방법을 배웁니다.
keywords:
- MAPI Calendar creation
- daily recurrence events
- Java calendar exceptions
title: 일일 반복 및 예외가 포함된 MAPI 캘린더 Java 만들기
url: /ko/java/calendar-appointments/create-mapi-calendar-daily-recurrence-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 일일 반복 및 예외가 있는 mapi calendar java 생성 방법

반복 이벤트를 효율적으로 관리하는 것은 특히 예외나 변경이 필요할 때 어려울 수 있습니다. 이 튜토리얼에서는 **create mapi calendar java** 객체를 만들고, 일일 반복 패턴을 설정하며, Aspose.Email for Java를 사용해 예외를 추가하는 방법을 배웁니다. 애플리케이션 내에서 일정 작업을 원활하게 자동화하는 방법을 학습하게 됩니다.

## Quick Answers
- **어떤 라이브러리?** Aspose.Email for Java  
- **주요 작업?** 일일 반복 및 예외가 포함된 MAPI 캘린더 생성  
- **필수 JDK?** Java 16 이상  
- **예외에 파일을 첨부할 수 있나요?** 예, `MapiCalendarExceptionInfo` 사용  
- **캘린더는 어디에 저장되나요?** `PersonalStorage`를 통해 PST 파일에 저장

### MAPI 캘린더란?
MAPI(Messaging Application Programming Interface) 캘린더는 Microsoft Outlook 및 기타 이메일 클라이언트에서 약속 데이터를 저장하는 표준 형식입니다. 풍부한 반복 규칙, 예외 및 첨부 파일을 지원하여 기업 일정 관리에 이상적입니다.

### 왜 Aspose.Email for Java를 사용하나요?
Aspose.Email은 순수 Java API를 제공하여 Outlook에 의존하지 않고 MAPI 객체를 생성, 수정 및 저장할 수 있게 합니다. 이를 통해 서버‑사이드 일정 기능을 구축하고, PST 파일을 생성하며, 복잡한 반복 시나리오를 프로그래밍 방식으로 처리할 수 있습니다.

## Prerequisites

시작하기 전에 다음 환경이 준비되어 있는지 확인하세요:
- **Aspose.Email Library**: 버전 25.4(또는 이후) – Maven 또는 직접 다운로드 가능.  
- **Java Development Kit (JDK)**: JDK 16 이상.  
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans 또는 Java‑호환 편집기.

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
- **무료 체험** – 비용 없이 모든 기능을 탐색할 수 있습니다.  
- **임시 라이선스** – 연장 평가를 위해 요청하세요.  
- **정식 라이선스** – 프로덕션 배포를 위해 구매하세요.

## Setting Up Aspose.Email for Java

먼저 환경을 설정합니다:

1. JDK 16이 설치되어 있고 `JAVA_HOME`이 설정되어 있는지 확인합니다.  
2. Maven 의존성을 추가하거나 JAR 파일을 프로젝트에 포함합니다.  

다음은 라이선스 파일을 로드하는 간단한 코드 조각입니다:

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

### Creating MAPI Calendar with Daily Recurrence and Exceptions

#### Overview
이 기능을 사용하면 반복 약속을 자동화하면서 특정 인스턴스를 건너뛰거나 수정할 수 있습니다.

#### Step‑by‑Step Implementation

**1. Set Up Event Start Date**  
시리즈가 시작될 날짜를 결정합니다:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. Create the MAPI Calendar Object**  
위치, 제목 및 설명을 지정합니다:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. Define a Daily Recurrence Pattern**  
이벤트가 매일 반복되도록 구성합니다:

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

### Saving MAPI Calendar in PST Files

#### Overview
캘린더를 PST 파일에 저장하면 Outlook이나 기타 클라이언트에서 읽을 수 있습니다.

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
- **기업 일정 관리** – 회의 시리즈를 자동화하고 휴일을 자동으로 건너뜁니다.  
- **프로젝트 관리** – 가끔 날짜가 변경되는 반복 마일스톤을 추적합니다.  
- **이벤트 기획** – 일부 세션이 취소되거나 재조정되는 다일 컨퍼런스를 관리합니다.

### Integration Possibilities
Aspose.Email을 CRM 플랫폼, 작업 관리 API 또는 맞춤형 워크플로 엔진과 결합해 엔드‑투‑엔드 자동화를 구현할 수 있습니다.

## Performance Considerations
- **Dispose Resources** – `PersonalStorage`의 `dispose()`를 항상 호출해 파일 핸들을 해제합니다.  
- **Stream Usage** – 전체 PST를 메모리로 로드하지 않도록 `ByteArrayOutputStream` 또는 파일 스트림을 사용합니다.  
- **Async Operations** – 대량 캘린더 생성을 위해 백그라운드 스레드에서 생성 로직을 실행해 UI 응답성을 유지합니다.

## Conclusion
이 가이드를 따라 하면 **create mapi calendar java** 객체를 일일 반복과 함께 생성하고, 예외를 추가하며, 파일을 첨부하고, 모든 내용을 PST 파일에 저장하는 방법을 알게 됩니다. 이러한 기능을 통해 Outlook에 직접 접근하지 않고도 강력한 일정 기능을 구축할 수 있습니다.

### Next Steps
- 주간 또는 월간 반복 패턴을 실험해 보세요.  
- 참석자, 알림, 카테고리와 같은 추가 MAPI 속성을 탐색하세요.  
- 보다 고급 시나리오를 위해 Aspose.Email의 포괄적인 API 문서를 검토하세요.

## FAQ Section
1. **Aspose.Email을 라이선스 없이 사용할 수 있나요?**  
   - 예, 무료 체험 버전으로 기능을 탐색할 수 있습니다.  
2. **반복 이벤트의 예외를 어떻게 처리하나요?**  
   - `MapiCalendarExceptionInfo`를 사용해 날짜, 수정된 시간 및 첨부 데이터를 정의합니다.  
3. **캘린더를 직접 PST 파일에 저장할 수 있나요?**  
   - 물론입니다. `PersonalStorage` 클래스를 사용해 PST 파일을 만들고 캘린더 항목을 추가할 수 있습니다.  
4. **다른 Java 애플리케이션과 통합할 수 있나요?**  
   - 예, API가 순수 Java이므로 any Java‑based 서비스나 데스크톱 앱에 임베드할 수 있습니다.  
5. **라이선스가 만료되면 어떻게 해야 하나요?**  
   - Aspose 포털을 통해 라이선스를 갱신하거나 일시적으로 체험 모드로 전환하세요.

## Frequently Asked Questions

**Q: 라이브러리가 시간대 인식 약속을 지원하나요?**  
A: 예, `MapiCalendar`의 `StartTimeZone` 및 `EndTimeZone` 속성을 설정할 수 있습니다.

**Q: 반복 시리즈에서 단일 인스턴스를 프로그래밍 방식으로 삭제할 수 있나요?**  
A: 반복 패턴의 `DeletedInstanceDates` 컬렉션을 사용해 특정 날짜를 제거로 표시합니다.

**Q: Aspose.Email으로 생성된 PST 파일 크기에 제한이 있나요?**  
A: PST 파일은 Unicode 형식 제한(기본 최대 2 GB)을 따르지만 `PersonalStorage` 설정을 통해 더 큰 크기로 구성할 수 있습니다.

**Q: 회의 요청에 참석자를 어떻게 추가하나요?**  
A: `MapiRecipient` 객체를 생성하고 `RecipientType`을 `MapiRecipientType.MAPI_TO`로 설정한 뒤 `MapiMessage`의 `Recipients` 컬렉션에 추가합니다.

**Q: 반복 작업(appointments 외)도 지원하나요?**  
A: 예, Aspose.Email은 유사한 반복 기능을 제공하는 `MapiTask`도 지원합니다.

## Resources
- [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)  
- [Download Aspose.Email](https://releases.aspose.com/email/java/)  
- [Purchase a License](https://purchase.aspose.com/buy)  
- [Free Trial Version](https://releases.aspose.com/email/java/)  
- [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- [Aspose Support Forum](https://forum.aspose.com/c/email/10)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Email for Java 25.4 (JDK 16)  
**Author:** Aspose