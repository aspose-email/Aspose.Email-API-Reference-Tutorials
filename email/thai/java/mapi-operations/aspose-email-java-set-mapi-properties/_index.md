---
"date": "2025-05-29"
"description": "เรียนรู้วิธีการจัดการคุณสมบัติต่างๆ ในข้อความ MAPI อย่างมีประสิทธิภาพโดยใช้ Aspose.Email สำหรับ Java คู่มือนี้ครอบคลุมการตั้งค่า float, double, long และประเภทอื่นๆ"
"title": "ตั้งค่าคุณสมบัติ MAPI หลายรายการใน Java ด้วย Aspose.Email คำแนะนำที่ครอบคลุม"
"url": "/th/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ตั้งค่าคุณสมบัติ MAPI หลายรายการใน Java ด้วย Aspose อีเมล: คู่มือฉบับสมบูรณ์

## การแนะนำ

การจัดการคุณสมบัติข้อความ MAPI อย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับการปรับปรุงแอปพลิเคชัน Java ของคุณ ด้วย Aspose.Email สำหรับ Java คุณสามารถตั้งค่าคุณสมบัติต่างๆ เช่น float, double, long, short, boolean และคุณสมบัติแบบกำหนดเองได้อย่างราบรื่น คู่มือนี้จะแนะนำคุณถึงวิธีการต่างๆ เพื่อให้บรรลุสิ่งนี้

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าคุณสมบัติต่างๆ ในข้อความ MAPI โดยใช้ Aspose.Email Java
- ทำความเข้าใจประเภททรัพย์สินที่แตกต่างกันและการใช้งานของพวกเขา
- ตัวอย่างโค้ดเชิงปฏิบัติสำหรับการใช้งาน

มาเริ่มต้นด้วยการครอบคลุมข้อกำหนดเบื้องต้นกันก่อน

## ข้อกำหนดเบื้องต้น

เพื่อติดตามต่อไป ให้แน่ใจว่าคุณมี:
- **ชุดพัฒนา Java (JDK):** ติดตั้ง JDK 8 หรือใหม่กว่า
- **ห้องสมุดอีเมล Aspose:** แนะนำเวอร์ชัน 25.4
- **การตั้งค่า Maven:** ควรกำหนดค่า Maven ใน IDE ของคุณสำหรับการจัดการการอ้างอิง

### ห้องสมุดที่จำเป็น

รวม Aspose.Email เป็นส่วนที่ต้องมีในของคุณ `pom.xml`-
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การขอใบอนุญาต
- **ทดลองใช้งานฟรี:** เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว:** รับเพื่อการทดสอบแบบขยายเวลาโดยไม่มีข้อจำกัด
- **ซื้อ:** พิจารณาซื้อหากเหมาะกับความต้องการของคุณ

## การตั้งค่า Aspose.Email สำหรับ Java

