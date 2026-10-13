---
date: 2026-10-12
description: Aspose.Email for Java를 사용하여 .ics 파일 java 생성, calendar invite 만들기, email
  java 전송, eml을 msg java로 변환, digital signature java 추가 방법을 배웁니다.
keywords:
- generate ics file java
- convert eml to msg java
- add digital signature java
- read ics file java
- encrypt email java
lastmod: 2026-10-12
linktitle: Aspose.Email for Java 튜토리얼
og_description: Aspose.Email for Java를 사용하여 .ics 파일 java를 생성하는 방법. calendar invites
  만들고, SMTP를 통해 전송하며, digital signatures를 추가하고, 몇 단계만으로 이메일을 암호화합니다.
og_image_alt: Developer guide showing how to generate .ics calendar invites in Java
  with Aspose.Email
og_title: Aspose.Email for Java를 사용하여 .ics 파일 java 생성 방법
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to generate .ics file java, create calendar invite, send
    email java, convert eml to msg java, and add digital signature java using Aspose.Email
    for Java.
  headline: How to generate .ics file java using Aspose.Email for Java
  type: TechArticle
- description: Learn how to generate .ics file java, create calendar invite, send
    email java, convert eml to msg java, and add digital signature java using Aspose.Email
    for Java.
  name: How to generate .ics file java using Aspose.Email for Java
  steps:
  - name: set up your project
    text: Add the Aspose.Email JAR to your classpath or reference it via Maven/Gradle.
      This gives you access to `Appointment`, `MailMessage`, `SmtpClient` and related
      types.
  - name: build the appointment
    text: '`Appointment` is Aspose.Email’s representation of a calendar event. It
      stores the subject, location, start/end times, and attendee list. Create the
      object and fill the required fields: *subject, location, start time, end time,
      attendees, reminder*.'
  - name: convert the appointment to an iCalendar stream
    text: Call `appointment.save` to serialize the object to the iCalendar format.
      You can write the stream to disk (`.ics` file) or keep it in memory for immediate
      attachment.
  - name: create the email message
    text: '`MailMessage` is the top‑level class that models an email. It holds the
      sender, recipients, subject, body and any attachments. Instantiate a `MailMessage`,
      set the plain‑text or HTML body, and attach the iCalendar stream with MIME type
      `text/calendar`.'
  - name: (optional) add a digital signature
    text: 'If you need a **digital signature java**, load your X.509 certificate (`certificate.pfx`)
      and call `mailMessage.sign(certificate, password)`. The `sign` method applies
      an S/MIME signature to the entire message using the provided certificate, ensuring
      integrity and authenticity. This guarantees that '
  - name: (optional) encrypt the email
    text: To **encrypt email java**, obtain the recipient’s public certificate and
      invoke `mailMessage.encrypt(publicCertificate)`. The `encrypt` method encrypts
      the MIME content with the recipient’s public key, producing an S/MIME encrypted
      message. Encryption protects sensitive meeting details such as locat
  - name: send the email via SMTP
    text: '`SmtpClient` is Aspose.Email’s SMTP transport class. Configure host, port,
      credentials, and enable TLS/SSL if required. Then call `client.send(mailMessage)`
      to deliver the invite. > **Pro tip:** reuse a single `SmtpClient` instance when
      sending bulk invitations; it reduces socket overhead and improv'
  type: HowTo
- questions:
  - answer: Use `Appointment.load("invite.ics")` to import the file back into an `Appointment`
      object, then read its properties such as `startTime`, `subject`, and `attendees`.
    question: How do I read an .ics file after creating a calendar invite?
  - answer: Yes – set `mailMessage.isCalendar = true` and assign the `Appointment`
      object directly to the message body; the client renders it as a meeting request.
    question: Can I send a calendar invite without an attachment?
  - answer: Absolutely. Load the EML with `MailMessage.load`, then call `mailMessage.save("output.msg",
      MailMessageSaveType.OutlookMessage)`. The attached `.ics` remains intact.
    question: Is it possible to convert an EML file to MSG while preserving calendar
      data?
  - answer: A valid X.509 certificate (PFX) and its private‑key password. Call `mailMessage.sign(certificate,
      password)` before sending.
    question: What do I need to add a digital signature to my email?
  - answer: Obtain the recipient’s public certificate and invoke `mailMessage.encrypt(publicCertificate)`.
      The entire message, including the `.ics` attachment, is encrypted end‑to‑end.
    question: How can I encrypt email java to protect the invite?
  type: FAQPage
