---
"date": "2025-05-29"
"description": "Java için Aspose.Email ile MAPI kişilerini etkili bir şekilde nasıl oluşturacağınızı ve yöneteceğinizi öğrenin. Bu kılavuz, temel kişi oluşturmadan profesyonel bilgiler ekleme dahil olmak üzere ayrıntılı yönetime kadar her şeyi kapsar."
"title": "Aspose.Email Kullanarak Java'da MAPI Kişileri Oluşturma&#58; Adım Adım Kılavuz"
"url": "/tr/java/mapi-operations/create-mapi-contacts-aspose-email-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email Kullanarak Java'da MAPI Kişileri Nasıl Oluşturulur: Adım Adım Kılavuz

## giriiş

Kişileri yönetmek, sağlam e-posta ve adres defteri entegrasyonu gerektiren uygulamalar için olmazsa olmazdır. Bu kapsamlı kılavuz, Java'daki güçlü Aspose.Email kütüphanesini kullanarak MAPI (Mesajlaşma Uygulama Programlama Arayüzü) kişilerinin nasıl oluşturulacağını gösterir. Bu öğreticiyi izleyerek, kişi oluşturmayı otomatikleştirecek, veri organizasyonunu geliştirecek ve kişi yönetimini Java uygulamalarınıza sorunsuz bir şekilde entegre edeceksiniz.

**Ne Öğreneceksiniz:**
- Temel ve detaylı MAPI kişileri oluşturun
- Profesyonel bilgileri, adresleri ve e-postaları Aspose.Email for Java ile yönetin
- Kişileri verimli bir şekilde depolamak için Kişisel Depolama Tablosu (PST) dosyası ayarlayın

## Ön koşullar

İletişim kurmaya başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler:
- Aspose.Email for Java kütüphanesi (Sürüm 25.4 veya üzeri)

### Çevre Kurulum Gereksinimleri:
- JDK sürüm 16 veya üzeri
- Tercih ettiğiniz bir IDE (IntelliJ IDEA, Eclipse, vb.)

### Bilgi Ön Koşulları:
Java programlama konusunda temel bilgi ve üçüncü parti kütüphaneleri kullanma konusunda aşinalık.

## Java için Aspose.Email Kurulumu

Başlamak için projenize Aspose.Email kütüphanesini ekleyin. Maven kullanıyorsanız, aşağıdaki bağımlılığı projenize ekleyin `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Alma Adımları:
- **Ücretsiz Deneme:** Deneme sürümünü şu adresten indirin: [Aspose web sitesi](https://releases.aspose.com/email/java/) Özelliklerini keşfetmek için.
- **Geçici Lisans:** Geçici lisans için başvuruda bulunun [satın alma sayfası](https://purchase.aspose.com/temporary-license/).
- **Satın almak:** Tam lisansı onlardan satın almayı düşünün [satın alma sayfası](https://purchase.aspose.com/buy) Aspose.Email ihtiyaçlarınızı karşılıyorsa.

### Temel Başlatma:
Kurulumdan sonra, MAPI kişilerini oluşturmaya ve yönetmeye başlamak için Java uygulamanızda Aspose.Email'i başlatın.

## Uygulama Kılavuzu

Üç temel özelliği ele alacağız: temel iletişim oluşturma, profesyonel bilgi ekleme ve kapsamlı ayrıntı yönetimi.

### Temel bir MAPI Kişisi Oluşturma

#### Genel bakış
Bu özellik, minimum veri gerektiren uygulamalar için uygun olup, sadece ad, soyad ve e-posta adresiyle basit kişiler oluşturmanıza olanak tanır.

#### Uygulama Adımları

##### Adım 1: Gerekli Sınıfları İçe Aktarın
```java
import com.aspose.email.MapiContact;
```

##### Adım 2: MAPI Kişisini Oluşturun
Temel bir MAPI kişisi oluşturma yöntemi şöyledir:
```java
public static MapiContact createBasicMapiContact(String firstName, String lastName, String emailAddress) {
    return new MapiContact(firstName + " " + lastName, emailAddress);
}
```
**Açıklama:** Bu yöntem bir `MapiContact` sağlanan ad ve e-posta adresini kullanarak nesne. İletişim, asgari bilgiyle saklanır.

### Profesyonel Bilgilerle MAPI İrtibat Kişisi Oluşturma

#### Genel bakış
Şirket adı, iş ünvanı ve telefon numaraları gibi profesyonel bilgiler ekleyerek iletişiminizi güçlendirin.

#### Uygulama Adımları

##### Adım 1: Ek Sınıfları İçe Aktar
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
```

##### Adım 2: Profesyonel Ayrıntılarla MAPI İrtibatını Oluşturun
Profesyonel bilgilerin nasıl ekleneceğini şu şekilde açıklayabiliriz:
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
**Açıklama:** Bu yöntem bir `MapiContact` Şirket adı ve iş ünvanı dahil olmak üzere genişletilmiş ayrıntılara sahip nesne. Ayrıca iş ile ilgili telefon numaralarını da ayarlar.

### Ayrıntılı Bilgilerle MAPI İrtibat Kişisi Oluşturma

#### Genel bakış
Ayrıntılı yönetim için fiziksel adresler, e-posta bilgileri ve cinsiyet özellikleri ekleyerek kapsamlı kişiler oluşturun.

#### Uygulama Adımları

##### Adım 1: Ek Sınıfları İçe Aktar
```java
import com.aspose.email.MapiContactNamePropertySet;
import com.aspose.email.MapiContactProfessionalPropertySet;
import com.aspose.email.MapiContactTelephonePropertySet;
import com.aspose.email.MapiContactElectronicAddress;
import com.aspose.email.MapiContactGender;
```

##### Adım 2: Ayrıntılı bir MAPI İletişimi Oluşturun
Ayrıntılı bir iletişim bilgisi oluşturmanın yolu şöyledir:
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
**Açıklama:** Bu yöntem bir `MapiContact` cinsiyet ve fiziksel adresler dahil olmak üzere ayrıntılı bilgilerle. Tüm ilgili verilerin yakalanmasını sağlar.

### PST Dosyası Oluşturma ve Kişileri Ekleme

#### Genel bakış
Merkezi yönetim için birden fazla kişiyi Kişisel Depolama Tablosu (PST) dosyasında saklayın.

#### Uygulama Adımları

##### Adım 1: Gerekli Sınıfları İçe Aktarın
```java
import com.aspose.email.FileFormatVersion;
import com.aspose.email.FolderInfo;
import com.aspose.email.MapiContact;
import com.aspose.email.PersonalStorage;
import com.aspose.email.StandardIpmFolder;
```

##### Adım 2: PST Oluşturun ve Kişileri Ekleyin
İşte bir PST dosyası oluşturma ve kişileri ekleme yöntemi:
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
**Açıklama:** Bu yöntem bir PST dosyası oluşturur ve birden fazla ekler `MapiContact` Nesneleri içine yerleştirip "Kişiler" klasörü altında düzenleyin.

## Pratik Uygulamalar

1. **CRM Sistemleri:** Müşteri ilişkileri yönetimi yazılımında iletişim oluşturmayı otomatikleştirin.
2. **E-posta İstemcileri:** Güçlü iletişim yönetimi özelliklerini entegre ederek e-posta istemcilerinizi geliştirin.
3. **Adres Defteri Senkronizasyonu:** Bu işlevi kullanarak kişileri farklı platformlar ve cihazlar arasında senkronize edebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}