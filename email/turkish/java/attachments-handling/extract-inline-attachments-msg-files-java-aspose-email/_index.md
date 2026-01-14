---
date: '2025-12-17'
description: Java için Aspose.Email kullanarak satır içi ekleri nasıl çıkaracağınızı
  ve Outlook MSG dosyalarını nasıl okuyacağınızı öğrenin. Outlook MSG dosyalarını
  verimli bir şekilde işlemek için adım adım rehber.
keywords:
- extract inline attachments MSG Java
- handle Outlook email formats Java
- use Aspose.Email library for Java
title: Java ile Satır İçi Ekleri Çıkarma – Aspose.Email ile MSG Dosyaları
url: /tr/java/attachments-handling/extract-inline-attachments-msg-files-java-aspose-email/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Email Kullanarak Java – MSG Dosyalarından Satır İçi Ekleri Çıkarma

## Giriş

Microsoft OutlookMSG dosyalarından **satır içi ekleri (Java) ayıklamanız** gerekiyorsa, doğru yerdesiniz. Birçok geliştirici, Outlookmsgjava dosyalarını okumakta zorlanıyor çünkü bu format, mesaj gövdesinin içine gömülü resimleri ve belgeleri gizliyor. Bu eğitimde, satır içi ekleri bulmak, tanımlamak ve kaydetmek için Java için Aspose.Email kütüphanesini kullanan temiz, üretime hazır bir çözümü adım adım inceleyeceğiz.

Bu kılavuzun sonunda şunları yapabileceksiniz:

* Bir Maven projesinde Java için Aspose.Email'i kurmak.

* **Outlookmsgjava** dosyalarını okumak ve eklerini listelemek.

* Hangi eklerin satır içi olduğunu tespit etmek ve bunları diske yazmak.

* Toplu işlem için performans en iyi uygulamalarını uygulamak.

## Hızlı Cevaplar
- **“Satır içi ek” ne anlama geliyor?** E-posta gövdesine yerleştirilmiş bir ek (örneğin, mesaj içinde görüntülenen resimler).

- **MSG dosyalarını hangi kütüphane işliyor?** Java için Aspose.Email.

- **Lisansa ihtiyacım var mı?** Deneme sürümü değerlendirme için yeterlidir; kalıcı lisans kullanım sınırlarını kaldırır.

- **Birçok MSG dosyasını aynı anda işleyebilir miyim?** Evet – mantığı gruplandırın ve ölçeklenebilirlik için iş parçacığı havuzlarını kullanın.

- **Hangi Java sürümü gereklidir?** JDK16 veya sonrası.

## Java'da “satır içi ekleri ayıklama” nedir?

Java'da satır içi ekleri ayıklamak, programatik olarak bir MSG dosyasını açmak, ek koleksiyonunu taramak ve yalnızca *satır içi* olarak işaretlenmiş öğeleri (normal dosya eklerinin aksine) ayıklamak anlamına gelir. Bu, e-postanın görsel içeriğinin (örneğin, gömülü logolar veya ekran görüntüleri) ayrı resim dosyaları olarak kaydedilmesi gerektiğinde önemlidir.

## Bu görev için neden Aspose.Email kullanmalısınız?

Aspose.Email, düşük seviyeli MAPI yapılarını soyutlayarak size basit, güçlü tipli bir API sunar. İkili MSG formatını kendiniz ayrıştırmaya çalışmakla karşılaştırıldığında, Aspose.Email:

* Tüm MSG varyantlarını (Unicode, RTF, HTML) işler.

* Ek meta verileri için güvenilir özellik erişimi sağlar.

* Dahili lisans kontrolleri ve kapsamlı dokümantasyon sunar.

## Önkoşullar

İlerlemeyi takip etmek için şunlara sahip olduğunuzdan emin olun:

1. **Kütüphaneler ve Bağımlılıklar**

* Aspose.Email for Java (en son sürüm).

* Maven (veya Maven desteği olan bir IDE).

2. **Çalışma Ortamı**

* JDK16 veya daha yenisi kurulu.

3. **Temel Bilgi**

* Java G/Ç ve istisna işleme konusunda bilgi sahibi olmak.

## Java için Aspose.Email Kurulumu

`pom.xml` dosyanıza Aspose.Email bağımlılığını ekleyin. Aşağıdaki kod parçası orijinal eğitimden değiştirilmemiştir.

```xml
<dependency>
  <groupId>com.aspose</groupId>
  <artifactId>aspose-email</artifactId>
  <version>25.4</version>
  <classifier>jdk16</classifier>
</dependency>
```

### Lisans Edinme Adımları

* **Ücretsiz Deneme:** Aspose web sitesinden deneme DLL/JAR dosyasını indirin.

* **Geçici Lisans:** Sınırsız test için 30 günlük değerlendirme lisansı talep edin.

* **Tam Satın Alma:** Üretim dağıtımları için kalıcı bir lisans edinin.

## Uygulama Kılavuzu

Aşağıda çözümü üç odaklı özelliğe ayırıyoruz. Her özellik, kısa bir açıklama ve ardından orijinal kod bloğunu (tam olarak korunmuş şekilde) içerir.