tags:
- generate ics
- Aspose.Email
- Java email processing
- calendar invites
- email security
title: Aspose.Email for Java를 사용하여 .ics 파일 java 생성 방법
url: /ko/java/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Email for Java를 사용하여 .ics 파일을 Java에서 생성하는 방법

이 튜토리얼에서는 Aspose.Email을 사용하여 **.ics 파일을 Java에서 생성하는 방법**을 알아보고, 초대를 이메일에 첨부하며, 선택적으로 서명하거나 암호화할 수 있습니다. 내부 일정 관리 도구를 만들든 대규모 알림 서비스를 구축하든, 아래 단계는 Windows, Linux 및 macOS Java 런타임에서 실행되는 프로덕션 준비 솔루션을 제공합니다.

## 빠른 답변
- **Java에서 .ics 파일을 어떻게 생성하나요?** `Appointment` 객체를 생성하고 필드를 채운 다음 `appointment.save`를 호출하여 iCalendar 스트림을 얻습니다.  
- **SMTP를 통해 초대를 보낼 수 있나요?** 예 – `SmtpClient`를 인스턴스화하고 TLS/SSL을 구성한 뒤 `client.send(message)`를 호출합니다.  
- **초대는 어떤 형식을 사용하나요?** Outlook, Google Calendar, Apple Calendar 및 대부분의 다른 클라이언트와 호환되는 표준 iCalendar(`.ics`) 형식입니다.  
- **프로덕션에 라이선스가 필요합니까?** 비평가용이 아닌 배포에는 상업용 Aspose.Email 라이선스가 필요합니다.  
- **초대에 디지털 서명을 추가할 수 있나요?** 물론입니다 – X.509 인증서를 로드하고 `mailMessage.sign`을 호출합니다.  

## 캘린더 초대란 무엇이며 프로그래밍 방식으로 만드는 이유는?
캘린더 초대는 이벤트의 시간, 장소, 참석자 및 반복 규칙을 설명하는 iCalendar(`.ics`) 파일입니다. 수신자는 한 번의 클릭으로 회의를 개인 캘린더에 추가할 수 있어 수동 입력을 없애고 일정 오류를 줄입니다.

## Aspose.Email for Java를 사용하여 .ics 파일을 Java에서 생성하는 이유는?
Aspose.Email는 **전체 .ics 지원**을 제공하며, 재발, 알람, 참석자 등 50개 이상의 iCalendar 기능을 제3자 라이브러리 없이 사용할 수 있습니다. Java 8‑21에서 실행되며, 메모리 효율 모드에서 최대 500 MB 파일을 처리하고 S/MIME 서명 및 암호화와 같은 내장 보안 기능을 제공합니다.

## 사전 요구 사항
- Java Development Kit (JDK) 8 이상.  
- Aspose.Email for Java 라이브러리(Aspose 웹사이트에서 다운로드).  
- SMTP 서버(Gmail, Office 365 또는 로컬 릴레이).  
- 선택 사항: 서명을 위한 X.509 인증서(PFX).  
- 선택 사항: 암호화를 위한 수신자 공개 키.  

## .ics 파일을 Java에서 생성하는 방법

Aspose.Email 라이브러리를 로드하고 아래 단계에 따라 진행하십시오. 전체 질문에 대한 답은 이 단락 끝에 있습니다: **`Appointment`를 생성하고 속성을 채운 뒤 `save`를 호출하여 iCalendar 스트림을 만든 다음 이를 `MailMessage`에 첨부함으로써 .ics 파일을 생성합니다.** 다음 섹션에서는 프로세스를 명확하고 재사용 가능한 작업으로 나눕니다.

### 단계 1: 프로젝트 설정
Aspose.Email JAR를 클래스패스에 추가하거나 Maven/Gradle을 통해 참조하십시오. 이를 통해 `Appointment`, `MailMessage`, `SmtpClient` 및 관련 타입에 접근할 수 있습니다.

### 단계 2: 약속 만들기
`Appointment`는 Aspose.Email이 제공하는 캘린더 이벤트 표현입니다. 제목, 위치, 시작/종료 시간 및 참석자 목록을 저장합니다.  
객체를 생성하고 필수 필드를 채웁니다:

