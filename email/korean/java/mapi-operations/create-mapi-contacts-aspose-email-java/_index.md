---
"date": "2025-05-29"
"description": "Aspose.Email for Java를 사용하여 MAPI 연락처를 효율적으로 생성하고 관리하는 방법을 알아보세요. 이 가이드에서는 기본적인 연락처 생성부터 전문 정보 추가를 포함한 세부적인 관리까지 모든 것을 다룹니다."
"title": "Aspose.Email을 사용하여 Java에서 MAPI 연락처 만들기 - 단계별 가이드"
"url": "/ko/java/mapi-operations/create-mapi-contacts-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email을 사용하여 Java에서 MAPI 연락처를 만드는 방법: 단계별 가이드

## 소개

강력한 이메일 및 주소록 통합이 필요한 애플리케이션의 경우 연락처 관리가 필수적입니다. 이 포괄적인 가이드는 Java에서 강력한 Aspose.Email 라이브러리를 사용하여 MAPI(메시징 애플리케이션 프로그래밍 인터페이스) 연락처를 생성하는 방법을 보여줍니다. 이 튜토리얼을 따라 하면 연락처 생성을 자동화하고, 데이터 구성을 개선하고, Java 애플리케이션에 연락처 관리를 원활하게 통합할 수 있습니다.

**배울 내용:**
- 기본 및 상세 MAPI 연락처 만들기
- Aspose.Email for Java를 사용하여 전문 정보, 주소 및 이메일을 관리하세요.
- 연락처를 효율적으로 저장하기 위해 PST(개인 저장 테이블) 파일을 설정하세요.

## 필수 조건

연락처 생성에 들어가기 전에 다음 사항이 있는지 확인하세요.

### 필수 라이브러리:
- Java 라이브러리용 Aspose.Email(버전 25.4 이상)

### 환경 설정 요구 사항:
- JDK 버전 16 이상
- 원하는 IDE(IntelliJ IDEA, Eclipse 등)

### 지식 전제 조건:
Java 프로그래밍에 대한 기본적인 이해와 타사 라이브러리 처리에 대한 익숙함이 필요합니다.

## Java용 Aspose.Email 설정

시작하려면 프로젝트에 Aspose.Email 라이브러리를 포함하세요. Maven을 사용하는 경우 다음 종속성을 프로젝트에 추가하세요. `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이센스 취득 단계:
- **무료 체험:** 평가판을 다운로드하세요 [Aspose 웹사이트](https://releases.aspose.com/email/java/) 그 특징을 알아보세요.
- **임시 면허:** 임시 면허 신청은 다음을 통해 신청하세요. [구매 페이지](https://purchase.aspose.com/temporary-license/).
- **구입:** 해당 회사의 전체 라이센스를 구매하는 것을 고려하세요. [구매 페이지](https://purchase.aspose.com/buy) Aspose.Email이 귀하의 요구 사항을 충족하는지 확인하세요.

### 기본 초기화:
설치가 완료되면 Java 애플리케이션에서 Aspose.Email을 초기화하여 MAPI 연락처를 만들고 관리하세요.

## 구현 가이드

여기서는 기본 연락처 생성, 전문적인 정보 포함, 포괄적인 세부 정보 관리라는 세 가지 주요 기능에 대해 다루겠습니다.

### 기본 MAPI 연락처 만들기

#### 개요
이 기능을 사용하면 이름, 성, 이메일 주소만으로 간단한 연락처를 만들 수 있어 최소한의 데이터만 필요한 애플리케이션에 적합합니다.

#### 구현 단계

##### 1단계: 필요한 클래스 가져오기
```java
import com.aspose.email.MapiContact;
```

##### 2단계: MAPI 연락처 만들기
기본 MAPI 연락처를 만드는 방법은 다음과 같습니다.
```java
public static MapiContact createBasicMapiContact(String firstName, String lastName, String emailAddress) {
    return new MapiContact(firstName + " " + lastName, emailAddress);
}
```
**설명:** 이 방법은 다음을 초기화합니다. `MapiContact` 제공된 이름과 이메일 주소를 사용하여 개체를 만듭니다. 연락처는 최소한의 정보로 저장됩니다.

### 전문 정보를 사용하여 MAPI 연락처 만들기

#### 개요
회사 이름, 직함, 전화번호 등 전문적인 세부 정보를 추가하여 연락처를 강화하세요.

#### 구현 단계

##### 1단계: 추가 클래스 가져오기
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
```

