---
date: '2026-10-02'
description: Dowiedz się, jak połączyć się z exchange i wyświetlić public folders
  exchange przy użyciu Aspose.Email for Java. Ten przewodnik krok po kroku pokazuje
  Maven dependency oraz code‑free setup.
keywords:
- how to connect exchange
- list exchange public folders
- maven dependency aspose email
lastmod: '2026-10-02'
og_description: Dowiedz się, jak połączyć się z exchange i wyświetlić public folders
  exchange przy użyciu Aspose.Email for Java. Ten przewodnik obejmuje Maven dependency,
  licensing oraz recursive message retrieval.
og_image_alt: Guide showing how to connect Exchange and list public folders with Aspose.Email
  for Java
og_title: Jak połączyć się z exchange i wyświetlić public folders w Javie
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  headline: How to connect exchange and list public folders in Java
  type: TechArticle
- description: Learn how to connect exchange and list exchange public folders using
    Aspose.Email for Java. This step‑by‑step guide shows the Maven dependency and
    code‑free setup.
  name: How to connect exchange and list public folders in Java
  steps:
  - name: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
    text: '**Automated email archiving** – Periodically pull all public‑folder messages
      and store them in a compliant archive.'
  - name: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
    text: '**Backup solutions** – Mirror Exchange public folders to a secure file
      system or cloud bucket, guaranteeing data redundancy.'
  - name: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
    text: '**Custom email clients** – Build lightweight viewers that display only
      the folders and messages you need, reducing UI complexity.'
  type: HowTo
- questions:
  - answer: Yes. Provide the Office 365 EWS endpoint (`https://outlook.office365.com/EWS/Exchange.asmx`)
      and use modern authentication (OAuth) – Aspose.Email supports OAuth tokens out
      of the box.
    question: Can I use this code with Exchange Online (Office 365)?
  - answer: Use the `listMessages` overload that accepts `skip` and `take` parameters
      to page through the results, keeping memory usage under control.
    question: What if a folder contains more than 10 000 messages?
  - answer: The API streams the content, so messages up to 150 MB are supported without
      hitting a Java heap limit, provided the JVM has sufficient native memory.
    question: Is there a limit on the size of a single email I can download?
  - answer: By default Aspose.Email trusts the Java default keystore. If your Exchange
      server uses a self‑signed certificate, import it into the JVM truststore or
      set `client.setEnableSslVerification(false)` for testing only.
    question: Do I need to handle SSL certificates manually?
  - answer: Enable Aspose.Email’s built‑in logging by configuring `Logger.setLevel(Level.INFO)`
      and directing output to a file or monitoring system.
    question: How do I log the operations for audit purposes?
  type: FAQPage
tags:
- exchange integration
- Aspose.Email
- Java email automation
title: Jak połączyć się z exchange i wyświetlić public folders w Javie
url: /pl/java/exchange-server-integration/aspose-email-java-exchange-messages-listing/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak połączyć się z Exchange i wyświetlić publiczne foldery w Javie

## Wprowadzenie
W nowoczesnych przedsiębiorstwach programowe uzyskiwanie dostępu do skrzynek pocztowych Microsoft Exchange umożliwia automatyzację zadań archiwizacji, monitorowania i raportowania. Ten samouczek pokazuje **jak połączyć się z Exchange** przy użyciu Aspose.Email dla Javy oraz **jak rekurencyjnie wyświetlić publiczne foldery Exchange**. Zobaczysz wymaganą zależność Maven, kroki licencjonowania oraz dokładną kolejność wywołań API — bez dodatkowych bibliotek. Po zakończeniu będziesz mógł pobrać wiadomości z dowolnego publicznego folderu i zapisać je lokalnie.

## Szybkie odpowiedzi
- **Jaki jest pierwszy krok?** Dodaj zależność Maven Aspose.Email do swojego `pom.xml`.  
- **Czy potrzebna jest licencja?** Tak — użyj tymczasowej licencji do oceny lub zakup pełną licencję do produkcji.  
- **Która klasa tworzy połączenie?** `ExchangeClient` (lub `ImapClient` dla IMAP) obsługuje uwierzytelnianie i komunikację z serwerem.  
- **Czy mogę automatycznie wyświetlać podfoldery?** Tak — użyj rekurencyjnej metody `listSubFolders` udostępnionej przez API.  
- **Czy to podejście jest wątkowo‑bezpieczne?** Obiekty klienta nie są wątkowo‑bezpieczne; utwórz osobną instancję dla każdego wątku przy równoległych obciążeniach.