*subject, location, start time, end time, attendees, reminder*.

### 단계 3: 약속을 iCalendar 스트림으로 변환
`appointment.save`를 호출하여 객체를 iCalendar 형식으로 직렬화합니다. 스트림을 디스크(`.ics` 파일)로 저장하거나 즉시 첨부하기 위해 메모리에 유지할 수 있습니다.

### 단계 4: 이메일 메시지 만들기
`MailMessage`는 이메일을 모델링하는 최상위 클래스입니다. 발신자, 수신자, 제목, 본문 및 모든 첨부 파일을 포함합니다.  
`MailMessage`를 인스턴스화하고 일반 텍스트 또는 HTML 본문을 설정한 뒤 MIME 유형 `text/calendar`로 iCalendar 스트림을 첨부합니다.

### 단계 5: (옵션) 디지털 서명 추가
**digital signature java**가 필요하면 X.509 인증서(`certificate.pfx`)를 로드하고 `mailMessage.sign(certificate, password)`를 호출하십시오.  
`sign` 메서드는 제공된 인증서를 사용해 전체 메시지에 S/MIME 서명을 적용하여 무결성과 진위성을 보장합니다. 이는 이메일이 전송 중에 변경되지 않았음을 보장하고 발신자 신원을 확인합니다.

### 단계 6: (옵션) 이메일 암호화
**encrypt email java**를 수행하려면 수신자의 공개 인증서를 얻은 뒤 `mailMessage.encrypt(publicCertificate)`를 호출하십시오.  
`encrypt` 메서드는 수신자의 공개 키로 MIME 콘텐츠를 암호화하여 S/MIME 암호화 메시지를 생성합니다. 암호화는 위치, 안건 및 참석자 목록과 같은 민감한 회의 세부 정보를 무단으로 읽히는 것을 방지합니다.

### 단계 7: SMTP를 통해 이메일 전송
`SmtpClient`는 Aspose.Email의 SMTP 전송 클래스입니다. 호스트, 포트, 자격 증명을 구성하고 필요하면 TLS/SSL을 활성화합니다. 그런 다음 `client.send(mailMessage)`를 호출하여 초대를 전송합니다.

> **Pro tip:** 대량 초대를 보낼 때 단일 `SmtpClient` 인스턴스를 재사용하면 소켓 오버헤드가 감소하고 처리량이 향상됩니다.

## .ics 파일을 Java에서 읽는 방법
`.ics` 파일을 `Appointment.load`를 사용하여 `Appointment` 객체로 다시 로드합니다. `load` 메서드는 iCalendar 파일을 읽고 이벤트 데이터가 채워진 `Appointment` 객체를 반환합니다. 반환된 객체를 통해 시작 시간, 제목, 참석자 목록 등 이벤트 세부 정보를 직접 접근할 수 있어 초대를 프로그래밍 방식으로 표시하거나 수정할 수 있습니다.

## eml을 msg Java로 변환하는 방법
Aspose.Email는 첨부된 캘린더 데이터를 보존하면서 **convert eml to msg java**를 수행할 수 있습니다. `MailMessage.load`로 EML 파일을 로드합니다. `load` 메서드는 이메일 파일(EML)을 `MailMessage` 객체로 읽은 뒤 `mailMessage.save("output.msg", MailMessageSaveType.OutlookMessage)`를 호출합니다. 결과 MSG 파일에는 원본 메시지 본문, 첨부 파일 및 포함된 `.ics` 초대가 포함됩니다.

## 디지털 서명 Java 추가 방법
X.509 인증서(PFX)와 비밀번호를 확보한 뒤 `mailMessage.sign(certificate, password)`를 호출합니다. 이 메서드는 MIME 엔터티를 S/MIME 서명으로 감싸며, 이메일 클라이언트가 자동으로 검증합니다. 이는 이메일의 무결성을 보장하고 수신자에게 발신자 신원을 확인시켜 줍니다.