##### 2단계: 전문가 세부 정보를 사용하여 MAPI 연락처 만들기
전문적인 정보를 포함하는 방법은 다음과 같습니다.
```java
public static MapiContact createProfessionalMapiContact(String firstName, String middleName, String lastName,
        String company, String jobTitle, String businessPhone, String mobilePhone) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getTelephones().setBusinessTelephoneNumber(businessPhone);
    contact.getTelephones().setMobileTelephoneNumber(mobilePhone);
    return contact;
}
```
**설명:** 이 방법은 다음을 초기화합니다. `MapiContact` 회사명과 직책을 포함한 자세한 정보를 포함하는 객체입니다. 또한 업무 관련 전화번호도 설정합니다.

### 자세한 정보를 사용하여 MAPI 연락처 만들기

#### 개요
실제 주소, 이메일 정보, 성별 속성을 추가하여 포괄적인 연락처를 만들고 세부적인 관리를 수행합니다.

#### 구현 단계

##### 1단계: 추가 클래스 가져오기
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
import com.aspose.email.MapiContactElectronicAddress;
import com.aspose.email.MapiContactGender;
```

##### 2단계: 자세한 MAPI 연락처 만들기
자세한 연락처를 만드는 방법은 다음과 같습니다.
```java
public static MapiContact createDetailedMapiContact(String firstName, String middleName, String lastName,
        MapiContactGender gender, String company, String jobTitle, String email, String workAddress) {
    MapiContact contact = new MapiContact();
    contact.setNameInfo(new MapiContactNamePropertySet(firstName, middleName, lastName));
    contact.getPersonalInfo().setGender(gender);
    contact.setProfessionalInfo(new MapiContactProfessionalPropertySet(company, jobTitle));
    contact.getPhysicalAddresses().getWorkAddress().setAddress(workAddress);
    contact.getElectronicAddresses().setEmail1(new MapiContactElectronicAddress(email));
    return contact;
}
```
**설명:** 이 방법은 다음을 초기화합니다. `MapiContact` 성별과 실제 주소를 포함한 자세한 정보를 제공합니다. 모든 관련 데이터가 수집되도록 보장합니다.

### PST 파일 생성 및 연락처 추가

#### 개요
중앙에서 관리할 수 있도록 여러 연락처를 PST(개인 저장 테이블) 파일에 저장합니다.

#### 구현 단계

##### 1단계: 필요한 클래스 가져오기
```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.MapiContact;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;
```

##### 2단계: PST 만들기 및 연락처 추가
PST 파일을 만들고 연락처를 추가하는 방법은 다음과 같습니다.
```java
public static void createPstAndAddContacts(MapiContact[] contacts) {
    String pstPath = "YOUR_OUTPUT_DIRECTORY/MapiContactToPST_out.pst";
    PersonalStorage pst = PersonalStorage.create(pstPath, FileFormatVersion.Unicode);
    FolderInfo contactFolder = pst.createPredefinedFolder("Contacts", StandardIpmFolder.Contacts);
    for (MapiContact contact : contacts) {
        contactFolder.addMapiMessageItem(contact);
    }
}
```
**설명:** 이 방법은 PST 파일을 생성하고 여러 개를 추가합니다. `MapiContact` 객체를 "연락처" 폴더로 구성하여 해당 객체를 그 안에 넣습니다.

## 실제 응용 프로그램

1. **CRM 시스템:** 고객 관계 관리 소프트웨어에서 연락처 생성을 자동화합니다.
2. **이메일 클라이언트:** 강력한 연락처 관리 기능을 통합하여 이메일 클라이언트를 향상시킵니다.
3. **주소록 동기화:** 이 기능을 사용하면 다양한 플랫폼과 기기에서 연락처를 동기화할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}