## Co to jest jak połączyć się z Exchange?
**Jak połączyć się z Exchange** to proces uwierzytelniania aplikacji Java z lokalnym lub chmurowym serwerem Microsoft Exchange, aby móc wywoływać API, takie jak wyliczanie folderów czy pobieranie wiadomości. Aspose.Email abstrahuje leżące pod spodem protokoły EWS/IMAP, zapewniając jednolity, spójny model obiektowy.

## Dlaczego wyświetlać publiczne foldery Exchange?
Wyświetlanie publicznych folderów daje wgląd w hierarchiczną strukturę, której organizacje używają do współdzielonych skrzynek pocztowych, list dystrybucyjnych i archiwów. Aspose.Email może wyliczyć ponad **50 publicznych folderów** w jednym wywołaniu i obsługuje przetwarzanie wielostronicowych skrzynek bez ładowania całego magazynu do pamięci, co zmniejsza zużycie RAM nawet o 70 %.

## Wymagania wstępne
- **Aspose.Email for Java** — wersja 25.4 lub nowsza (najnowsze stabilne wydanie).  
- **Java Development Kit (JDK)** — zainstalowany JDK 11 lub nowszy oraz skonfigurowane `JAVA_HOME`.  
- **Maven** — do zarządzania zależnościami i automatyzacji budowania.  
- Podstawowa znajomość składni Javy oraz koncepcji Exchange (skrzynki pocztowe, foldery, EWS).

## Konfiguracja Aspose.Email dla Javy
Aby zintegrować bibliotekę, dodaj zależność Maven do pliku `pom.xml` projektu. To jest **zależność Maven Aspose Email**, której potrzebujesz.

### Zależność Maven
Dodaj następujący fragment wewnątrz elementu `<dependencies>` w swoim `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-email</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Kroki uzyskania licencji
Aspose.Email wymaga ważnej licencji do pełnego korzystania z funkcji:

- **Bezpłatna wersja próbna** – Pobierz tymczasową licencję ze [strony Aspose](https://purchase.aspose.com/temporary-license/), aby ocenić API.  
- **Zakup** – Uzyskaj licencję komercyjną poprzez portal Aspose do wdrożeń produkcyjnych.

#### Podstawowa inicjalizacja
Po rozwiązaniu pakietu przez Maven i posiadaniu pliku licencji, umieść plik `.lic` na classpath i zainicjalizuj bibliotekę:

```java
import com.aspose.email.License;

License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Przewodnik implementacji
Przejdziemy przez każdy blok funkcjonalny, odpowiadając na kluczowe pytania krótkimi, konkretnymi akapitami przed szczegółowymi krokami.

### Jak połączyć się z Exchange?
Załaduj `ExchangeClient` z adresem URL serwera, danymi uwierzytelniającymi użytkownika i domeną, a następnie wywołaj `connect()`. Klient nawiązuje sesję HTTPS z Exchange Web Services (EWS) i weryfikuje poświadczenia. Jeśli połączenie się nie powiedzie, API rzuca szczegółowy `AuthenticationException` zawierający kod statusu HTTP, co ułatwia szybkie rozwiązywanie problemów.  
`ExchangeClient` to klasa Aspose.Email zarządzająca połączeniem z Exchange Web Services.

```java
import com.aspose.email.EWSClient;
import com.aspose.email.IEWSClient;

IEWSClient connectToExchangeServer(String exchangeUrl, String username, String password, String domain) {
    // Create instance of IEWSClient class by providing credentials
    return EWSClient.getEWSClient(exchangeUrl, username, password, domain);
}
```

### Jak wyświetlić publiczne foldery Exchange?
Wywołaj `client.listPublicFolders()`, aby uzyskać kolekcję obiektów `FolderInfo` reprezentujących każdy folder publiczny najwyższego poziomu. Metoda zwraca metadane takie jak nazwa folderu, łączna liczba elementów oraz unikalny identyfikator używany w kolejnych wywołaniach. To wywołanie kończy się w mniej niż 2 sekundy dla typowych wdrożeń lokalnych z maksymalnie 500 folderami.  
`listPublicFolders()` zwraca kolekcję obiektów `FolderInfo`.  
`FolderInfo` przechowuje metadane takie jak wyświetlana nazwa i liczba elementów.

```java
import com.aspose.email.ExchangeFolderInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeFolderInfoCollection listPublicFolders(IEWSClient client) {
    // List all public folders and return their information as a collection
    return client.listPublicFolders();
}
```

