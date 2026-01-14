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

## 빠른 답변
- **어떤 존재입니까?** Java용 Aspose.Email
- **주요 작업?** 기념일 반복 및 백업이 포함된 MAPI 생성
- **필수 JDK?** Java16 이상
- **예외에 파일을 첨부할 수 있나요?** 예, `MapiCalendarExceptionInfo` 사용
- **캘린더는 어디서든 저장할 수 있나요?** `PersonalStorage`를 통해 PST 파일에 저장

### MAPI 작업란?
MAPI(Messaging Application 프로그래밍 인터페이스)는 Microsoft Outlook 및 기타 이메일 클라이언트에서 확장 데이터를 저장하는 표준 형식입니다. 구간 변경, 백업 및 첨부 파일을 지원하여 기업 일정 관리에 해당합니다.

### 왜 Aspose.Email for Java를 사랑해요?
Aspose.Email은 Outlook에 의존하지 않고 MAPI를 생성하고 수정하고 수정할 수 있도록 순수 Java API를 제공합니다. 이를 통해 서버-사이드 작업 기능을 구축하고, PST 파일을 생성하고, 관련 반복 시나리오를 프로그래밍 방식으로 처리할 수 있습니다.

## 전제 조건

시작하기 전에 환경이 준비되어 있는지 확인하세요:
- **Aspose.Email Library**: 버전 25.4(또는 이후) – Maven 또는 직접 다운로드가 가능합니다.
- **JDK(Java Development Kit)**: JDK16 이상.
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans 또는 Java‑호환 편집기.

### 필수 라이브러리 및 종속성

Maven을 사용하여 Aspose.Email을 프로젝트에 통합하려면 `pom.xml`에 다음 의존성을 추가하세요:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이선스 취득

Aspose.Email을 사용하려면 다음이 필요합니다.
- **무료 체험** – 비용 부담 없이 모든 기능을 탐색할 수 있습니다.
- **임시권** – 연속 평가를 위해 요청하세요.
- **정식 권위** – 배치를 위해 구매하세요.

## Java용 Aspose.Email 설정

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

## 구현 가이드

### 일일 반복 및 예외가 포함된 MAPI 달력 만들기

#### 개요
이 기능을 사용하면 반복해서 약속을 지키면서 특정 부분을 건너뛰거나 할 수 있습니다.

#### 단계별 구현

**1. 이벤트 시작 날짜 설정**  
시리즈가 시작될 날짜를 결정합니다:

```java
Date startDate = addHours(newDate(2018, 7, 19), 12);
```

**2. MAPI 달력 개체 만들기** 
위치, 제목 및 설명을 지정합니다:

```java
MapiCalendar calendar = new MapiCalendar("location1", "summary1", "description1", startDate, addHours(startDate, 1));
```

**3. 일일 반복 패턴 정의** 
이벤트가 매일 반복되도록 구성합니다:

```java
MapiCalendarEventRecurrence recurrence = new MapiCalendarEventRecurrence();
recurrence.setRecurrencePattern(new MapiCalendarDailyRecurrencePattern());
MapiCalendarRecurrencePattern pattern = recurrence.getRecurrencePattern();

pattern.setPatternType(MapiCalendarRecurrencePatternType.Day);
pattern.setPeriod(1); // Daily
pattern.setEndType(MapiCalendarRecurrenceEndType.NeverEnd);
```

**4. 반복에 예외 추가**  
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

### 캘린더 예외에 파일 첨부

#### 개요
별도 신청에 지원 문서(예: 안건)를 첨부할 수 있습니다.

**1. 파일 생성 및 첨부**

```java
MapiCalendarExceptionInfo exception = new MapiCalendarExceptionInfo();
exception.getAttachments().add("file.txt", "hello, world!".getBytes());
```

### MAPI 달력을 PST 파일에 저장

#### 개요
서버를 PST 파일에 저장하면 Outlook이나 기타 클라이언트에서 읽을 수 있습니다.