### Özellik 1 – MSG Dosyasını Yükleme

Öncelikle, Outlook mesajını bir `MapiMessage` nesnesine yükleyin.

```java
import com.aspose.email.MapiMessage;

String dataDir = "YOUR_DOCUMENT_DIRECTORY/email/";
MapiMessage message = MapiMessage.fromFile(dataDir + "MSG file with RTF Formatting.msg");
```

### Özellik 2 – Ekleri Alma

Ardından, mesajdan tüm ek koleksiyonunu çekin.

```java
import com.aspose.email.MapiAttachmentCollection;

MapiAttachmentCollection attachments = message.getAttachments();
```

### Özellik 3 – Satır İçi Ekleri Tanımlama ve Kaydetme

Her bir eki döngüye alın, satır içi olup olmadığını kontrol edin ve ardından diske yazın.

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

#### Yardımcı Program: Bir Ekin Satır İçi Olup Olmadığını Belirleme

Yardımcı yöntem, bir ekin gömülü olup olmadığına karar vermek için MAPI özelliklerini inceler.

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

#### Yardımcı Program: Satır İçi Eki Kaydet

Satır içi ekin ikili içeriğini yerel dosya sistemindeki bir dosyaya yazar.

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

## Pratik Uygulamalar

Satır içi ekleri ayıklamak birçok gerçek dünya senaryosunda faydalıdır:

* **Otomatik E-posta İşleme** – Analiz için bültenlerden görselleri çekin.

* **Veri Taşıma** – Exchange'den başka bir platforma geçiş yaparken gömülü içeriği taşıyın.

* **Arşivleme Çözümleri** – Satır içi varlıkları ayrı olarak depolayarak arşivlenmiş mesajların görsel doğruluğunu koruyun.

## Performans Hususları

Yüzlerce veya binlerce MSG dosyasıyla uğraşırken şu ipuçlarını aklınızda bulundurun:

* **Toplu İşleme:** Bellek artışlarını önlemek için dosyaları yönetilebilir gruplara ayırın.

* **Kaynakları Hemen Serbest Bırakın:** Akışları kapatın (`try-with-resources`) ve çöp toplayıcının nesneleri geri kazanmasına izin verin.

* **Paralel Yürütme:** Birden fazla ayıklama işini eş zamanlı olarak çalıştırmak için sabit boyutlu bir `ExecutorService` kullanın, ancak CPU kullanımını izleyin.

## Sık Karşılaşılan Sorunlar ve Sorun Giderme

| Belirti | Olası Sebep | Çözüm |

|---------|--------------|-----|

| `attachment.getObjectData()` üzerinde `NullPointerException` | Mesajda ek meta verisi eksik (örneğin, bozuk MSG) | İşleme başlamadan önce MSG dosyasını doğrulayın veya istisnayı yakalayıp dosya adını kaydedin. |

| Kaydedilen dosya boş veya bozuk | Yanlış özellik adı ("Package" büyük/küçük harf duyarlılığı) | Özellik adının MSG'nin gerçek özelliğiyle eşleştiğini doğrulayın; Aspose.Email dokümantasyonu tam dizeyi listeler. |

| Büyük dosyalarla performans düşüyor | Akışlar kapatılmıyor, bu da bellek sızıntılarına yol açıyor | (Gösterildiği gibi) try-with-resources kullanın ve gerekirse JVM yığınını artırmayı düşünün. |

## Sıkça Sorulan Sorular

**S: Gerekli minimum Aspose.Email sürümü nedir?**
C: Bu eğitimde 25.4 sürümü kullanılmıştır, ancak JDK16'yı destekleyen herhangi bir 24.x+ sürümü çalışacaktır.

**S: Şifrelenmiş MSG dosyalarından satır içi ekleri çıkarabilir miyim?**
C: Evet, `MapiMessage` yüklenirken doğru şifre çözme parolasını sağladığınız sürece.

**S: Satır içi resimler ile normal dosya ekleri arasında nasıl ayrım yapabilirim?**
C: `IsAttachmentInline` yardımcısını kullanın; bu yardımcı, bir eki satır içi olarak işaretleyen MAPI `ObjInfo` bayrağını kontrol eder.

**S: Satır içi ekteki dosyanın orijinal dosya adını korumanın bir yolu var mı?**
C: Örnek, benzersizlik için bir UUID oluşturur, ancak `attachment.getLongFileName()` özelliğini okuyabilir ve `SaveAttachment` çağrısı yaparken kullanabilirsiniz.

**S: Bu yaklaşım Linux/macOS'ta olduğu kadar Windows'ta da çalışır mı?**
C: Kesinlikle—Aspose.Email, JDK yüklü olduğu sürece platformdan bağımsızdır.

## Kaynaklar
- **Belgeler:** [Aspose E-posta Belgeleri](https://docs.aspose.com/email/java/)

---

**Son Güncelleme:** 2025-12-17
**Test Edilen Sürüm:** Aspose.Email for Java 25.4 (JDK16)
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}