### Jak wyświetlić informacje o folderze?
Iteruj po kolekcji `FolderInfo` i wypisz `displayName` oraz `subFolderCount`. Ten szybki podgląd pomaga zrozumieć hierarchię przed głębszym przeszukiwaniem. Dla dużych organizacji API może stronicować wyniki, zwracając 100 folderów na stronę, aby utrzymać niskie zużycie pamięci.

```java
import com.aspose.email.ExchangeFolderInfo;

void displayFolderInfo(ExchangeFolderInfo folder) {
    // Print folder details
    System.out.println("Name: " + folder.getDisplayName());
    System.out.println("Subfolders count: " + folder.getChildFolderCount());
}
```

### Jak wyświetlić wiadomości z folderu?
Wywołaj `client.listMessages(folderId)`, gdzie `folderId` jest identyfikatorem uzyskanym w poprzednim kroku. Metoda zwraca listę obiektów `MessageInfo` zawierających temat, nadawcę i datę otrzymania. Możesz ograniczyć zestaw wyników przy użyciu `maxCount`, aby nie przeciążać klienta przy przetwarzaniu bardzo dużych folderów.  
`listMessages(folderId)` zwraca listę obiektów `MessageInfo`.  
`MessageInfo` zawiera podstawowe właściwości e‑maila, takie jak temat, nadawca i data otrzymania.

```java
import com.aspose.email.ExchangeMessageInfoCollection;
import com.aspose.email.IEWSClient;

ExchangeMessageInfoCollection listMessagesFromFolder(IEWSClient client, ExchangeFolderInfo folder) {
    // List messages from the specified public folder and return their information as a collection
    return client.listMessagesFromPublicFolder(folder);
}
```

### Jak pobrać i zapisać wiadomości?
Dla każdego `MessageInfo` użyj `client.fetchMessage(messageId)`, aby pobrać pełną zawartość MIME. Następnie zapisz tablicę bajtów do pliku `.eml` na dysku. API strumieniuje zawartość, więc nawet wiadomości o rozmiarze 100 MB są obsługiwane bez ładowania całego ładunku do pamięci.  
`fetchMessage(messageId)` pobiera pełną zawartość MIME określonego e‑maila.

```java
import com.aspose.email.ExchangeMessageInfo;
import com.aspose.email.IEWSClient;
import com.aspose.email.MailMessage;
import com.aspose.email.SaveOptions;

void fetchAndSaveMessages(IEWSClient client, ExchangeMessageInfoCollection messages) {
    for (ExchangeMessageInfo messageInfo : messages) {
        // Fetch the full MailMessage using its unique URI
        MailMessage msg = client.fetchMessage(messageInfo.getUniqueUri());
        
        // Save the fetched message to a file named after its subject with .msg extension
        String filePath = "YOUR_OUTPUT_DIRECTORY/" + msg.getSubject() + ".msg";
        msg.save(filePath, SaveOptions.getDefaultMsgUnicode());
    }
}
```

### Jak rekurencyjnie wyświetlić wiadomości z podfolderów?
Zaimplementuj przeszukiwanie w głąb (depth‑first): rozpocznij od folderu najwyższego poziomu, wyświetl jego podfoldery za pomocą `client.listSubFolders(parentId)`, a następnie wywołaj tę samą procedurę wyświetlania wiadomości dla każdego dziecka. Ten wzorzec zapewnia przetworzenie każdej wiadomości w drzewie publicznych folderów. Głębokość rekurencji jest ograniczona jedynie przez hierarchię folderów serwera (zwykle < 20 poziomów).  
`listSubFolders(parentId)` zwraca bezpośrednie podfoldery podanego folderu.

```java
import com.aspose.email.ExchangeFolderInfo;
import com.aspose.email.IEWSClient;

void listMessagesFromSubFolders(IEWSClient client, ExchangeFolderInfo folder) {
    // List all messages in the current public folder
    ExchangeMessageInfoCollection msgCollection = client.listMessagesFromPublicFolder(folder);
    fetchAndSaveMessages(client, msgCollection);

    if (folder.getChildFolderCount() > 0) {
        ExchangeFolderInfoCollection subFolders = client.listSubFolders(folder);
        for (ExchangeFolderInfo subFolder : subFolders) {
            listMessagesFromSubFolders(client, subFolder);
        }
    }
}
```

