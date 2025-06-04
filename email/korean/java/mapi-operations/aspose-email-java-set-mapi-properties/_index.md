---
"date": "2025-05-29"
"description": "Aspose.Email for Java를 사용하여 MAPI 메시지의 여러 속성을 효율적으로 관리하는 방법을 알아보세요. 이 가이드에서는 float, double, long 등의 데이터 유형을 설정하는 방법을 다룹니다."
"title": "Aspose.Email을 사용하여 Java에서 여러 MAPI 속성 설정하기 - 포괄적인 가이드"
"url": "/ko/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email을 사용하여 Java에서 여러 MAPI 속성 설정: 포괄적인 가이드

## 소개

MAPI 메시지 속성을 효과적으로 관리하는 것은 Java 애플리케이션의 성능을 향상시키는 데 매우 중요합니다. Aspose.Email for Java를 사용하면 float, double, long, short, boolean 및 사용자 지정 속성과 같은 여러 속성을 원활하게 설정할 수 있습니다. 이 가이드에서는 이를 위한 다양한 방법을 안내합니다.

**배울 내용:**
- Aspose.Email Java를 사용하여 MAPI 메시지에 여러 속성 설정
- 다양한 부동산 유형과 그 용도 이해
- 구현을 위한 실제 코드 예제

먼저 전제 조건부터 살펴보겠습니다.

## 필수 조건

따라오려면 다음 사항이 있는지 확인하세요.
- **자바 개발 키트(JDK):** JDK 8 이상이 설치되어 있습니다.
- **Aspose.Email 라이브러리:** 버전 25.4를 권장합니다.
- **Maven 설정:** 종속성 관리를 위해 IDE에 Maven을 구성해야 합니다.

### 필수 라이브러리

Aspose.Email을 종속성으로 포함합니다. `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 라이센스 취득
- **무료 체험:** 무료 체험판을 통해 기능을 살펴보세요.
- **임시 면허:** 제한 없이 장기 테스트를 위해 얻으세요.
- **구입:** 귀하의 필요에 맞는다면 구매를 고려해 보세요.

## Java용 Aspose.Email 설정

개발 환경에서 Aspose.Email이 올바르게 구성되었는지 확인하세요.
1. **가져오기 종속성:** Maven 종속성을 해결합니다.
2. **라이센스 설정:**
   - 라이센스 파일을 다운로드하세요 [아스포제](https://purchase.aspose.com/buy).
   - 다음을 사용하여 적용하세요.
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

설정이 완료되었으므로 다양한 속성을 설정하는 방법을 살펴보겠습니다.

## 구현 가이드

### 여러 개의 Float 속성 설정

float 속성을 설정하면 숫자 데이터를 효율적으로 저장할 수 있습니다.

#### 개요
이 기능은 Java용 Aspose.Email을 사용하여 여러 개의 float 값을 MAPI 메시지 속성으로 추가하는 방법을 보여줍니다.

#### 단계
1. **메시지 생성 및 초기화**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **목록에 부동 소수점 값 추가**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **고유 식별자로 속성 설정**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*설명:* 속성 태그 `0x23901004` 이 float 속성 집합을 식별합니다.

### 여러 개의 Double 속성 설정

Double 속성은 고정밀 부동 소수점 숫자를 저장합니다.

#### 개요
이 섹션에서는 여러 개의 double 값을 MAPI 메시지 속성으로 저장하는 방법을 보여줍니다.

#### 단계
1. **메시지 초기화**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **이중 값 채우기**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **속성 태그에 할당**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### 여러 APPTIME 속성 설정

APPTIME 속성은 시간 기간을 효율적으로 저장합니다.

#### 개요
이 기능은 시간 표현에 배정밀도 숫자를 사용하는 방법을 보여줍니다.

#### 단계
1. **메시지 객체 생성**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **시간 값 추가**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **속성 설정**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### 여러 개의 긴 속성 설정

긴 속성은 큰 정수에 이상적입니다.

#### 개요
이 기능은 메시지에서 여러 개의 긴 정수 값을 설정하는 데 중점을 둡니다.

#### 단계
1. **MAPI 메시지 초기화**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **긴 값 추가**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **속성 태그 정의**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### 여러 개의 짧은 속성 설정

짧은 속성은 작은 정수 데이터를 효율적으로 저장합니다.

#### 개요
이 가이드에서는 짧은 정수를 메시지 속성으로 설정하는 방법을 보여줍니다.

#### 단계
1. **메시지 초기화**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **짧은 값 추가**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **속성 태그 지정**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### 여러 부울 속성 설정

부울 속성은 참/거짓 상태를 저장합니다.

#### 개요
메시지에 여러 개의 부울 값을 설정하는 방법을 알아보세요.

#### 단계
1. **메시지 객체 생성**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **부울 값 추가**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **식별자를 사용하여 속성 설정**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Null 속성 설정

속성을 명시적으로 null로 설정하는 것이 유용할 수 있습니다.

#### 개요
이 섹션에서는 속성에 null 값을 할당하는 방법을 보여줍니다.

#### 단계
1. **메시지 초기화**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Null 속성 할당**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### 사용자 지정 ID 및 UUID를 사용하여 명명된 긴 속성 설정

복잡한 시나리오의 경우 명명된 속성을 설정합니다.

#### 개요
이 기능은 사용자 정의 식별자와 UUID로 긴 속성을 설정하는 방법을 보여줍니다.

#### 단계
1. **메시지 초기화**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **긴 값 추가**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **속성 만들기 및 매핑**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### 이름으로 사용자 정의 속성 설정

사용자 정의 속성은 식별을 더 쉽게 하기 위해 이름을 지정할 수 있습니다.

#### 개요
이 가이드에서는 사용자 정의 이름의 속성을 설정하는 방법을 보여줍니다.

#### 단계
1. **메시지 객체 초기화**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **사용자 정의 속성 정의**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### 속성 설정 및 유효성 검사

속성이 올바르게 설정되었는지 확인하는 것이 중요합니다.

#### 개요
이 섹션에서는 MAPI 메시지에서 여러 속성을 설정하고 검증하는 방법을 다룹니다.

#### 단계
1. **속성 설정**
   이전 예시를 따라 속성을 설정합니다.
2. **속성 검증**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## 결론

이 가이드에서는 Aspose.Email for Java를 사용하여 MAPI 메시지의 여러 속성을 관리하는 포괄적인 방법을 제시했습니다. 다음 단계를 따르면 애플리케이션 내에서 다양한 데이터 유형을 효율적으로 저장하고 관리할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}