**1. 달력을 생성하고 PST에 저장**

```java
final PersonalStorage pst = PersonalStorage.create(new ByteArrayOutputStream(), FileFormatVersion.Unicode);
try {
    FolderInfo calendarFolder = pst.createPredefinedFolder("Calendar", StandardIpmFolder.Appointments);
    calendarFolder.addMapiMessageItem(calendar);
} finally {
    pst.dispose();
}
```

## 실제 적용
- **기업 업무를 관리** – 업무 시리즈를 자동화하고 시간을 자동으로 넘겨줍니다.
- **프로젝트 관리** – 종종 데이트가 변경되는 반복되는 스톤을 추적합니다.
- **이벤트 기획** – 일부 세션이 취소되더라도 재조정되는 다일범위를 관리합니다.

### 통합 가능성
Aspose.Email을 CRM 플랫폼, 작업 관리 API 또는 연결 플로 엔진과 결합해 엔드-투-엔드 통합을 공유할 수 있습니다.

## 성능 고려 사항
- **자원 폐기** – `PersonalStorage`의 `dispose()`를 호출해 파일 핸들을 해제합니다.
- **스트림 사용량** – 전체 PST를 메모리로 로드하지 않도록 `ByteArrayOutputStream` 또는 파일 스트림을 사용합니다.
- **비동기 작업** – 다수 생성을 위해 백그라운드 스레드에서 생성을 실행해 UI 응답성을 유지합니다.

## 결론
이 가이드를 따라 **mapi Calendar java**를 생성하고, 백업을 추가하며, 파일을 첨부하고, 모든 내용을 PST 파일에 저장하는 방법을 연결합니다. 이러한 기능을 통해 Outlook에 직접 접근할 수 없습니다.

### 다음 단계
- 매주 또는 월간 반복 패턴을 실험해 보세요.
- 알림, 알림, 카테고리와 동일한 추가 MAPI 속성을 탐색하세요.
- 좀 더 특별한 징후를 위해 Aspose.Email의 전반적인 API 문서를 검토하세요.

## 자주 묻는 질문

**Q: 댄스가 절연을 지원하고 있나요?**
A: 예, `MapiCalendar`의 `StartTimeZone` 및 `EndTimeZone` 속성에 접근할 수 있습니다.

**Q: 시리즈를 단독으로 분리하여 프로그래밍할 수 있습니까?**
A: 반복 패턴의 `DeletedInstanceDates` 컬렉션을 특정 날짜를 제거로 표시합니다.

**Q: Aspose.Email로 생성된 PST 파일 크기에 제한이 있습니까?**
A: PST 파일은 유니코드 제한 형식(기본 최대 2GB)을 추가하지만 `PersonalStorage` 설정을 통해 더 큰 규모로 구성할 수 있습니다.

**Q: 통화를 요청하는 중에 추가로?**
A: `MapiRecipient`를 생성하고 `RecipientType`을 `MapiRecipientType.MAPI_TO`로 설정한 뒤 `MapiMessage`의 `Recipients` 컬렉션에 추가합니다.

**Q: 반복 작업(appointments 외도 지원입니까?**
A: 예, Aspose.Email은 반복 서비스를 제공하는 `MapiTask`도 지원합니다.

## 참고 자료
- [Aspose.Email for Java 문서](https://reference.aspose.com/email/java/)
- [Aspose.Email 다운로드](https://releases.aspose.com/email/java/)
- [라이선스 구매](https://purchase.aspose.com/buy)
- [무료 평가판](https://releases.aspose.com/email/java/)
- [임시 라이선스 요청](https://purchase.aspose.com/temporary-license/)
- [Aspose 지원 포럼](https://forum.aspose.com/c/email/10)

---

**최종 업데이트:** 2025년 12월 20일
**테스트 환경:** Aspose.Email for Java 25.4 (JDK16)
**개발자:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
