---
date: '2026-10-02'
description: Aspose.Email for Java를 사용하여 Exchange에 연결하고 Exchange 공개 폴더를 나열하는 방법을 배웁니다.
  이 단계별 가이드에서는 Maven 의존성 및 코드 없이 설정하는 방법을 보여줍니다.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Aspose.Email for Java를 사용하여 Exchange에 연결하고 Exchange 공개 폴더를 나열하는 방법을
  배웁니다. 이 가이드에서는 Maven 의존성, 라이선스 및 재귀 메시지 검색에 대해 다룹니다.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Java에서 Exchange에 연결하고 공개 폴더를 나열하는 방법
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Java에서 Exchange에 연결하고 공개 폴더를 나열하는 방법
url: /ko/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 Exchange에 연결하고 공개 폴더를 나열하는 방법

## 소개
현대 기업에서는 Microsoft Exchange 사서함에 프로그래밍 방식으로 접근함으로써 보관, 모니터링 및 보고 작업을 자동화할 수 있습니다. 이 튜토리얼에서는 Aspose.Email for Java를 사용하여 **Exchange에 연결하는 방법**과 **Exchange 공개 폴더를 재귀적으로 나열하는 방법**을 보여줍니다. 필요한 Maven 종속성, 라이선스 단계 및 정확한 API 호출 순서를 확인할 수 있으며, 추가 라이브러리는 필요하지 않습니다. 마지막까지 진행하면 모든 공개 폴더에서 메시지를 가져와 로컬에 저장할 수 있게 됩니다.

## 빠른 답변
- **첫 번째 단계는 무엇인가요?** `pom.xml`에 Aspose.Email Maven 종속성을 추가합니다.  
- **라이선스가 필요합니까?** 예—평가용 임시 라이선스를 사용하거나 프로덕션용 정식 라이선스를 구매하십시오.  
- **연결을 생성하는 클래스는?** `ExchangeClient`(IMAP의 경우 `ImapClient`)가 인증 및 서버 통신을 처리합니다.  
- **하위 폴더를 자동으로 나열할 수 있나요?** 예—API에서 제공하는 재귀 `listSubFolders` 메서드를 사용합니다.  
- **이 접근 방식이 스레드 안전합니까?** 클라이언트 객체는 스레드 안전하지 않으므로, 동시 작업을 위해 스레드당 별도 인스턴스를 생성하십시오.

## Exchange에 연결하는 방법이란?
**Exchange에 연결하는 방법**은 Java 애플리케이션을 온프레미스 또는 클라우드 기반 Microsoft Exchange 서버에 인증하여 폴더 열거나 메시지 검색과 같은 API 호출을 할 수 있게 하는 과정입니다. Aspose.Email는 기본 EWS/IMAP 프로토콜을 추상화하여 단일하고 일관된 객체 모델을 제공합니다.

## 왜 Exchange 공개 폴더를 나열해야 하나요?
공개 폴더를 나열하면 조직이 공유 사서함, 배포 리스트 및 보관 저장소에 사용되는 계층 구조를 파악할 수 있습니다. Aspose.Email는 단일 호출로 **50개 이상의 공개 폴더**를 열거할 수 있으며, 전체 저장소를 메모리에 로드하지 않고 수백 페이지에 달하는 사서함을 처리할 수 있어 RAM 사용량을 최대 70 %까지 줄여줍니다.

## 전제 조건
- **Aspose.Email for Java** — 버전 25.4 이상(최신 안정 버전).  
- **Java Development Kit (JDK)** — JDK 11 이상이 설치되고 `JAVA_HOME`이 설정되어 있어야 합니다.  
- **Maven** — 종속성 관리 및 빌드 자동화를 위해 필요합니다.  
- Java 구문 및 Exchange 개념(사서함, 폴더, EWS)에 대한 기본 지식.

## Aspose.Email for Java 설정
라이브러리를 통합하려면 프로젝트의 `pom.xml`에 Maven 종속성을 추가하십시오. 이것이 필요한 **Aspose.Email Maven 종속성**입니다.

### Maven 종속성
다음 코드를 `pom.xml`의 `<dependencies>` 요소 안에 추가하십시오:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이선스 획득 단계
Aspose.Email는 전체 기능 사용을 위해 유효한 라이선스가 필요합니다:

