---
date: '2026-09-12'
description: Aspose.Email을 사용하여 Java에서 작업을 목록화하고 필터링하는 방법을 배웁니다. 이 가이드는 Exchange Server를
  위한 단계별 설정, 작업 검색 및 상태 필터링을 보여줍니다.
keywords:
- how to list tasks
- how to filter tasks
- Aspose.Email Java
- Exchange Server task automation
lastmod: '2026-09-12'
og_description: Aspose.Email for Java를 사용하여 작업을 목록화하는 방법. 이 튜토리얼을 따라 효율적으로 Exchange
  Server 작업을 설정하고, 검색하며, 필터링하세요.
og_image_alt: Tutorial screenshot showing Java code listing Exchange tasks with Aspose.Email
og_title: Aspose.Email for Java를 사용하여 작업 목록을 가져오는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to list tasks and how to filter tasks in Java using Aspose.Email.
    This guide shows step‑by‑step setup, task retrieval, and status filtering for
    Exchange Server.
  headline: How to list tasks with Aspose.Email for Java
  type: TechArticle
- description: Learn how to list tasks and how to filter tasks in Java using Aspose.Email.
    This guide shows step‑by‑step setup, task retrieval, and status filtering for
    Exchange Server.
  name: How to list tasks with Aspose.Email for Java
  steps:
  - name: '**Automated task sync** – Keep tasks in sync between Exchange and a project‑management
      tool.'
    text: '**Automated task sync** – Keep tasks in sync between Exchange and a project‑management
      tool.'
  - name: '**Status reporting** – Generate daily or weekly summaries that compare
      completed versus pending tasks.'
    text: '**Status reporting** – Generate daily or weekly summaries that compare
      completed versus pending tasks.'
  - name: '**Workflow triggers** – Launch CI/CD pipelines or notification services
      when a task reaches a particular status.'
    text: '**Workflow triggers** – Launch CI/CD pipelines or notification services
      when a task reaches a particular status.'
  - name: '**Bulk updates** – Reassign owners or change categories for many tasks
      in a single operation.'
    text: '**Bulk updates** – Reassign owners or change categories for many tasks
      in a single operation.'
  - name: '**Free trial** – Begin with a free trial to explore features.'
    text: '**Free trial** – Begin with a free trial to explore features.'
  - name: '**Temporary license** – Apply for an extended testing license if needed.'
    text: '**Temporary license** – Apply for an extended testing license if needed.'
  - name: '**Purchase** – Consider buying a full license after evaluating the library.'
    text: '**Purchase** – Consider buying a full license after evaluating the library.'
  - name: '**Automated task management** – Synchronize and update tasks across platforms
      automatically.'
    text: '**Automated task management** – Synchronize and update tasks across platforms
      automatically.'
  - name: '**Reporting tools** – Generate reports based on task completion status.'
    text: '**Reporting tools** – Generate reports based on task completion status.'
  - name: '**Workflow automation** – Trigger downstream processes when a task reaches
      a defined state.'
    text: '**Workflow automation** – Trigger downstream processes when a task reaches
      a defined state.'
  type: HowTo