## 이메일 Java 암호화 방법
수신자의 공개 인증서(보통 `.cer` 파일)를 확보하고 `mailMessage.encrypt(publicCertificate)`를 호출합니다. 이는 전체 MIME 페이로드를 암호화하여 일치하는 개인 키를 가진 사람만 내용을 복호화할 수 있게 합니다. 암호화는 위치, 안건 및 참석자 목록과 같은 민감한 회의 세부 정보를 무단으로 읽히는 것을 방지합니다.

## 일반적인 사용 사례
- 웹 포털 또는 내부 도구를 통한 자동 회의 일정 잡기
- 첨부된 `.ics` 파일이 포함된 알림 이메일
- 웨비나, 교육 세션 또는 기업 이벤트를 위한 대량 초대
- Outlook 또는 Google Calendar와 판매 회의를 동기화하는 CRM 통합

## 모범 사례 및 문제 해결
- **객체 재사용**: 배치 전송 시 TLS 핸드셰이크를 반복하지 않도록 단일 `SmtpClient`를 유지합니다.
- **참석자 검증**: `Appointment`에 추가하기 전에 이메일 주소가 RFC‑5322 규격을 준수하는지 확인합니다.
- **시간대 처리**: 지역 간 시작 시간 불일치를 방지하려면 `Appointment.timeZone` 속성을 설정합니다.
- **대용량 파일**: 많은 참석자가 있는 이벤트 초대를 생성할 때는 메모리 사용량을 낮추기 위해 `Appointment.save` 오버로드를 사용해 `FileOutputStream`에 직접 기록합니다.
- **서명 오류**: 수신자가 서명이 유효하지 않다고 보고하면 인증서 체인이 완전한지와 개인 키 비밀번호가 올바른지 확인합니다.

## 자주 묻는 질문

**Q: 캘린더 초대를 만든 후 .ics 파일을 어떻게 읽나요?**  
A: `Appointment.load("invite.ics")`를 사용하여 파일을 `Appointment` 객체로 가져온 뒤 `startTime`, `subject`, `attendees`와 같은 속성을 읽습니다.

**Q: 첨부 파일 없이 캘린더 초대를 보낼 수 있나요?**  
A: 예 – `mailMessage.isCalendar = true`로 설정하고 `Appointment` 객체를 메시지 본문에 직접 할당하면 클라이언트가 회의 요청으로 표시합니다.

**Q: 캘린더 데이터를 보존하면서 EML 파일을 MSG로 변환할 수 있나요?**  
A: 물론입니다. `MailMessage.load`로 EML을 로드한 뒤 `mailMessage.save("output.msg", MailMessageSaveType.OutlookMessage)`를 호출합니다. 첨부된 `.ics`는 그대로 유지됩니다.

**Q: 이메일에 디지털 서명을 추가하려면 무엇이 필요합니까?**  
A: 유효한 X.509 인증서(PFX)와 해당 개인 키 비밀번호가 필요합니다. 전송 전에 `mailMessage.sign(certificate, password)`를 호출하십시오.

**Q: 초대를 보호하기 위해 email java를 어떻게 암호화할 수 있나요?**  
A: 수신자의 공개 인증서를 확보하고 `mailMessage.encrypt(publicCertificate)`를 호출합니다. `.ics` 첨부 파일을 포함한 전체 메시지가 종단 간 암호화됩니다.

---

### Aspose.Email for Java 학습 경로

* ### [Aspose.Email for Java 시작하기](./getting-started/)
    **Aspose.Email for Java**와 함께 여정을 시작하십시오. API 설치, 라이선스 구성 및 첫 번째 이메일 애플리케이션 구축 방법을 배웁니다. 따라하기 쉬운 단계별 가이드를 통해 기본을 빠르게 마스터할 수 있습니다.

* ### [Java에서 핵심 이메일 메시지 작업](./email-message-operations/)
    **Aspose.Email for Java**를 사용한 포괄적인 이메일 메시지 처리 기술을 살펴보세요. 실용적인 튜토리얼과 코드 예제를 통해 **EML**, **MSG**, **MHTML**와 같은 인기 형식 간에 이메일 메시지를 생성, 로드, 저장 및 변환하는 방법을 배웁니다.

* ### [Java에서 이메일 메시지 포맷 및 맞춤화](./message-formatting-customization/)
    **Aspose.Email for Java**로 이메일 콘텐츠 포맷을 마스터하십시오. 자세한 튜토리얼을 통해 **HTML 본문**, 대체 텍스트, 사용자 정의 헤더 및 메시지 인코딩을 활용하여 전문적이고 시각적으로 매력적인 이메일을 만드는 방법을 배웁니다.