- **무료 체험** – API를 평가하려면 [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 다운로드하십시오.  
- **구매** – 프로덕션 배포를 위해 Aspose 포털을 통해 상용 라이선스를 획득하십시오.

#### 기본 초기화
Maven이 패키지를 해결하고 라이선스 파일을 확보한 후, `.lic` 파일을 클래스패스에 배치하고 라이브러리를 초기화하십시오:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 구현 가이드
각 기능 블록을 단계별로 살펴보며, 핵심 질문에 대한 직접적이고 간결한 설명을 제공한 후 상세 단계로 진행합니다.

### Exchange에 연결하는 방법?
서버 URL, 사용자 자격 증명 및 도메인을 사용하여 `ExchangeClient`를 로드한 다음 `connect()`를 호출합니다. 클라이언트는 Exchange Web Services(EWS)와 HTTPS 세션을 설정하고 자격 증명을 검증합니다. 연결에 실패하면 API는 HTTP 상태 코드를 포함한 상세한 `AuthenticationException`을 발생시켜 빠른 문제 해결을 돕습니다.  
`ExchangeClient`는 Exchange Web Services와의 연결을 관리하는 Aspose.Email 클래스입니다.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Exchange 공개 폴더를 나열하는 방법?
`client.listPublicFolders()`를 호출하여 최상위 공개 폴더 각각을 나타내는 `FolderInfo` 객체 컬렉션을 가져옵니다. 이 메서드는 폴더 이름, 전체 항목 수 및 이후 호출에 사용되는 고유 식별자와 같은 메타데이터를 반환합니다. 일반적인 온프레미스 배포에서 500개 폴더까지는 2초 미만에 완료됩니다.  
`listPublicFolders()`는 `FolderInfo` 객체 컬렉션을 반환합니다.  
`FolderInfo`는 표시 이름 및 항목 수와 같은 메타데이터를 보유합니다.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### 폴더 정보를 표시하는 방법?
`FolderInfo` 컬렉션을 반복하면서 `displayName`과 `subFolderCount`를 출력합니다. 이 간단한 스냅샷은 더 깊은 탐색을 시작하기 전에 계층 구조를 이해하는 데 도움이 됩니다. 대규모 조직의 경우 API가 결과를 페이지화하여 페이지당 100개의 폴더를 반환함으로써 메모리 사용량을 낮게 유지합니다.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### 폴더에서 메시지를 나열하는 방법?
`folderId`는 이전 단계에서 얻은 식별자이며, `client.listMessages(folderId)`를 호출합니다. 이 메서드는 제목, 발신자 및 수신 날짜를 포함하는 `MessageInfo` 객체 목록을 반환합니다. 매우 큰 폴더를 처리할 때 클라이언트가 과부하되지 않도록 `maxCount`로 결과 집합을 제한할 수 있습니다.  
`listMessages(folderId)`는 `MessageInfo` 객체 목록을 반환합니다.  
`MessageInfo`는 이메일의 기본 속성(제목, 발신자, 수신 날짜)을 포함합니다.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### 메시지를 가져와 저장하는 방법?
각 `MessageInfo`에 대해 `client.fetchMessage(messageId)`를 사용하여 전체 MIME 콘텐츠를 다운로드합니다. 그런 다음 바이트 배열을 디스크의 `.eml` 파일에 씁니다. API는 콘텐츠를 스트리밍하므로 100 MB 메시지도 전체 페이로드를 메모리에 로드하지 않고 처리할 수 있습니다.  
`fetchMessage(messageId)`는 지정된 이메일의 전체 MIME 콘텐츠를 다운로드합니다.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### 하위 폴더에서 메시지를 재귀적으로 나열하는 방법?
깊이 우선 탐색을 구현합니다: 최상위 폴더에서 시작하여 `client.listSubFolders(parentId)`로 하위 폴더를 나열한 다음 각 하위 폴더에 대해 동일한 메시지 나열 루틴을 호출합니다. 이 패턴은 공개 폴더 트리의 모든 메시지가 처리되도록 보장합니다. 재귀 깊이는 서버의 폴더 계층 구조에 의해 제한되며(보통 < 20 레벨).  
`listSubFolders(parentId)`는 지정된 폴더의 즉시 하위 폴더를 반환합니다.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## 실용적인 적용 사례
이 워크플로우가 빛을 발하는 실제 시나리오:

1. **자동 이메일 보관** – 정기적으로 모든 공개 폴더 메시지를 가져와 규정에 맞는 아카이브에 저장합니다.  
2. **백업 솔루션** – Exchange 공개 폴더를 안전한 파일 시스템이나 클라우드 버킷에 복제하여 데이터 중복성을 보장합니다.  
3. **맞춤형 이메일 클라이언트** – 필요한 폴더와 메시지만 표시하는 경량 뷰어를 구축하여 UI 복잡성을 줄입니다.

## 성능 고려 사항
수천 개의 폴더와 수백만 개의 메시지로 확장할 때 다음 팁을 기억하십시오:

- **연결 풀링** – 폴더당 새 클라이언트를 생성하는 대신 여러 작업에 단일 `ExchangeClient` 인스턴스를 재사용합니다.  
- **지연 로딩** – 필요한 메타데이터만 요청(`maxCount` 매개변수를 사용한 `listMessages`)하고 필요 시 전체 본문을 가져옵니다.  
- **객체 해제** – 배치 실행 후 `client.dispose()`를 호출하여 HTTP 연결 및 스레드 로컬 버퍼를 해제합니다.  
- **병렬 처리** – 최상위 폴더를 여러 스레드에 분산하고 각 스레드마다 자체 클라이언트 인스턴스를 사용하여 다중 코어 CPU를 효율적으로 활용합니다.

## 자주 묻는 질문

**Q: 이 코드를 Exchange Online(Office 365)과 함께 사용할 수 있나요?**  
A: 예. Office 365 EWS 엔드포인트(`https://outlook.office365.com/EWS/Exchange.asmx`)를 제공하고 최신 인증(OAuth)을 사용하십시오 – Aspose.Email는 OAuth 토큰을 기본적으로 지원합니다.

**Q: 폴더에 10 000개 이상의 메시지가 포함된 경우 어떻게 해야 하나요?**  
A: `skip` 및 `take` 매개변수를 허용하는 `listMessages` 오버로드를 사용하여 결과를 페이지화하고 메모리 사용량을 제어하십시오.

**Q: 다운로드할 수 있는 단일 이메일 크기에 제한이 있나요?**  
A: API는 콘텐츠를 스트리밍하므로 JVM에 충분한 네이티브 메모리가 있는 경우 최대 150 MB까지의 메시지를 Java 힙 제한에 걸리지 않고 지원합니다.

**Q: SSL 인증서를 수동으로 처리해야 하나요?**  
A: 기본적으로 Aspose.Email는 Java 기본 키스토어를 신뢰합니다. Exchange 서버가 자체 서명 인증서를 사용하는 경우 JVM 신뢰 저장소에 가져오거나 테스트용으로만 `client.setEnableSslVerification(false)`를 설정하십시오.

**Q: 감사 목적을 위해 작업을 로그하려면 어떻게 해야 하나요?**  
A: `Logger.setLevel(Level.INFO)`를 구성하고 출력을 파일이나 모니터링 시스템으로 지정하여 Aspose.Email의 내장 로깅을 활성화하십시오.

## 결론
이제 Aspose.Email for Java를 사용하여 **Exchange에 연결하는 방법**과 공개 폴더에서 메시지를 재귀적으로 나열하는 완전하고 프로덕션 준비된 레시피를 갖추었습니다. 단계에는 Maven 설정, 라이선스, 연결, 폴더 열거, 메시지 검색 및 성능 튜닝이 포함됩니다. 데이터베이스, 클라우드 스토리지 또는 맞춤형 분석 파이프라인과 통합하여 조직의 특정 요구에 맞게 이 기반을 확장하십시오.

---

**마지막 업데이트:** 2026-10-02  
**테스트 환경:** Aspose.Email for Java 25.4  
**작성자:** Aspose

## 관련 튜토리얼

- [Java에서 Aspose.Email을 사용하여 Exchange 서버에 연결하는 방법: 단계별 가이드](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Aspose.Email for Java를 사용하여 Exchange 서버 폴더에 연결하고 나열하는 방법](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Aspose.Email for Java를 사용한 Exchange 서버 폴더 관리: 포괄적인 가이드](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}