- questions:
  - answer: Aspose.Email for Java is a library that simplifies interaction with email
      servers—including Exchange—through a clean, object‑oriented API.
    question: What is Aspose.Email for Java?
  - answer: Start with a free trial or request a temporary license; purchase a full
      license for production use via the Aspose website.
    question: How do I obtain an Aspose.Email license?
  - answer: It supports Java 16 or later; newer LTS releases are also fully compatible.
    question: Can I use Aspose.Email on any version of Java?
  - answer: Incorrect credentials, insufficient folder permissions, and not setting
      the correct time zone are the most frequent issues.
    question: What are common pitfalls when listing exchange tasks java?
  - answer: Visit the [official documentation](https://reference.aspose.com/email/java/)
      and [support forums](https://forum.aspose.com/c/email/10) for detailed guides
      and community help.
    question: Where can I find more resources on Aspose.Email for Java?
  type: FAQPage
tags:
- list tasks
- Aspose.Email
- Java task management
- Exchange Server
- filter tasks
title: Aspose.Email for Java를 사용하여 작업 목록을 가져오는 방법
url: /ko/java/calendar-appointments/aspose-email-java-task-management/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email for Java를 사용하여 작업 목록 가져오기

## 소개

현대 기업에서는 Microsoft Exchange에서 작업 처리를 자동화함으로써 수동 작업을 줄이고 정확성을 향상시킵니다. 이 튜토리얼에서는 Aspose.Email for Java를 사용하여 Exchange 사서함에서 **작업 목록을 가져오는 방법**을 설명하고, 상태별로 **작업을 필터링하는 방법**을 보여줍니다. 이를 통해 Outlook을 사용하지 않고도 보고 파이프라인이나 동기화 엔진을 구축할 수 있습니다. 필요한 설정, 정확한 API 호출, 성능 및 신뢰성을 위한 모범 사례 팁을 확인할 수 있습니다.

## 빠른 답변
- **“list exchange tasks java”는 무엇을 하나요?** Aspose.Email for Java를 통해 Exchange 사서함에서 작업을 가져옵니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Email for Java (버전 25.4 이상).  
- **상태별로 작업을 필터링할 수 있나요?** 예—`TaskStatus`와 함께 `ExchangeQueryBuilder`를 사용합니다.  
- **개발에 라이선스가 필요합니까?** 테스트용으로는 무료 체험판을 사용할 수 있으며, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Java 16 이상 권장됩니다.

## “list exchange tasks java”란 무엇인가요?
Java를 사용하여 Exchange 작업을 나열한다는 것은 프로그래밍 방식으로 Exchange 서버에 연결하고 작업 컬렉션을 가져오며 필요에 따라 필터링하는 것을 의미합니다. 이를 통해 수동 Outlook 작업 없이 대량 업데이트, 보고서 작성 또는 워크플로 트리거와 같은 자동화를 구현할 수 있습니다. 작업 인벤토리를 생성하고, 프로젝트 관리 도구와 동기화하거나, 분석 파이프라인에 데이터를 공급하는 데 사용할 수 있어 수동 작업을 줄이고 시스템 간 일관성을 보장합니다.

## 상태별로 작업을 필터링하는 이유
상태별로 작업을 필터링하면 현재 중요한 작업만 분리할 수 있습니다—예를 들어 일일 대시보드에 열려 있는 항목만 표시하거나 종료 보고서를 위해 완료된 작업을 가져오는 식입니다. 이렇게 하면 데이터 양이 감소하고 처리 속도가 빨라지며, 하위 시스템이 관련된 변경 사항에만 반응하도록 할 수 있습니다.

## 전제 조건

시작하기 전에 다음을 확인하십시오:

### 필수 라이브러리 및 종속성
- **Aspose.Email for Java**: 버전 25.4 이상.
- **Java Development Kit (JDK)**: 버전 16 이상 사용.

### 환경 설정
- Maven이 설치된 기능적인 Java 개발 환경.

### 지식 전제 조건
- Java 구문 및 객체 지향 개념에 대한 기본적인 이해.

## 이것이 중요한 이유
Aspose.Email를 사용하여 **list exchange tasks java**를 수행하면 Outlook UI가 제공하지 못하는 프로그래밍 제어를 얻을 수 있습니다. 반복적인 정리 작업을 자동화하고, 작업 데이터를 BI 대시보드에 통합하거나, 하위 서비스를 트리거할 수 있으며—all를 단일하고 유지 관리 가능한 Java 코드베이스에서 수행합니다. Aspose.Email는 **50개 이상의 Exchange 작업**을 지원하고 **수백 페이지에 달하는 작업 컬렉션**을 전체 사서함을 메모리에 로드하지 않고 처리할 수 있어 지연 시간과 메모리 사용량을 최소화합니다.

## 일반적인 사용 사례
1. **자동 작업 동기화** – Exchange와 프로젝트 관리 도구 간에 작업을 동기화합니다.  
2. **상태 보고** – 완료된 작업과 보류 중인 작업을 비교하는 일일 또는 주간 요약을 생성합니다.  
3. **워크플로 트리거** – 작업이 특정 상태에 도달하면 CI/CD 파이프라인이나 알림 서비스를 시작합니다.  
4. **대량 업데이트** – 여러 작업의 소유자를 재할당하거나 카테고리를 한 번에 변경합니다.

## Aspose Email Java 튜토리얼 – 설정
프로젝트에 Aspose.Email 라이브러리를 통합하려면 Maven을 사용하는 경우 `pom.xml`에 다음 종속성을 추가하십시오:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이선스 획득 단계
1. **무료 체험** – 기능을 살펴보기 위해 무료 체험으로 시작합니다.  
2. **임시 라이선스** – 필요에 따라 연장 테스트 라이선스를 신청합니다.  
3. **구매** – 라이브러리를 평가한 후 정식 라이선스 구매를 고려합니다.

환경을 설정하고 라이선스를 확보한 후, 다음과 같이 라이브러리를 초기화합니다:

```java
String mailboxUri = "https://ex2010/exchangeews/exchange.asmx";
String username = "test.exchange";
String password = "pwd";
String domain = "ex2010.local";

NetworkCredential credentials = new NetworkCredential(username, password, domain);
IEWSClient client = EWSClient.getEWSClient(mailboxUri, credentials);
```

## 구현 가이드

### Exchange 클라이언트 초기화
`ExchangeClient`는 Exchange 서버에 연결하기 위한 Aspose.Email의 주요 클래스입니다. 인증, 세션 관리 및 사서함 폴더에 대한 접근을 처리합니다.

```java
String mailboxUri = "https://ex2010/exchangeews/exchange.asmx";
String username = "test.exchange";
String password = "pwd";
String domain = "ex2010.local";

NetworkCredential credentials = new NetworkCredential(username, password, domain);
IEWSClient client = EWSClient.getEWSClient(mailboxUri, credentials);
```

- **매개변수**:  
  - `mailboxUri`: Exchange 서버의 엔드포인트 URL.  
  - `username`, `password`, `domain`: 인증에 사용되는 자격 증명.

### Exchange 서버에서 모든 작업 목록 가져오기
`TaskCollection`은 사서함 폴더에 저장된 작업 집합을 나타냅니다. 이를 검색하면 상태와 관계없이 모든 작업 항목을 반환합니다.

```java
client.setTimezoneId("Central Europe Standard Time");
TaskCollection taskCollection = client.listTasks(client.getMailboxInfo().getTasksUri());
int iTasksCount = taskCollection.size();
for (int i = 0; i < iTasksCount; i++) {
    ExchangeTask task = (ExchangeTask) taskCollection.get_Item(i);
    // Process each task
}
```

- **매개변수**:  
  - `setTimezoneId`: 작업이 올바른 현지 시간으로 표시되도록 합니다.

### Exchange 서버에서 특정 작업을 쿼리하고 목록 가져오기
`ExchangeQueryBuilder`는 서버 측 쿼리를 구축하여 `TaskStatus`와 같은 속성으로 작업을 필터링할 수 있게 합니다. 이것이 **작업을 필터링하는 방법**의 핵심입니다.

```java
Integer[] selectedStatuses = new Integer[]{
        ExchangeTaskStatus.Completed,
        ExchangeTaskStatus.InProgress
};

ExchangeQueryBuilder queryBuilder = new ExchangeQueryBuilder();
queryBuilder.getTaskStatus().in(Arrays.asList(selectedStatuses));
MailQuery query = queryBuilder.getQuery();

taskCollection = client.listTasks(client.getMailboxInfo().getTasksUri(), query);
iTasksCount = taskCollection.size();
for (int i = 0; i < iTasksCount; i++) {
    ExchangeTask task = (ExchangeTask) taskCollection.get_Item(i);
    // Process each queried task
}
```

- **매개변수**:  
  - `selectedStatuses`: 결과 집합에 포함할 상태를 지정하는 배열.

## 실용적인 적용 사례
Aspose.Email를 Java와 통합하면 다양한 실제 시나리오를 구현할 수 있습니다:
1. **자동 작업 관리** – 플랫폼 간 작업을 자동으로 동기화하고 업데이트합니다.  
2. **보고 도구** – 작업 완료 상태를 기반으로 보고서를 생성합니다.  
3. **워크플로 자동화** – 작업이 정의된 상태에 도달하면 하위 프로세스를 트리거합니다.  
4. **크로스‑플랫폼 통합** – CRM 또는 프로젝트 관리 시스템과 원활하게 연결합니다.

## 성능 고려 사항
솔루션을 빠르고 메모리 효율적으로 유지하려면:
- **네트워크 사용 최적화** – 필요한 필드(예: 제목, 마감일)만 요청합니다.  
- **효율적인 메모리 관리** – 전체 컬렉션을 한 번에 로드하는 대신 `TaskCollection`을 배치로 처리합니다.  
- **Aspose.Email 모범 사례** – 캐싱 및 연결 풀링에 대한 공식 문서를 따릅니다.

## 일반적인 문제 및 해결책

| 문제 | 가능한 원인 | 해결책 |
|-------|--------------|----------|
| **인증 실패** | 잘못된 자격 증명 또는 도메인 | `username`, `password`, `domain`을 확인하고 Exchange URL에 접근 가능한지 확인합니다. |
| **작업이 반환되지 않음** | 잘못된 사서함 URI 또는 권한 부족 | 서비스 계정이 Tasks 폴더에 접근할 수 있는지 확인합니다. |
| **시간대 불일치** | `setTimezoneId`가 설정되지 않았거나 잘못됨 | 해당 지역에 맞는 Windows 시간대 ID를 사용합니다. |
| **대용량 작업 컬렉션으로 인한 OOM** | 한 번에 모든 작업을 로드함 | 문서에 설명된 대로 `client.listTasks(..., query, offset, limit)`를 사용해 페이지 처리를 구현합니다. |

## 자주 묻는 질문

**Q: Aspose.Email for Java란 무엇인가요?**  
A: Aspose.Email for Java는 Exchange를 포함한 이메일 서버와의 상호 작용을 깔끔한 객체 지향 API를 통해 단순화하는 라이브러리입니다.

**Q: Aspose.Email 라이선스는 어떻게 얻나요?**  
A: 무료 체험으로 시작하거나 임시 라이선스를 요청할 수 있으며, 프로덕션 사용을 위해서는 Aspose 웹사이트에서 정식 라이선스를 구매합니다.

**Q: Aspose.Email를 모든 Java 버전에서 사용할 수 있나요?**  
A: Java 16 이상을 지원하며, 최신 LTS 릴리스와도 완전히 호환됩니다.

**Q: “list exchange tasks java”를 수행할 때 흔히 발생하는 함정은 무엇인가요?**  
A: 잘못된 자격 증명, 폴더 권한 부족, 올바른 시간대를 설정하지 않은 것이 가장 흔한 문제입니다.

**Q: Aspose.Email for Java에 대한 추가 자료는 어디서 찾을 수 있나요?**  
A: 자세한 가이드와 커뮤니티 도움을 위해 [공식 문서](https://reference.aspose.com/email/java/)와 [지원 포럼](https://forum.aspose.com/c/email/10)을 방문하십시오.

## 리소스
- **문서**: [Aspose Email Java 레퍼런스](https://reference.aspose.com/email/java/)
- **다운로드**: [Aspose Email Java 릴리스](https://releases.aspose.com/email/java/)
- **구매**: [Aspose 라이선스 구매](https://purchase.aspose.com/buy)
- **무료 체험**: [무료 체험 시작](https://releases.aspose.com/email/java/)
- **임시 라이선스**: [임시 라이선스 받기](https://purchase.aspose.com/temporary-license/)
- **지원**: [Aspose 지원 포럼](https://forum.aspose.com/c/email/10)

Aspose.Email for Java의 강력함을 활용하여 오늘 바로 Exchange 작업 관리를 간소화하세요!

---

**마지막 업데이트:** 2026-09-12  
**테스트 환경:** Aspose.Email for Java 25.4 (jdk16 classifier)  
**작성자:** Aspose

## 관련 튜토리얼
- [Aspose.Email for Java를 사용하여 Microsoft Exchange에서 작업 생성: 완전 가이드](/email/java/exchange-server-integration/create-tasks-exchange-aspose-email-java/)
- [Aspose.Email를 사용하여 Java에서 Exchange 서버에 연결하는 방법: 단계별 가이드](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Aspose.Email for Java로 Exchange 약속 관리: 종합 가이드](/email/java/exchange-server-integration/aspose-email-java-exchange-appointments-management/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}