* ### [Java에서 이메일 첨부 파일 처리](./attachments-handling/)
    **Aspose.Email for Java**를 사용하여 이메일에서 강력한 첨부 파일 작업을 구현하십시오. 임베디드 객체 및 TNEF 형식을 포함한 다양한 메시지 형식에서 첨부 파일을 추가, 추출, 제거 및 저장하는 방법을 배웁니다.

* ### [Java 이메일에서 캘린더 및 약속 관리](./calendar-appointments/)
    포괄적인 **Aspose.Email for Java** 튜토리얼을 통해 애플리케이션에서 캘린더 기능을 관리하는 방법을 알아보세요. 캘린더 항목을 만들고, 회의 요청을 생성하며, 약속 응답을 처리하고, **ICS 캘린더 파일**을 다루는 방법을 배웁니다.

* ### [Aspose.Email for Java를 사용한 Exchange Server 통합](./exchange-server-integration/)
    **Aspose.Email for Java** 튜토리얼을 통해 **Exchange Server**와 원활하게 통합하는 방법을 배우세요. Exchange 서버에 연결하고, 사서함 및 폴더에 접근하며, **Exchange Web Services (EWS)**를 사용해 메시지와 약속을 관리합니다.

* ### [Aspose.Email for Java와 IMAP 클라이언트 작업](./imap-client-operations/)
    **Aspose.Email for Java**에서 **IMAP 프로토콜**을 사용해 이메일 서버와 상호 작용하는 방법을 **IMAP 클라이언트** 튜토리얼을 통해 보여줍니다. IMAP 서버에 연결하고, 폴더를 탐색하며, 메시지를 가져오고, 고급 검색 작업을 구현하는 방법을 배웁니다.

* ### [Aspose.Email for Java와 POP3 클라이언트 작업](./pop3-client-operations/)
    자세한 **Aspose.Email for Java** 튜토리얼을 통해 **POP3 메일 클라이언트** 구현을 마스터하십시오. POP3 서버에 연결하고, 메시지를 다운로드하며, 메일 정보를 검색하고, 프로그래밍 방식으로 이메일을 처리하는 방법을 배웁니다.

* ### [Java에서 이메일 전송을 위한 SMTP 클라이언트 작업](./smtp-client-operations/)
    **SMTP 클라이언트** 튜토리얼을 통해 **Aspose.Email in Java**를 사용해 프로그래밍 방식으로 이메일을 보내는 방법을 보여줍니다. SMTP 서버를 구성하고, 보안 연결을 구현하며, 배달 알림을 처리하고, 대량 이메일 작업을 생성하는 방법을 배웁니다.

* ### [Java에서 Outlook PST 및 OST 파일 작업](./outlook-pst-ost-operations/)
    포괄적인 **Aspose.Email for Java** 튜토리얼을 통해 **Microsoft Outlook 저장 파일**을 다루는 방법을 배우세요. **PST** 및 **OST** 파일을 생성, 로드 및 조작하고, 메시지를 추출 및 저장하며, 폴더를 프로그래밍 방식으로 관리합니다.

* ### [Java에서 Outlook 데이터용 MAPI 작업](./mapi-operations/)
    자세한 **Aspose.Email for Java** 튜토리얼을 통해 **MAPI 메시지 조작**을 마스터하십시오. MAPI 속성을 다루고, 연락처, 작업, 메모와 같은 Outlook 호환 항목을 프로그래밍 방식으로 생성 및 수정하는 방법을 배웁니다.

* ### [Java 애플리케이션에서 이메일 보안 및 인증](./security-authentication/)
    **Aspose.Email for Java**를 사용해 이메일 통신을 보호하는 방법을 보안 및 인증 튜토리얼에서 보여줍니다. 이메일 암호화를 구현하고, 디지털 서명을 추가하며, DKIM 서명을 구성하고, 보안 인증을 설정하는 방법을 배웁니다.

* ### [Java에서 이메일 파싱 및 분석 기법](./email-parsing-analysis/)
    **Aspose.Email in Java**를 사용해 이메일 메시지에서 유용한 정보를 추출하는 방법을 이메일 파싱 및 분석 튜토리얼에서 보여줍니다. 이메일 헤더를 파싱하고, 수신자 정보를 추출하며, 메시지 내용을 프로그래밍 방식으로 분석하는 방법을 배웁니다.

