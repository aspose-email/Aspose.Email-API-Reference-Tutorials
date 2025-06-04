---
"date": "2025-05-29"
"description": "Java için Aspose.Email kullanarak MAPI mesajlarındaki birden fazla özelliği etkili bir şekilde nasıl yöneteceğinizi öğrenin. Bu kılavuz, float, double, long ve daha fazla türün ayarlanmasını kapsar."
"title": "Aspose.Email ile Java'da Çoklu MAPI Özelliklerini Ayarlama&#58; Kapsamlı Bir Kılavuz"
"url": "/tr/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Email ile Çoklu MAPI Özellikleri Ayarlama: Kapsamlı Bir Kılavuz

## giriiş

MAPI ileti özelliklerini etkili bir şekilde yönetmek, Java uygulamalarınızı geliştirmek için çok önemlidir. Aspose.Email for Java ile float, double, long, short, boolean ve özel özellikler gibi birden fazla özelliği sorunsuz bir şekilde ayarlayabilirsiniz. Bu kılavuz, bunu başarmak için çeşitli yöntemlerde size yol gösterecektir.

**Ne Öğreneceksiniz:**
- Aspose.Email Java kullanarak MAPI mesajlarında birden fazla özelliği ayarlama
- Farklı mülk tiplerini ve kullanımlarını anlamak
- Uygulama için pratik kod örnekleri

Öncelikle ön koşulları ele alarak başlayalım.

## Ön koşullar

Takip edebilmek için şunlara sahip olduğunuzdan emin olun:
- **Java Geliştirme Kiti (JDK):** JDK 8 veya üzeri yüklü.
- **Aspose.E-posta Kütüphanesi:** 25.4 sürümü önerilir.
- **Maven Kurulumu:** Bağımlılık yönetimi için IDE'nizde Maven yapılandırılmalıdır.

### Gerekli Kütüphaneler

Aspose.Email'i bağımlılık olarak ekleyin `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Lisans Edinimi
- **Ücretsiz Deneme:** Özellikleri keşfetmek için ücretsiz denemeyle başlayın.
- **Geçici Lisans:** Sınırlama olmaksızın genişletilmiş testlere katılın.
- **Satın almak:** İhtiyaçlarınıza uygunsa satın almayı düşünün.

## Java için Aspose.Email Kurulumu

Aspose.Email'in geliştirme ortamınızda doğru şekilde yapılandırıldığından emin olun:
1. **İçe Aktarım Bağımlılıkları:** Maven bağımlılıklarını çözün.
2. **Lisans Ayarla:**
   - Lisans dosyasını indirin [Aspose](https://purchase.aspose.com/buy).
   - Bunu kullanarak uygulayın:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Kurulum tamamlandıktan sonra çeşitli özelliklerin nasıl ayarlanacağını inceleyelim.

## Uygulama Kılavuzu

### Çoklu Kayan Nokta Özelliklerini Ayarlama

Float özelliklerinin ayarlanması sayısal verilerin verimli bir şekilde depolanmasını sağlar:

#### Genel bakış
Bu özellik, Aspose.Email for Java kullanılarak MAPI mesaj özellikleri olarak birden fazla kayan nokta değerinin eklenmesini göstermektedir.

#### Adımlar
1. **Mesajı Oluşturun ve Başlatın**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Bir Listeye Kayan Noktalı Değerler Ekleme**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Özelliği Benzersiz Bir Tanımlayıcıyla Ayarlayın**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Açıklama:* Özellik etiketi `0x23901004` Bu float özellik kümesini tanımlar.

### Çoklu Çift Özellikleri Ayarlama

Çift özellikler yüksek hassasiyetli kayan nokta sayılarını depolar:

#### Genel bakış
Bu bölüm, birden fazla double değerinin MAPI mesaj özelliği olarak nasıl saklanacağını göstermektedir.

#### Adımlar
1. **Mesajı Başlat**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Çift Değerleri Doldur**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Özellik Etiketine Ata**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Birden Fazla APPTIME Özelliğini Ayarlama

APPTIME özellikleri zaman sürelerini verimli bir şekilde depolar:

#### Genel bakış
Bu özellik, zaman gösterimlerinde çift hassasiyetli sayıların kullanımını göstermektedir.

#### Adımlar
1. **Mesaj Nesnesi Oluştur**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Zaman Değerleri Ekle**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Özelliği Ayarla**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Çoklu Uzun Özellikleri Ayarlama

Uzun özellikler büyük tam sayılar için idealdir:

#### Genel bakış
Bu özellik, bir mesajda birden fazla uzun tamsayı değerinin ayarlanmasına odaklanır.

#### Adımlar
1. **MAPI Mesajını Başlat**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Uzun Değerler Ekle**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Özellik Etiketini Tanımla**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Çoklu Kısa Özellikleri Ayarlama

Kısa özellikler küçük tamsayı verilerini verimli bir şekilde depolar:

#### Genel bakış
Bu kılavuz, kısa tam sayıların mesaj özelliği olarak ayarlanmasını göstermektedir.

#### Adımlar
1. **Mesajı Başlat**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Kısa Değerler Ekle**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Özellik Etiketi Ata**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Çoklu Boolean Özelliklerini Ayarlama

Boolean özellikleri doğru/yanlış durumlarını depolar:

#### Genel bakış
Bir mesajda birden fazla Boole değerinin nasıl ayarlanacağını öğrenin.

#### Adımlar
1. **Mesaj Nesnesi Oluştur**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Boolean Değerleri Ekle**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Tanımlayıcı ile Özellik Ayarla**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Boş Bir Özellik Ayarlama

Bir özelliği açıkça null olarak ayarlamak yararlı olabilir:

#### Genel bakış
Bu bölüm bir özelliğe boş değer atamayı göstermektedir.

#### Adımlar
1. **Mesajı Başlat**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Boş Özellik Ata**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Özel Kimlik ve UUID ile Adlandırılmış Uzun Özellik Ayarlama

Karmaşık senaryolar için adlandırılmış özellikleri ayarlayın:

#### Genel bakış
Bu özellik, uzun bir özelliğin özel bir tanımlayıcı ve UUID ile ayarlanmasını gösterir.

#### Adımlar
1. **Mesajı Başlat**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Uzun Değerler Ekle**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Özellik Oluştur ve Haritala**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### İsimle Özel Özellik Ayarlama

Özel özellikler daha kolay tanımlanabilmesi için isimlendirilebilir:

#### Genel bakış
Bu kılavuz, özel adlandırılmış özelliklerin nasıl ayarlanacağını gösterir.

#### Adımlar
1. **Mesaj Nesnesini Başlat**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Özel Özelliği Tanımla**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Özellikleri Ayarlama ve Doğrulama

Özelliklerin doğru şekilde ayarlanması çok önemlidir:

#### Genel bakış
Bu bölüm MAPI mesajlarında birden fazla özelliğin ayarlanmasını ve doğrulanmasını ele almaktadır.

#### Adımlar
1. **Özellik Ayarla**
   Bir özelliği ayarlamak için önceki örnekleri izleyin.
2. **Özelliği Doğrula**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Çözüm

Bu kılavuz, Java için Aspose.Email kullanarak MAPI mesajlarındaki birden fazla özelliği yönetmeye yönelik kapsamlı bir yaklaşım sağlamıştır. Bu adımları izleyerek, uygulamalarınızda çeşitli veri türlerini verimli bir şekilde depolayabilir ve yönetebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}