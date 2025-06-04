---
"date": "2025-05-29"
"description": "Dowiedz się, jak efektywnie zarządzać wieloma właściwościami w wiadomościach MAPI przy użyciu Aspose.Email dla Java. Ten przewodnik obejmuje ustawianie float, double, long i innych typów."
"title": "Ustawianie wielu właściwości MAPI w Javie za pomocą Aspose.Email&#58; Kompleksowy przewodnik"
"url": "/pl/java/mapi-operations/aspose-email-java-set-mapi-properties/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ustawianie wielu właściwości MAPI w Javie za pomocą Aspose.Email: kompleksowy przewodnik

## Wstęp

Efektywne zarządzanie właściwościami wiadomości MAPI jest kluczowe dla ulepszenia aplikacji Java. Dzięki Aspose.Email for Java możesz bezproblemowo ustawić wiele właściwości, takich jak float, double, long, short, boolean i właściwości niestandardowe. Ten przewodnik przeprowadzi Cię przez różne metody, aby to osiągnąć.

**Czego się nauczysz:**
- Ustawianie wielu właściwości w wiadomościach MAPI przy użyciu Aspose.Email Java
- Zrozumienie różnych typów nieruchomości i ich zastosowań
- Praktyczne przykłady kodu do implementacji

Zacznijmy od omówienia warunków wstępnych.

## Wymagania wstępne

Aby móc kontynuować, upewnij się, że posiadasz:
- **Zestaw narzędzi programistycznych Java (JDK):** Zainstalowano JDK 8 lub nowszy.
- **Biblioteka Aspose.Email:** Zalecana jest wersja 25.4.
- **Konfiguracja Maven:** Maven powinien być skonfigurowany w środowisku IDE do zarządzania zależnościami.

### Wymagane biblioteki

Dołącz Aspose.Email jako zależność w swoim `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Nabycie licencji
- **Bezpłatna wersja próbna:** Zacznij od bezpłatnego okresu próbnego, aby poznać funkcje.
- **Licencja tymczasowa:** Pobierz w celu rozszerzonego testowania bez ograniczeń.
- **Zakup:** Rozważ zakup, jeśli odpowiada Twoim potrzebom.

## Konfigurowanie Aspose.Email dla Java

Upewnij się, że Aspose.Email jest poprawnie skonfigurowany w Twoim środowisku programistycznym:
1. **Zależności importowe:** Rozwiąż zależności Maven.
2. **Ustaw licencję:**
   - Pobierz plik licencji z [Postawić](https://purchase.aspose.com/buy).
   - Zastosuj za pomocą:
     ```java
     com.aspose.email.License license = new com.aspose.email.License();
     license.setLicense("path/to/your/license.lic");
     ```

Po zakończeniu konfiguracji przyjrzymy się bliżej temu, jak ustawić różne właściwości.

## Przewodnik wdrażania

### Ustawianie wielu właściwości zmiennoprzecinkowych

Ustawienie właściwości float pozwala na efektywne przechowywanie danych liczbowych:

#### Przegląd
Ta funkcja demonstruje dodawanie wielu wartości zmiennoprzecinkowych jako właściwości wiadomości MAPI przy użyciu Aspose.Email dla Java.

#### Kroki
1. **Utwórz i zainicjuj wiadomość**
   ```java
   import java.util.ArrayList;
   import com.aspose.email.MapiMessage;
   import com.aspose.email.MapiProperty;
   import com.aspose.email.system.collections.IList;

   MapiMessage msg = new MapiMessage();
   ```
2. **Dodaj wartości zmiennoprzecinkowe do listy**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((float) 1);
   values.addItem((float) 2);
   ```
3. **Ustaw właściwość z unikalnym identyfikatorem**
   ```java
   msg.setProperty(new MapiProperty(0x23901004, values));
   ```
*Wyjaśnienie:* Etykieta właściwości `0x23901004` identyfikuje ten zestaw właściwości float.

### Ustawianie wielu podwójnych właściwości

Właściwości Double przechowują liczby zmiennoprzecinkowe o wysokiej precyzji:

#### Przegląd
Ta sekcja pokazuje, jak przechowywać wiele wartości zmiennoprzecinkowych jako właściwości wiadomości MAPI.

#### Kroki
1. **Zainicjuj wiadomość**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Wypełnij wartości podwójne**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((double) 1);
   values.addItem((double) 2);
   ```
3. **Przypisz do znacznika właściwości**
   ```java
   msg.setProperty(new MapiProperty(0x23901005, values));
   ```

### Ustawianie wielu właściwości APPTIME

Właściwości APPTIME efektywnie przechowują czasy trwania:

#### Przegląd
Funkcja ta ilustruje wykorzystanie liczb podwójnej precyzji do reprezentacji czasu.

#### Kroki
1. **Utwórz obiekt wiadomości**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Dodaj wartości czasu**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(30456.34);
   values.addItem(40655.45);
   ```