* ### [Java에서 다양한 형식으로 이메일 변환 및 렌더링](./email-conversion-rendering/)
    자세한 **Aspose.Email for Java** 튜토리얼을 통해 이메일 변환 작업을 마스터하십시오. 다양한 이메일 형식(**EML**, **MSG**, **MHTML**, **HTML**) 간에 변환하고, 적절한 포맷으로 메시지를 렌더링하며, 시각적 충실도를 유지하는 방법을 배웁니다.

* ### [Aspose.Email for Java와 Thunderbird 및 MBOX 작업](./thunderbird-mbox-operations/)
    **Aspose.Email in Java**를 사용해 오픈소스 이메일 형식인 Thunderbird 및 MBOX를 다루는 포괄적인 가이드를 제공합니다. Thunderbird 메일 저장소에 접근하고, **MBOX 파일**을 처리하며, 아카이브에서 메시지를 추출하는 방법을 배웁니다.

* ### [Aspose.Email for Java로 이메일 보내기](./sending-emails/)
    이 포괄적인 튜토리얼을 통해 **Aspose.Email for Java**를 사용한 이메일 전송 기술을 마스터하십시오. Java 애플리케이션에서 손쉽고 효율적으로 이메일을 작성하고 전송하는 방법을 배웁니다.

* ### [Aspose.Email for Java로 이메일 수신](./receiving-emails/)
    **Aspose.Email for Java** 튜토리얼을 통해 이메일을 손쉽게 수신하고 처리하는 방법을 배우세요. 프로그래밍 방식으로 받은 편지함을 관리하고 이메일 워크플로를 간소화하십시오.

* ### [Aspose.Email for Java로 SMTP 서버 구성](./configuring-smtp-servers/)
    **Aspose.Email for Java**를 사용해 **SMTP 서버**를 손쉽게 구성하는 방법을 배우세요. 단계별 튜토리얼을 통해 원활한 이메일 전송 설정 및 모범 사례를 안내합니다.

* ### [Aspose.Email for Java와 고급 이메일 첨부 파일](./advanced-email-attachments/)
    **Aspose.Email for Java**와 함께 고급 이메일 첨부 파일 기술을 탐구하십시오. 다양한 첨부 유형을 처리하고, 대용량 파일을 관리하며, 첨부 파일 처리를 효율적으로 최적화하는 튜토리얼을 살펴봅니다.

* ### [Aspose.Email for Java로 이메일 통신 보안](./securing-email-communications/)
    **Aspose.Email for Java**를 사용해 이메일 보안을 강화하는 방법을 배우세요. 우리의 튜토리얼은 **암호화**, **디지털 서명**, 그리고 견고한 이메일 보호를 위한 보안 통신 프로토콜과 같은 필수 주제를 다룹니다.

* ### [Aspose.Email for Java로 이메일 헤더 맞춤화](./customizing-headers/)
    **Aspose.Email for Java**를 사용해 이메일 헤더를 손쉽게 맞춤화하는 방법을 배우세요. 이 튜토리얼을 통해 이메일 헤더 조작의 힘을 활용하여 메시지 제어를 강화합니다.

* ### [Aspose.Email for Java와 이메일 보안 탐구](./exploring-email-security/)
    **Aspose.Email for Java**를 사용해 이메일 보안을 심층적으로 강화하는 방법을 알아보세요. 단계별 튜토리얼과 모범 사례를 통해 Java 애플리케이션에 보안 이메일 솔루션을 구현하는 방법을 탐구합니다.

**마지막 업데이트:** 2026-10-12  
**테스트 환경:** Aspose.Email for Java 24.11  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose Email Java로 캘린더 초대 생성 및 전송](/email/java/calendar-appointments/create-send-calendar-invitations-aspose-email-java/)
- [Aspose Email Java로 다중 Ics 이벤트 읽기](/email/java/calendar-appointments/read-multiple-ics-events-aspose-email-java/)
- [Aspose.Email을 사용하여 Java에서 캘린더 항목 생성 방법](/email/java/calendar-appointments/create-save-calendar-items-aspose-email-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}