ตรวจสอบให้แน่ใจว่า Aspose.Email ได้รับการกำหนดค่าอย่างถูกต้องในสภาพแวดล้อมการพัฒนาของคุณ:
1. **การนำเข้าสิ่งที่ต้องพึ่งพา:** แก้ไขการอ้างอิง Maven
2. **ตั้งค่าใบอนุญาต:**
   - ดาวน์โหลดไฟล์ลิขสิทธิ์จาก [อาโปเซ่](https://purchase-aspose.com/buy).
   - ใช้ได้โดย:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

เมื่อการตั้งค่าเสร็จสมบูรณ์แล้ว เรามาดูวิธีการตั้งค่าคุณสมบัติต่างๆ กัน

## คู่มือการใช้งาน

### การตั้งค่าคุณสมบัติการลอยตัวหลายรายการ

การตั้งค่าคุณสมบัติ float ช่วยให้จัดเก็บข้อมูลตัวเลขได้อย่างมีประสิทธิภาพ:

#### ภาพรวม
ฟีเจอร์นี้สาธิตการเพิ่มค่า float หลายค่าเป็นคุณสมบัติข้อความ MAPI โดยใช้ Aspose.Email สำหรับ Java

#### ขั้นตอน
1. **สร้างและเริ่มต้นข้อความ**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **เพิ่มค่าลอยตัวลงในรายการ**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **ตั้งค่าคุณสมบัติด้วยตัวระบุที่ไม่ซ้ำกัน**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*คำอธิบาย:* ป้ายทรัพย์สิน `0x23901004` ระบุชุดคุณสมบัติ float นี้

### การตั้งค่าคุณสมบัติ Double หลายรายการ

คุณสมบัติคู่จัดเก็บตัวเลขทศนิยมลอยตัวที่มีความแม่นยำสูง:

#### ภาพรวม
ส่วนนี้แสดงการจัดเก็บค่า double หลายค่าเป็นคุณสมบัติข้อความ MAPI

#### ขั้นตอน
1. **เริ่มต้นข้อความ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **เติมค่าสองเท่า**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **มอบหมายให้แท็กทรัพย์สิน**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### การตั้งค่าคุณสมบัติ APPTIME หลายรายการ

คุณสมบัติ APPTIME จัดเก็บระยะเวลาอย่างมีประสิทธิภาพ:

#### ภาพรวม
ฟีเจอร์นี้แสดงการใช้ตัวเลขความแม่นยำสองเท่าสำหรับการแสดงเวลา

#### ขั้นตอน
1. **สร้างวัตถุข้อความ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **เพิ่มค่าเวลา**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **ตั้งค่าคุณสมบัติ**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### การตั้งค่าคุณสมบัติยาวหลายรายการ

คุณสมบัติยาวเหมาะสำหรับจำนวนเต็มขนาดใหญ่:

#### ภาพรวม
คุณลักษณะนี้มุ่งเน้นที่การตั้งค่าค่าจำนวนเต็มยาวหลายค่าในข้อความ

#### ขั้นตอน
1. **เริ่มต้นข้อความ MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **เพิ่มค่ายาว**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **กำหนดแท็กทรัพย์สิน**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### การตั้งค่าคุณสมบัติสั้นหลายรายการ

คุณสมบัติสั้น ๆ จะจัดเก็บข้อมูลจำนวนเต็มขนาดเล็กอย่างมีประสิทธิภาพ:

#### ภาพรวม
คู่มือนี้สาธิตการตั้งค่าจำนวนเต็มสั้นเป็นคุณสมบัติของข้อความ

#### ขั้นตอน
1. **เริ่มต้นข้อความ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **เพิ่มค่าสั้น**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **กำหนดแท็กทรัพย์สิน**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### การตั้งค่าคุณสมบัติบูลีนหลายรายการ

คุณสมบัติบูลีนจัดเก็บสถานะจริง/เท็จ:

#### ภาพรวม
เรียนรู้วิธีการตั้งค่าค่าบูลีนหลายค่าในข้อความ

#### ขั้นตอน
1. **สร้างวัตถุข้อความ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **เพิ่มค่าบูลีน**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **ตั้งค่าคุณสมบัติด้วยตัวระบุ**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### การตั้งค่าคุณสมบัติ Null

การกำหนดคุณสมบัติเป็นค่าว่างอย่างชัดเจนอาจเป็นประโยชน์ได้:

#### ภาพรวม
ส่วนนี้สาธิตการกำหนดค่า null ให้กับคุณสมบัติ

#### ขั้นตอน
1. **เริ่มต้นข้อความ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **กำหนดคุณสมบัติว่าง**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### ตั้งค่าคุณสมบัติแบบยาวที่มีชื่อพร้อม ID และ UUID ที่กำหนดเอง

สำหรับสถานการณ์ที่ซับซ้อน ให้ตั้งค่าคุณสมบัติที่มีชื่อ:

#### ภาพรวม
ฟีเจอร์นี้สาธิตการตั้งค่าคุณสมบัติ long ด้วยตัวระบุที่กำหนดเองและ UUID

#### ขั้นตอน
1. **เริ่มต้นข้อความ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **เพิ่มค่ายาว**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **สร้างและจัดทำแผนที่ทรัพย์สิน**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### การตั้งค่าคุณสมบัติที่กำหนดเองด้วยชื่อ

คุณสมบัติที่กำหนดเองสามารถตั้งชื่อเพื่อให้ระบุได้ง่ายขึ้น:

#### ภาพรวม
คู่มือนี้แสดงการตั้งค่าคุณสมบัติที่มีชื่อกำหนดเอง

#### ขั้นตอน
1. **เริ่มต้นวัตถุข้อความ**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **กำหนดคุณสมบัติที่กำหนดเอง**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### การตั้งค่าและการตรวจสอบคุณสมบัติ

การตรวจสอบให้แน่ใจว่าคุณสมบัติได้รับการตั้งค่าอย่างถูกต้องเป็นสิ่งสำคัญ:

#### ภาพรวม
หัวข้อนี้ครอบคลุมการตั้งค่าและการตรวจสอบคุณสมบัติต่างๆ ในข้อความ MAPI

#### ขั้นตอน
1. **ตั้งค่าคุณสมบัติ**
   ทำตามตัวอย่างก่อนหน้าเพื่อตั้งค่าคุณสมบัติ
2. **ตรวจสอบคุณสมบัติ**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## บทสรุป

คู่มือนี้ให้แนวทางที่ครอบคลุมในการจัดการคุณสมบัติต่างๆ ในข้อความ MAPI โดยใช้ Aspose.Email สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถจัดเก็บและจัดการประเภทข้อมูลต่างๆ ภายในแอปพลิเคชันของคุณได้อย่างมีประสิทธิภาพ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}