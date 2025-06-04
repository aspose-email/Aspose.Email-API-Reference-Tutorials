---
"date": "2025-05-29"
"description": "Tanulja meg, hogyan kezelhet hatékonyan több tulajdonságot MAPI üzenetekben az Aspose.Email for Java használatával. Ez az útmutató a float, double, long és egyéb típusok beállítását ismerteti."
"title": "Több MAPI tulajdonság beállítása Java-ban az Aspose.Email segítségével – Átfogó útmutató"
"url": "/hu/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Több MAPI tulajdonság beállítása Java-ban az Aspose.Email segítségével: Átfogó útmutató

## Bevezetés

A MAPI üzenettulajdonságok hatékony kezelése kulcsfontosságú a Java alkalmazások fejlesztéséhez. Az Aspose.Email for Java segítségével zökkenőmentesen beállíthat több tulajdonságot, például float, double, long, short, boolean és egyéni tulajdonságokat. Ez az útmutató bemutatja a különböző módszereket ennek eléréséhez.

**Amit tanulni fogsz:**
- Több tulajdonság beállítása MAPI üzenetekben Aspose.Email Java használatával
- A különböző ingatlantípusok és azok felhasználásának megértése
- Gyakorlati kódpéldák a megvalósításhoz

Kezdjük az előfeltételek ismertetésével.

## Előfeltételek

A folytatáshoz győződjön meg arról, hogy rendelkezik a következőkkel:
- **Java fejlesztőkészlet (JDK):** JDK 8 vagy újabb verzió telepítve.
- **Aspose.Email könyvtár:** A 25.4-es verzió ajánlott.
- **Maven beállítás:** A Mavent be kell állítani az IDE-ben a függőségek kezeléséhez.

### Kötelező könyvtárak

Vegye fel az Aspose.Email-t függőségként a `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Licencbeszerzés
- **Ingyenes próbaverzió:** Kezdje egy ingyenes próbaverzióval a funkciók felfedezését.
- **Ideiglenes engedély:** Korlátozások nélküli, kiterjesztett teszteléshez szerezze be.
- **Vásárlás:** Fontold meg a vásárlást, ha megfelel az igényeidnek.

## Az Aspose.Email beállítása Java-hoz

Győződjön meg arról, hogy az Aspose.Email megfelelően van konfigurálva a fejlesztői környezetben:
1. **Függőségek importálása:** Maven függőségek feloldása.
2. **Licenc beállítása:**
   - Licencfájl letöltése innen [Aspose](https://purchase.aspose.com/buy).
   - Alkalmazza a következőképpen:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

A beállítás befejezése után nézzük meg, hogyan állíthatunk be különböző tulajdonságokat.

## Megvalósítási útmutató

### Többszörös úszófelület tulajdonságainak beállítása

A lebegőpontos tulajdonságok beállítása lehetővé teszi a numerikus adatok hatékony tárolását:

#### Áttekintés
Ez a funkció bemutatja több lebegőpontos érték hozzáadását MAPI üzenettulajdonságként az Aspose.Email for Java használatával.

#### Lépések
1. **Az üzenet létrehozása és inicializálása**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Lebegőpontos értékek hozzáadása egy listához**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Állítsa be a tulajdonságot egyedi azonosítóval**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Magyarázat:* A tulajdonságcímke `0x23901004` azonosítja ezt a float tulajdonságkészletet.

### Többszörös dupla tulajdonság beállítása

A Double tulajdonságok nagy pontosságú lebegőpontos számokat tárolnak:

#### Áttekintés
Ez a szakasz több dupla érték MAPI üzenettulajdonságként való tárolását mutatja be.

#### Lépések
1. **Üzenet inicializálása**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Dupla értékek kitöltése**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Tulajdonságcímkéhez rendelés**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Több APPTIME tulajdonság beállítása

Az APPTIME tulajdonságok hatékonyan tárolják az időtartamokat:

#### Áttekintés
Ez a funkció a dupla pontosságú számok használatát szemlélteti az időábrázoláshoz.

#### Lépések
1. **Üzenetobjektum létrehozása**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Időértékek hozzáadása**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Tulajdonság beállítása**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Több hosszú tulajdonság beállítása

A Long tulajdonságok ideálisak nagy egész számokhoz:

#### Áttekintés
Ez a funkció több hosszú egész szám értékének üzenetben való beállítására összpontosít.

#### Lépések
1. **MAPI üzenet inicializálása**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Hosszú értékek hozzáadása**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Tulajdonságcímke definiálása**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Több rövid tulajdonság beállítása

rövid tulajdonságok hatékonyan tárolják a kis egész számokat:

#### Áttekintés
Ez az útmutató bemutatja a rövid egész számok üzenettulajdonságként való beállítását.

#### Lépések
1. **Üzenet inicializálása**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Rövid értékek hozzáadása**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Tulajdonságcímke hozzárendelése**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Több logikai tulajdonság beállítása

A logikai tulajdonságok igaz/hamis állapotokat tárolnak:

#### Áttekintés
Ismerje meg, hogyan állíthat be több logikai értéket egy üzenetben.

#### Lépések
1. **Üzenetobjektum létrehozása**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Logikai értékek hozzáadása**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Tulajdonság beállítása azonosítóval**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Null tulajdonság beállítása

Hasznos lehet egy tulajdonság explicit módon null értékűre állítása:

#### Áttekintés
Ez a szakasz bemutatja egy tulajdonsághoz null érték hozzárendelését.

#### Lépések
1. **Üzenet inicializálása**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Null tulajdonság hozzárendelése**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Elnevezett hosszú tulajdonság beállítása egyéni azonosítóval és UUID-val

Összetett forgatókönyvek esetén állítson be elnevezett tulajdonságokat:

#### Áttekintés
Ez a funkció egy long tulajdonság egyéni azonosítóval és UUID-val történő beállítását mutatja be.

#### Lépések
1. **Üzenet inicializálása**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Hosszú értékek hozzáadása**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Tulajdon létrehozása és leképezése**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Egyéni tulajdonság beállítása névvel

Az egyéni tulajdonságok elnevezése a könnyebb azonosítás érdekében:

#### Áttekintés
Ez az útmutató az egyéni nevű tulajdonságok beállítását mutatja be.

#### Lépések
1. **Üzenetobjektum inicializálása**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Egyéni tulajdonság definiálása**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Tulajdonságok beállítása és érvényesítése

A tulajdonságok helyes beállítása elengedhetetlen:

#### Áttekintés
Ez a szakasz a MAPI-üzenetekben található több tulajdonság beállítását és érvényesítését tárgyalja.

#### Lépések
1. **Tulajdonság beállítása**
   Kövesd az előző példákat egy tulajdonság beállításához.
2. **Tulajdonság érvényesítése**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Következtetés

Ez az útmutató átfogó megközelítést kínál a MAPI üzenetek több tulajdonságának kezelésére az Aspose.Email for Java használatával. A lépéseket követve hatékonyan tárolhat és kezelhet különféle adattípusokat az alkalmazásain belül.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}