3. **Ustaw właściwość**
   ```java
   msg.setProperty(new MapiProperty(0x23901007, values));
   ```

### Ustawianie wielu długich właściwości

Długie właściwości idealnie nadają się do dużych liczb całkowitych:

#### Przegląd
Funkcja ta służy do ustawiania wielu długich wartości całkowitych w wiadomości.

#### Kroki
1. **Zainicjuj komunikat MAPI**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Dodaj długie wartości**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((long) 30456);
   values.addItem((long) 40655);
   ```
3. **Zdefiniuj etykietę właściwości**
   ```java
   msg.setProperty(new MapiProperty(0x23901014, values));
   ```

### Ustawianie wielu krótkich właściwości

Krótkie właściwości pozwalają na wydajne przechowywanie małych danych całkowitych:

#### Przegląd
W tym przewodniku pokazano, jak ustawiać krótkie liczby całkowite jako właściwości wiadomości.

#### Kroki
1. **Zainicjuj wiadomość**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Dodaj krótkie wartości**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((short) 1);
   values.addItem((short) 2);
   ```
3. **Przypisz etykietę właściwości**
   ```java
   msg.setProperty(new MapiProperty(0x23901002, values));
   ```

### Ustawianie wielu właściwości logicznych

Właściwości boolowskie przechowują stany prawda/fałsz:

#### Przegląd
Dowiedz się, jak ustawić wiele wartości logicznych w wiadomości.

#### Kroki
1. **Utwórz obiekt wiadomości**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Dodaj wartości logiczne**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem(true);
   values.addItem(false);
   ```
3. **Ustaw właściwość z identyfikatorem**
   ```java
   msg.setProperty(new MapiProperty(0x2390100b, values));
   ```

### Ustawianie właściwości null

Jawne ustawienie właściwości na wartość null może być przydatne:

#### Przegląd
W tej sekcji pokazano, jak przypisać właściwości wartość null.

#### Kroki
1. **Zainicjuj wiadomość**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Przypisz właściwość null**
   ```java
   msg.setProperty(new MapiProperty(0x67400001, new byte[1]));
   ```

### Ustawianie właściwości o nazwie Long z niestandardowym identyfikatorem i identyfikatorem UUID

W przypadku złożonych scenariuszy ustaw nazwane właściwości:

#### Przegląd
Ta funkcja demonstruje ustawienie długiej właściwości z niestandardowym identyfikatorem i UUID.

#### Kroki
1. **Zainicjuj wiadomość**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Dodaj długie wartości**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem((int) 4);
   UUID uuid = UUID.randomUUID();
   ```
3. **Utwórz i zmapuj nieruchomość**
   ```java
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_MV_LONG), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, (long) 0x00008028, uuid);
   msg.setProperty(property);
   ```

### Ustawianie właściwości niestandardowej z nazwą

Właściwościom niestandardowym można nadawać nazwy, aby ułatwić ich identyfikację:

#### Przegląd
W tym przewodniku dowiesz się, jak ustawić właściwości o niestandardowych nazwach.

#### Kroki
1. **Zainicjuj obiekt wiadomości**
   ```java
   MapiMessage msg = new MapiMessage();
   ```
2. **Zdefiniuj niestandardową właściwość**
   ```java
   IList values = (IList) new ArrayList();
   values.addItem("Custom Value");
   UUID uuid = UUID.randomUUID();
   
   MapiProperty property = new MapiProperty(msg.getNamedPropertyMapping().getNextAvailablePropertyId(com.aspose.email.MapiPropertyType.PT_STRING), values);
   msg.getNamedPropertyMapping().addNamedPropertyMapping(property, "CustomName", uuid);
   ```

### Ustawianie i sprawdzanie poprawności właściwości

Kluczowe jest upewnienie się, że właściwości są ustawione poprawnie:

#### Przegląd
W tej sekcji omówiono ustawianie i sprawdzanie poprawności wielu właściwości w komunikatach MAPI.

#### Kroki
1. **Ustaw właściwość**
   Aby ustawić właściwość, wykonaj czynności opisane w poprzednich przykładach.
2. **Sprawdź właściwość**
   ```java
   if (msg.getProperties().containsKey(0x23901004)) {
       System.out.println("Property is set correctly.");
   } else {
       System.err.println("Property setting failed.");
   }
   ```

## Wniosek

Ten przewodnik przedstawia kompleksowe podejście do zarządzania wieloma właściwościami w wiadomościach MAPI przy użyciu Aspose.Email dla Java. Wykonując te kroki, możesz wydajnie przechowywać i zarządzać różnymi typami danych w swoich aplikacjach.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}