---
"date": "2025-05-30"
"description": "Aspose.Email for .NET을 사용하여 PST 파일을 로드하고 MAPI 속성을 사용자 지정하여 이메일 데이터를 효과적으로 관리하는 방법을 알아보세요. 지금 바로 .NET 애플리케이션을 개선하세요."
"title": "마스터 이메일 관리&#58; Aspose.Email .NET을 사용하여 PST 파일 로드 및 MAPI 속성 사용자 지정"
"url": "/ko/net/email-message-operations/aspose-email-net-load-pst-customize-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 마스터 이메일 관리: Aspose.Email .NET을 사용하여 PST 파일 로드 및 MAPI 속성 사용자 지정

## 소개

대용량 PST 파일을 처리하거나 사용자 지정 MAPI 속성 구성이 필요할 때 이메일 관리를 간소화하고 싶으신가요? Aspose.Email for .NET을 사용하면 이러한 작업이 훨씬 간편해집니다. 이 튜토리얼에서는 Aspose.Email을 사용하여 PST 파일을 로드하고 MAPI 메시지 속성을 사용자 지정하여 .NET 애플리케이션과의 원활한 통합을 보장하는 방법을 안내합니다.

**배울 내용:**
- 받은 편지함 폴더에 접근하기 위해 PST 파일을 로드합니다.
- MAPI 메시지에 사용자 정의 속성을 만들고 추가합니다.
- 다양한 개발 환경에서 .NET용 Aspose.Email 설정하기.

구현에 들어가기 전에 전제 조건을 설정하는 것부터 시작해 보겠습니다.

## 필수 조건

모든 필수 종속성이 포함된 환경이 준비되었는지 확인하세요.

### 필수 라이브러리
- **.NET용 Aspose.Email**: PST 파일 및 MAPI 속성 작업에 필수적입니다. 버전 21.x 이상을 사용하세요.

### 환경 설정
- **개발 도구**: Visual Studio(2017 이상)가 컴퓨터에 설치되어 있어야 합니다.

### 지식 전제 조건
- C# 프로그래밍에 대한 기본적인 이해.
- .NET 개발 관행에 익숙함.

필수 구성 요소를 충족했으므로 이제 프로젝트에서 .NET용 Aspose.Email을 설정해 보겠습니다.

## .NET용 Aspose.Email 설정

Aspose.Email 기능을 활용하려면 다음과 같이 .NET 프로젝트에 추가하세요.

### 설치 옵션
- **.NET CLI 사용:**
  ```bash
  dotnet add package Aspose.Email
  ```

- **Visual Studio에서 패키지 관리자 사용:**
  ```
  Install-Package Aspose.Email
  ```

- **NuGet 패키지 관리자 UI**"Aspose.Email"을 검색하여 인터페이스를 통해 최신 버전을 직접 설치하세요.

### 라이센스 취득 단계
Aspose.Email의 모든 기능에 액세스하려면 라이선스를 취득하세요.
- **무료 체험**: 임시면허증으로 테스트 가능 [여기](https://purchase.aspose.com/temporary-license/).
- **구입**: 지속적인 사용을 위해서는 다음을 통해 라이센스를 구매하세요. [Aspose 웹사이트](https://purchase.aspose.com/buy).

### 기본 초기화
설치하고 라이선스를 받은 후 프로젝트에서 Aspose.Email을 초기화합니다.
```csharp
// .NET용 Aspose.Email 초기화
class Program
{
    static void Main(string[] args)
    {
        License license = new License();
        license.SetLicense("path_to_your_license.lic");
    }
}
```

## 구현 가이드
이제 모든 것이 설정되었으므로 주요 기능을 구현해 보겠습니다.

### 기능 1: PST 로드 및 받은 편지함 폴더 액세스
이 기능은 Aspose.Email for .NET을 사용하여 PST 파일을 로드하고 '받은 편지함' 폴더에 액세스하는 방법을 보여줍니다.

#### 단계별 구현
**개요:**
PST 파일을 로드하면 이메일 데이터를 프로그래밍 방식으로 조작할 수 있습니다. 여기에서는 받은 편지함 폴더에 접근하는 방법을 중점적으로 살펴보겠습니다.

```csharp
using System;
using Aspose.Email.Storage.Pst;

class Program
{
    static void Main(string[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY\Outlook.pst";
        using (PersonalStorage personalStorage = PersonalStorage.FromFile(dataDir))
        {
            // PST 파일 내의 '받은 편지함' 폴더에 접근하세요
            FolderInfo testFolder = personalStorage.RootFolder.GetSubFolder("Inbox");
        }
    }
}
```
**설명:**
- `PersonalStorage.FromFile`: 지정된 디렉토리에서 PST 파일을 로드합니다.
- `GetSubFolder("Inbox")`: 추가 작업을 위해 받은 편지함 폴더를 검색합니다.

### 기능 2: MAPI 메시지에 사용자 정의 속성 만들기 및 추가
MAPI 속성을 사용자 지정하면 맞춤형 이메일 메타데이터 관리가 가능합니다. 이 기능은 메시지에 사용자 지정 속성을 만들고 추가하는 방법을 보여줍니다.

#### 단계별 구현
**개요:**
사용자 정의 속성을 만들면 이메일과 함께 추가 정보를 저장할 수 있어 데이터 구성 및 검색이 향상됩니다.

```csharp
using System;
using System.Text;
using Aspose.Email.Mapi;

// 다양한 유형으로 사용자 정의 속성 정의
class Program
{
    static void Main(string[] args)
    {
        MapiPropertyCollection newProperties = new MapiPropertyCollection();

        // 표준 속성(예: 조직 이메일 주소)을 추가합니다.
        MapiProperty property = new MapiProperty(MapiPropertyTag.PR_ORG_EMAIL_ADDR_W, Encoding.Unicode.GetBytes("test_address@org.com"));
        newProperties.Add(property.Tag, property);

        // 사용자 지정 명명된 속성을 만들고 추가합니다.
        MapiProperty namedProperty1 = new MapiNamedProperty(GenerateNamedPropertyTag(0, MapiPropertyType.PT_LONG), "ITEM_ID\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}