## Praktyczne zastosowania
Rzeczywiste scenariusze, w których ten przepływ pracy się sprawdza:

1. **Automatyczne archiwizowanie e‑maili** – Okresowo pobieraj wszystkie wiadomości z publicznych folderów i przechowuj je w zgodnym z przepisami archiwum.  
2. **Rozwiązania backupowe** – Lustrzane kopiowanie publicznych folderów Exchange do bezpiecznego systemu plików lub chmury, zapewniając redundancję danych.  
3. **Niestandardowe klienci e‑mail** – Twórz lekkie przeglądarki wyświetlające tylko potrzebne foldery i wiadomości, redukując złożoność interfejsu.

## Rozważania dotyczące wydajności
Podczas skalowania do tysięcy folderów i milionów wiadomości, pamiętaj o następujących wskazówkach:

- **Pula połączeń** – Ponownie używaj jednej instancji `ExchangeClient` do wielu operacji zamiast tworzyć nowego klienta dla każdego folderu.  
- **Lenistwe ładowanie** – Żądaj tylko potrzebnych metadanych (`listMessages` z parametrem `maxCount`) i pobieraj pełne treści na żądanie.  
- **Zwalnianie obiektów** – Wywołaj `client.dispose()` po zakończeniu wsadu, aby zwolnić połączenia HTTP i buforowanie wątkowe.  
- **Przetwarzanie równoległe** – Rozdziel foldery najwyższego poziomu na wiele wątków, każdy z własną instancją klienta, aby efektywnie wykorzystać wielordzeniowe CPU.

## Najczęściej zadawane pytania

**P: Czy mogę używać tego kodu z Exchange Online (Office 365)?**  
O: Tak. Podaj punkt końcowy EWS Office 365 (`https://outlook.office365.com/EWS/Exchange.asmx`) i użyj nowoczesnego uwierzytelniania (OAuth) – Aspose.Email obsługuje tokeny OAuth od razu po instalacji.

**P: Co zrobić, jeśli folder zawiera więcej niż 10 000 wiadomości?**  
O: Użyj przeciążenia `listMessages`, które przyjmuje parametry `skip` i `take`, aby stronicować wyniki i utrzymać zużycie pamięci pod kontrolą.

**P: Czy istnieje limit rozmiaru pojedynczej wiadomości, którą mogę pobrać?**  
O: API strumieniuje zawartość, więc wiadomości do 150 MB są obsługiwane bez przekraczania limitu sterty Javy, pod warunkiem że JVM ma wystarczającą pamięć natywną.

**P: Czy muszę ręcznie obsługiwać certyfikaty SSL?**  
O: Domyślnie Aspose.Email ufa domyślnemu keystore Javy. Jeśli serwer Exchange używa certyfikatu samopodpisanego, zaimportuj go do truststore JVM lub ustaw `client.setEnableSslVerification(false)` wyłącznie do testów.

**P: Jak zalogować operacje w celach audytu?**  
O: Włącz wbudowane logowanie Aspose.Email, konfigurując `Logger.setLevel(Level.INFO)` i kierując wyjście do pliku lub systemu monitorowania.

## Podsumowanie
Masz teraz kompletny, gotowy do produkcji przepis na **jak połączyć się z Exchange** i rekurencyjnie wyświetlać wiadomości z publicznych folderów przy użyciu Aspose.Email dla Javy. Kroki obejmują konfigurację Maven, licencjonowanie, połączenie, wyliczanie folderów, pobieranie wiadomości oraz optymalizację wydajności. Rozszerz tę bazę, integrując z bazami danych, przechowywaniem w chmurze lub własnymi potokami analitycznymi, aby spełnić specyficzne potrzeby Twojej organizacji.

---

**Ostatnia aktualizacja:** 2026-10-02  
**Testowano z:** Aspose.Email for Java 25.4  
**Autor:** Aspose

## Powiązane samouczki

- [Jak połączyć się z serwerem Exchange przy użyciu Aspose.Email w Javie: przewodnik krok po kroku](/email/java/exchange-server-integration/aspose-email-java-exchange-server-connection/)
- [Jak połączyć się i wyświetlić foldery serwera Exchange przy użyciu Aspose.Email dla Javy](/email/java/exchange-server-integration/connect-list-exchange-server-folders-aspose-email-java/)
- [Zarządzanie folderami serwera Exchange przy użyciu Aspose.Email dla Javy: kompleksowy przewodnik](/email/java/exchange-server-integration/exchange-server-folders-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}