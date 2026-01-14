---
date: '2025-12-17'
description: Aspose.Email for Java를 사용하여 Java에서 인라인 첨부 파일을 추출하고 Outlook MSG 파일을 읽는
  방법을 배워보세요. Outlook MSG 파일을 효율적으로 처리하기 위한 단계별 가이드.
keywords:
- extract inline attachments MSG Java
- handle Outlook email formats Java
- use Aspose.Email library for Java
title: Java – Aspose.Email을 사용한 MSG 파일의 인라인 첨부 파일 추출
url: /ko/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email을 사용하여 Java – MSG 파일에서 인라인 첨부 파일 추출

## 소개

Microsoft OutlookMSG 파일에서 **inline attachments java**를 추출해야 합니다. 올바른 것이 었습니다. 많은 개발자들이 Outlookmsgjava 파일을 읽는 데 어려움을 겪고 있는데, 형식이 내부에 삽입된 이미지와 문서를 숨기기 때문에 발생합니다. 이 튜토리얼에서는 Aspose.Email for Java 라이브러리를 사용하여 인라인 첨부 파일을 찾고, 크기를 지정하고, 저장하는 별도-준비 포함을 포함하여 안내합니다.

이 가이드를 종료하면 다음을 수행할 수 있습니다.

* Maven 프로젝트에 Aspose.Email for Java를 설정합니다.
* **Outlookmsgjava** 파일을 읽고 첨부 파일을 화면에서 확인합니다.
* 인라인 첨부 파일을 식별하고 디스크에 저장합니다.
* 처리 시 성능 최적화 모범 사례를 적용합니다.

## 빠른 답변
- **“인라인 첨부 파일”이란 무엇입니까?** 이메일 본문에 삽입된 첨부 파일(예: 내부 표시되는 이미지)입니다.
- **MSG 파일을 처리하는 클래스는 무엇입니까?** Java용 Aspose.Email.
- **라이센스가 필요합니까?** 평가용 베어링을 사용할 수 있으며, 영구 기능을 구매하면 사용 제한이 가능합니다.
- **여러 MSG 파일을 한 번에 처리할 수 있습니까?** 예 – 섀시를 배치하고 스레드 풀을 사용하면 확장성이 있습니다.
- **필요한 Java 버전은 무엇입니까?** JDK16 이상.

## "인라인 첨부 파일 추출 java"란 무엇입니까?

Java에서 인라인 첨부 파일을 추출한다는 것은 MSG 파일을 프로그래밍 방식으로, 첨부 파일 클러스터를 검색한 후, *인라인*으로 추출하는 항목만 추출하는 것을 의미합니다(일반 파일 첨부와 구분). 이메일의 표시 콘텐츠(예: 삽입된 로고 스크린샷)를 별도의 이미지 파일로 저장해야 할 때입니다.

## 이 작업에 Aspose.Email을 사용하는 이유는 무엇입니까?

Aspose.Email은 저수준 MAPI 구조를 추상화하고 간단하고 강력한 유형의 API를 제공합니다. 직접 바이너리 MSG 형식을 분석하고 비교했을 때 Aspose.Email은:

* 모든 MSG 변형(Unicode, RTF, HTML)을 지원합니다.
* 첨부 파일 데이터에 대한 데이터를 제공할 수 있는 속성을 제공합니다.
* 권한을 부여받은 권한을 가진 문서를 제공합니다.

## 전제 조건

이 튜토리얼을 따라 다음 단계에 따라야 합니다.

1. **라이브러리 및 종속성** 
* Aspose.Email for Java (최신 버전). 
* Maven(또는 Maven을 지원하는 IDE).

2. **런타임** 
* JDK16이 설치되어 있어야 합니다.

3. **기본 지식** 
* Java I/O 및 예외 처리에 대한 기본 기술.

## Java용 Aspose.Email 설정

`pom.xml`에 Aspose.Email 의존성을 추가합니다. 아래 스니펫은 원본 튜토리얼과 동일합니다.

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### 라이선스 취득 단계

* **무료 평가판:** Aspose 웹사이트에서 밀어얼 DLL/JAR을 다운로드합니다.
* **임시 라이선스:** 제한 없는 테스트를 위해 30일 평가를 요청합니다.
* **전체 구매:** 배포를 위해 영구 권한을 구매합니다.

## 구현 가이드

아래에서는 솔루션을 세 가지 핵심 기능으로 나눕니다. 각은 간단한 설명과 원본 코드 블록(정확히 유지) 기능을 포함합니다.

### 기능 1 – MSG 파일 로드

먼저 Outlook 메시지를 `MapiMessage`로 로드합니다.

```java
import com.aspose.email.MapiMessage;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
MapiMessage message = MapiMessage.fromFile(dataDir + "MSG file with RTF Formatting.msg");
```

### 기능 2 – 첨부 파일 검색

다음으로 전체 파일을 제출합니다.

```java
import com.aspose.email.MapiAttachmentCollection;

MapiAttachmentCollection attachments = message.getAttachments();
```

### 기능 3 – 인라인 첨부 파일 식별 및 저장

각 첨부 파일을 순회하면서 인라인 여부를 확인하고, 디스크에 저장합니다.

