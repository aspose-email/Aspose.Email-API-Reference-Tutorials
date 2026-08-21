---
date: '2026-06-18'
description: Aspose.Email for Java를 사용하여 Zimbra TGZ 아카이브에서 이메일을 추출하는 방법을 배웁니다. Maven
  의존성 설정 및 Aspose Email 설정과 실용적인 예제가 포함됩니다.
keywords:
- how to use aspose.email
- maven dependency aspose email
- extract emails from zimbra tgz
schemas:
- author: Aspose
  dateModified: '2026-06-18'
  description: Learn how to use Aspose.Email for Java to extract emails from Zimbra
    TGZ archives. Includes Maven dependency Aspose Email setup and practical examples.
  headline: 'How to Use Aspose.Email for Java: Extract Emails from Zimbra TGZ Archives'
  type: TechArticle
- description: Learn how to use Aspose.Email for Java to extract emails from Zimbra
    TGZ archives. Includes Maven dependency Aspose Email setup and practical examples.
  name: 'How to Use Aspose.Email for Java: Extract Emails from Zimbra TGZ Archives'
  steps:
  - name: Define File Path
    text: Specify the absolute or relative path to the TGZ file you want to process.
  - name: Initialize TgzReader
    text: Create a `TgzReader` instance using the file path. *Direct answer:* Initializing
      `TgzReader` opens the archive and prepares it for sequential message extraction.
  - name: Extract Emails
    text: Iterate through each stored message, retrieve its folder location, and obtain
      a `MailMessage` object. - `readNextMessage()` returns `false` when no more messages
      remain. - `getCurrentDirectory()` shows the internal folder path inside the
      TGZ. - `getCurrentMessage()` gives you a fully parsed `MailMes
  type: HowTo
- questions:
  - answer: JDK 16+, Maven, and the `com.aspose:aspose-email` Maven artifact.
    question: What are the prerequisites for using Aspose.Email for Java?
  - answer: Purchase a license or request a temporary one via the [Aspose purchase
      page](https://purchase.aspose.com/buy).
    question: How can I obtain a license for production use?
  - answer: Verify the file exists, the path is correctly escaped for Java strings,
      and the process has read permissions.
    question: My TGZ path seems invalid—what should I check?
  - answer: Yes, the API is thread‑safe; you can instantiate separate `TgzReader`
      objects per thread.
    question: Does Aspose.Email support multi‑threaded extraction?
  - answer: Save each `MailMessage` as EML, JSON, or XML using `SaveOptions`, then
      feed the files into your downstream pipelines.
    question: How do I integrate extracted emails with other systems?
  type: FAQPage
title: 'Aspose.Email for Java 사용 방법: Zimbra TGZ 아카이브에서 이메일 추출'
url: /ko/java/email-parsing-analysis/extract-emails-zimbra-tgz-aspose-email-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email for Java 사용 방법: Zimbra TGZ 아카이브에서 이메일 추출

## 소개

Zimbra TGZ 아카이브에 저장된 메시지를 추출하기 위해 **Aspose.Email 사용 방법**이 필요하다면, 여기서 정확히 확인할 수 있습니다. 이 가이드에서는 Maven 설정부터 각 이메일을 읽는 단계까지 모두 안내하므로, 백업, 마이그레이션 또는 포렌식 작업을 자신 있게 자동화할 수 있습니다. 끝까지 읽으면 라이브러리 구성, 메시지 순회, 결과를 자체 워크플로에 통합하는 방법을 이해하게 됩니다.

## 빠른 답변
- **Zimbra TGZ 이메일을 추출하는 라이브러리는?** Aspose.Email for Java.
- **필요한 Maven 아티팩트는?** `com.aspose:aspose-email`.
- **최소 Java 버전?** JDK 16 이상.
- **대용량 아카이브도 처리할 수 있나요?** 예, 배치 처리로 메모리 사용량을 낮게 유지합니다.
- **프로덕션에 라이선스가 필요합니까?** 예, 전체 또는 임시 Aspose.Email 라이선스가 필요합니다.

## 전제 조건

- **Java Development Kit (JDK)** 16 이상.
- **Maven** – 의존성 관리용.
- **Aspose.Email for Java** v25.4 (또는 이후 버전) – 다음에 Maven 종속성을 추가합니다.
- 파싱하려는 Zimbra TGZ 아카이브 파일에 대한 접근 권한.

## Aspose.Email Maven 종속성을 추가하는 방법은?

Aspose.Email을 Maven 프로젝트에 포함하려면 `pom.xml`의 `<dependencies>` 섹션에 아래 종속성 코드를 추가하십시오. Maven이 아티팩트를 해결하고 필요한 JAR을 다운로드하여 클래스패스에 라이브러리를 자동으로 제공하므로 수동으로 JAR을 다룰 필요 없이 바로 코딩을 시작할 수 있습니다.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
</dependency>
```

*Direct answer:* 위 종속성을 추가하면 라이브러리가 자동으로 다운로드되어 수동 JAR 처리를 하지 않고 바로 코딩을 시작할 수 있습니다.

## 라이선스 획득

Aspose는 세 가지 라이선스 경로를 제공합니다:
- **무료 체험** – 평가용 임시 라이선스.
- **임시 라이선스** – 평가 제한 없이 단기 사용.
- **전체 구매** – 무제한 프로덕션 사용.

자세한 내용은 [Aspose 구매 페이지](https://purchase.aspose.com/buy)를 방문하십시오.

## 기본 초기화

Aspose.Email을 사용하려면 필요한 클래스를 임포트하고 기본 설정 블록을 생성합니다.

```java
import com.aspose.email.*;
```

*Direct answer:* 임포트를 추가한 후 Java 코드에서 바로 Aspose.Email 객체를 인스턴스화할 수 있습니다.

## 구현 가이드

### TgzReader 클래스는 무엇이며 어떻게 작동합니까?

`TgzReader` 클래스는 전체 아카이브를 메모리에 로드하지 않고 Zimbra TGZ 저장 파일을 스트리밍으로 읽을 수 있는 Aspose.Email의 API입니다.

#### 단계 1: 파일 경로 정의

처리하려는 TGZ 파일의 절대 경로나 상대 경로를 지정합니다.

```java
String tgzPath = "C:/archives/zimbra_backup.tgz";
```

#### 단계 2: TgzReader 초기화

파일 경로를 사용하여 `TgzReader` 인스턴스를 생성합니다.

```java
TgzReader tgzReader = new TgzReader(tgzPath);
```

*Direct answer:* `TgzReader` 초기화는 아카이브를 열고 순차적인 메시지 추출을 준비합니다.

#### 단계 3: 이메일 추출

저장된 각 메시지를 순회하면서 폴더 위치를 가져오고 `MailMessage` 객체를 얻습니다.

```java
while (tgzReader.readNextMessage()) {
    String directory = tgzReader.getCurrentDirectory();
    MailMessage message = tgzReader.getCurrentMessage();
    // Process the MailMessage (save, analyze, etc.)
}
tgzReader.dispose();
```

- `readNextMessage()`는 더 이상 메시지가 없을 때 `false`를 반환합니다.
- `getCurrentDirectory()`는 TGZ 내부의 폴더 경로를 표시합니다.
- `getCurrentMessage()`는 완전히 파싱된 `MailMessage`를 제공합니다.

*Direct answer:* 위 루프는 아카이브의 모든 이메일을 추출하여 각 메시지를 개별적으로 처리할 수 있게 합니다.

### Aspose.Email 유틸리티로 디렉터리 처리를 간소화하는 방법은?

Aspose.Email은 파일 시스템 경로를 동적으로 구성하는 헬퍼 메서드를 제공합니다. 아래는 어떤 클래스에도 삽입할 수 있는 간결한 유틸리티 메서드입니다.

```java
public static String buildOutputPath(String base, String folder, String fileName) {
    return Paths.get(base, folder, fileName).toString();
}
```

*Direct answer:* `buildOutputPath`를 사용하면 저장된 이메일 파일의 출력 위치를 일관되게 생성할 수 있습니다.

#### 유틸리티 함수 사용

유틸리티를 추출 루프와 결합하여 각 이메일을 EML 파일로 저장합니다.

```java
String outputBase = "C:/extracted_emails";
while (tgzReader.readNextMessage()) {
    String dir = tgzReader.getCurrentDirectory();
    MailMessage msg = tgzReader.getCurrentMessage();
    String outPath = buildOutputPath(outputBase, dir, msg.getSubject() + ".eml");
    msg.save(outPath, SaveOptions.getDefaultEml());
}
```

*Direct answer:* 코드는 TGZ 아카이브 내부의 원래 위치를 반영하는 폴더에 각 메시지를 저장합니다.

## Zimbra TGZ 추출에 Aspose.Email을 사용하는 이유

Aspose.Email은 Zimbra TGZ 아카이브에서 이메일을 추출하기 위한 포괄적이고 고성능 솔루션을 제공합니다. 스트리밍을 지원해 메모리 사용량을 낮게 유지하고, 1 GB 이상의 대용량 아카이브를 처리하며, 스레드 안전 API를 제공하므로 대규모 백업, 마이그레이션 또는 포렌식 프로젝트에 신뢰성과 속도가 중요한 경우 이상적입니다.

- **50개 이상의 입력 형식** – Aspose.Email은 EML, MSG, MBOX, PST 및 Zimbra TGZ 등을 읽을 수 있습니다.
- **1 GB 이상 아카이브 처리** – 스트리밍 방식으로 다중 기가바이트 TGZ 파일을 처리하며 RAM 사용량을 200 MB 이하로 유지합니다.
- **외부 종속성 없음** – Zimbra 서버 라이브러리나 네이티브 도구가 필요 없습니다.
- **스레드 안전 API** – 배치 작업을 위해 여러 `TgzReader` 인스턴스를 병렬로 실행할 수 있습니다.

이러한 정량적 이점은 Aspose.Email을 대규모 이메일 아카이빙 프로젝트에 적합한 프로덕션급 선택으로 만듭니다.

## 성능 고려 사항

매우 큰 TGZ 파일을 다룰 때는 다음 모범 사례를 따르세요:

- **즉시 해제** – 작업이 끝나는 즉시 `tgzReader.dispose()`를 호출해 네이티브 리소스를 해제합니다.
- **배치 처리** – 메시지를 그룹(예: 500개씩)으로 처리하고 결과를 디스크에 기록한 후 다음 배치를 진행합니다.
- **전체 내용 로드 회피** – 전체 아카이브를 메모리로 읽는 대신 스트리밍 API(`readNextMessage`)를 사용합니다.

이 지침을 따르면 저사양 서버에서도 CPU와 메모리 사용량을 낮게 유지할 수 있습니다.

## 실용적인 적용 사례

Zimbra TGZ 아카이브에서 이메일을 추출하는 것은 다음과 같은 상황에 유용합니다:

- **백업 및 복구** – 아카이브된 TGZ 파일에서 메일함을 재구성합니다.
- **데이터 마이그레이션** – 레거시 Zimbra 데이터를 Exchange, Office 365 또는 맞춤형 스토리지로 이동합니다.
- **포렌식 분석** – 전체 Zimbra 인스턴스를 복원하지 않고도 과거 커뮤니케이션을 검토합니다.

## 자주 묻는 질문

**Q: Aspose.Email for Java 사용을 위한 전제 조건은 무엇입니까?**  
A: JDK 16 이상, Maven, 그리고 `com.aspose:aspose-email` Maven 아티팩트가 필요합니다.

**Q: 프로덕션 사용을 위한 라이선스를 어떻게 얻을 수 있습니까?**  
A: 라이선스를 구매하거나 [Aspose 구매 페이지](https://purchase.aspose.com/buy)를 통해 임시 라이선스를 요청하십시오.

**Q: TGZ 경로가 유효하지 않은 것 같습니다—무엇을 확인해야 하나요?**  
A: 파일이 존재하는지, Java 문자열에 경로가 올바르게 이스케이프되었는지, 프로세스에 읽기 권한이 있는지 확인하십시오.

**Q: Aspose.Email이 다중 스레드 추출을 지원합니까?**  
A: 예, API가 스레드 안전하므로 각 스레드마다 별도의 `TgzReader` 객체를 인스턴스화하여 사용할 수 있습니다.

**Q: 추출된 이메일을 다른 시스템과 어떻게 통합할 수 있습니까?**  
A: 각 `MailMessage`를 EML, JSON 또는 XML 형식으로 `SaveOptions`를 사용해 저장한 뒤, 해당 파일을 다운스트림 파이프라인에 전달합니다.

## 리소스
- **문서**: [Aspose.Email for Java Documentation](https://reference.aspose.com/email/java/)
- **다운로드**: [Aspose Email Releases](https://releases.aspose.com/email/java/)
- **구매**: [Buy Aspose Products](https://purchase.aspose.com/buy)
- **무료 체험**: [Aspose Email Free Trials](https://releases.aspose.com/email/java/)
- **임시 라이선스**: [Obtain a Temporary License](https://purchase.aspose.com/temporary-license/)
- **지원**: 질문이나 도움이 필요하면 [Aspose Support Forum](https://forum.aspose.com/c/email/10)을 방문하십시오.

---

**마지막 업데이트:** 2026-06-18  
**테스트 환경:** Aspose.Email for Java 25.4  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Email Java용 이메일 파싱 및 분석 튜토리얼](/email/java/email-parsing-analysis/)
- [Aspose.Email for Java를 사용한 이메일 첨부 파일 추출](/email/java/advanced-email-attachments/)
- [Aspose.Email for Java로 EML 이메일을 효율적으로 로드 및 표시](/email/java/email-message-operations/load-display-emml-emails-aspose-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```java
import com.aspose.email.TgzReader;
import com.aspose.email.MailMessage;
```

```java
String storagePath = "YOUR_DOCUMENT_DIRECTORY/ZimbraSample.tgz";
```

```java
TgzReader reader = new TgzReader(storagePath);
```

```java
try {
    while (reader.readNextMessage()) { // Continue until all messages are read.
        String directoryName = reader.getCurrentDirectory(); // Get the current email's storage path.
        MailMessage eml = reader.getCurrentMessage(); // Retrieve the current email message.

        // At this point, 'directoryName' and 'eml' hold crucial details of each email.
    }
} finally {
    reader.dispose(); // Always dispose of resources to prevent memory leaks.
}
```

```java
import com.aspose.email.examples.Utils;

public class ExampleUtils {
    public static String getSharedDataDir(Class<?> cls) {
        return "YOUR_DOCUMENT_DIRECTORY/"; // Set your shared data directory path.
    }
}
```

```java
String dataDir = ExampleUtils.getSharedDataDir(ExampleUtils.class) + "email/";
// 'dataDir' now points to a specific subdirectory for email-related operations.
```