```java
for (Object untypedAttachment : attachments) {
    MapiAttachment attachment = (MapiAttachment) untypedAttachment;
    if (IsAttachmentInline(attachment)) {
        try {
            SaveAttachment(attachment, UUID.randomUUID().toString());
        } catch (IOException e) {
            // Handle exception
        }
    }
}
```

#### 유틸리티: 첨부 파일이 인라인인지 확인

헬퍼 메서드는 MAPI 속성을 검사하여 첨부 파일이 삽입된 내용입니다.

```java
import com.aspose.email.MapiAttachment;
import com.aspose.email.MapiObjectProperty;
import com.aspose.email.MapiProperty;

static boolean IsAttachmentInline(MapiAttachment attachment) {
    MapiObjectProperty objectData = attachment.getObjectData();
    if (objectData == null) return false;

    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("\u0003ObjInfo".equals(property.getName())) {
            byte[] data = property.getData();
            int odtPersist1 = data[1] << 8 | data[0];
            return (odtPersist1 & 0x40) == 0;
        }
    }
    return false;
}
```

#### 유틸리티: 인라인 첨부 파일 저장

인라인 첨부 파일의 내용을 파일 시스템에 파일로 기록합니다.

```java
import com.aspose.email.MapiAttachment;
import java.io.FileOutputStream;
import java.io.IOException;

static void SaveAttachment(MapiAttachment attachment, String fileName) throws IOException {
    for (Object prop : attachment.getObjectData().getProperties().getValues()) {
        MapiProperty property = (MapiProperty) prop;
        if ("Package".equals(property.getName())) {
            try (FileOutputStream fs = new FileOutputStream(fileName)) {
                fs.write(property.getData(), 0, property.getData().length);
            }
        }
    }
}
```

## 실제 적용

인라인 첨부 파일 추출은 다양한 실제 시나리오에서 유용합니다:

* **자동화된 이메일 처리** – 뉴스레터에서 이미지를 추출하여 분석에 활용합니다.
* **데이터 마이그레이션** – Exchange에서 다른 플랫폼으로 마이그레이션할 때 삽입된 컨텐츠를 이동합니다.
* **보관 솔루션** – 인라인 단편을 단편 저장하여 저장한 메시지의 대표도를 유지합니다.

## 성능 고려 사항

수많은 MSG 파일을 처리할 때 다음 팁을 기억하세요:

* **일괄 처리:** 메모리 군중을 방지하기 위해 파일을 관리할 수 있는 배치로 그룹화합니다.
* **리소스를 즉시 폐기하세요.** 스트림을 `try-with-resources`로늦고 가비지 컬렉터가 점점 줄어들도록 합니다.
* **병렬 실행:** 고정 크기의 `ExecutorService`를 분산하여 여러 추출 작업을 동시에 실행하는 CPU를 모델링합니다.

## 일반적인 문제 및 문제 해결

| 증상 | 가능한 원인 | 수정 |
|---------|--------------|-----|
| `attachment.getObjectData()`에서 `NullPointerException` 발생 | 메시지에 첨부 파일 데이터가 없습니다(예: MSG) | MSG 파일을 처리하기 위해 인증 또는 원시를 기록한 파일명을 기록합니다. |
| 남은 파일이 없어 손상될 수 있음 | 속성 이름(`"Package"`) 대 존재하는 오류 | 속성 이름이 MSG 실제 속성인지 확인하는지 확인합니다. 문자열은 Aspose.Email 문서에 등록되어 있습니다. |
| 습지 파일 관리 시 보호 패드 | 스트림을 종료하기 때문에 메모리 누수 발생 | 예시와 함께 `try-with-resources`를 사용하고 필요 시 JVM 힙을늘립니다. |

## 자주 묻는 질문

**Q: 최소 Aspose.Email 버전 요구 사항은 무엇입니까?**
A: 튜토리얼은 버전 25.4를 사용하지만 JDK16을 지원하는 24.x 이상이라면 모두 작동합니다.

**Q: 파일이 포함된 MSG 파일에 인라인 첨부 파일을 추출할 수 있습니까?**
A: 예, `MapiMessage`를 로드할 때 올바른 복호화를 제공하면 가능합니다.

**Q: 인라인 이미지와 일반 파일 애플리케이션을 어떻게 거대해?**
A: `IsAttachmentInline` 헬퍼를 사용합니다; 이 메서드는 인라인으로 연결 파일을 활성화하는 MAPI `ObjInfo` 인증을 확인합니다.

**Q: 인라인 첨부 파일의 원본 파일명을 사용할 방법이 있습니까?**
A: 샘플은 고유성을 위해 UUID를 생성하지만, 'attachment.getLongFileName()' 속성을 입력하려면 'SaveAttachment'를 호출할 수 있습니다.

**Q: 이 방법은 Linux/macOS에서도 Windows와 동일하게 동작하는건가요?**
A: 물론입니다—JDK만 설치해 주시면 Aspose.Email은 플랫폼에 있습니다.

## 참고 자료
- **문서:** [Aspose 이메일 문서](https://docs.aspose.com/email/java/)

---

**최종 업데이트:** 2025년 12월 17일
**테스트 환경:** Aspose.Email for Java 25.4 (JDK16)
**개발자:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}