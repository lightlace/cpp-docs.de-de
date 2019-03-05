---
title: Grundlagen der MFC-Internetprogrammierung
ms.date: 11/19/2018
helpviewer_keywords:
- ISAPI extensions, programming with ISAPI
- Internet applications [MFC]
- ISAPI
- ActiveX controls [MFC], Internet
- programming [MFC], Internet
- Web applications [MFC], MFC classes
- ISAPI filters [MFC], programming with ISAPI
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], writing
- Internet applications [MFC], Active technology
- Active technology [MFC]
- Internet content [MFC]
- WinInet classes [MFC]
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
ms.openlocfilehash: 37fe5486d6d41ad182779a3a15b0aca3af51d04b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288440"
---
# <a name="mfc-internet-programming-basics"></a>Grundlagen der MFC-Internetprogrammierung

Microsoft bietet viele APIs für die Programmierung von Client- und serveranwendungen. Viele neue Anwendungen für das Internet geschrieben werden, und als Technologien, Browserfunktionen und Sicherheit ändern, neue Arten von Anwendungen geschrieben werden. Browser führen Sie auf den Clientcomputern den Zugriff auf das World Wide Web und Anzeigen von HTML-Seiten, die Text, Grafiken, ActiveX-Steuerelemente und Dokumente enthalten. Server FTP, HTTP und Gopher-Dienste bereitzustellen, und führen die Erweiterung-serveranwendungen mit CGI. Ihre benutzerdefinierte Anwendung kann Informationen abrufen und Daten im Internet bereitstellen.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

![Client- und serveranwendungen](../mfc/media/vc38bq1.gif "Client- und serveranwendungen")

MFC enthält Klassen, die internetprogrammierung unterstützen. Sie können [COleControl](../mfc/reference/colecontrol-class.md) und [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) und verwandte Klassen von MFC-ActiveX-Steuerelemente und aktive Dokumente zu schreiben. Sie können MFC-Klassen wie z. B. [CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md), und [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) zum Abrufen von Dateien und Informationen über Internet-Protokolle wie FTP, HTTP und Gopher.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Internetbezogene MFC-Klassen](../mfc/internet-related-mfc-classes.md)

- [Themenliste für Internetinformationen](../mfc/internet-information-by-topic.md)

- [Internetinformation – nach Aufgaben geordnet](../mfc/internet-information-by-task.md)

- [Active Technology für das Internet](../mfc/active-technology-on-the-internet.md)

- [WinInet-Grundlagen](../mfc/wininet-basics.md)

- [Grundlagen zu HTML](../mfc/html-basics.md)

## <a name="related-sections"></a>Verwandte Abschnitte

- [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md)

- [Asynchrone Moniker im Internet](../mfc/asynchronous-monikers-on-the-internet.md)

- [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)

- [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)

- [Überlegungen zum Anwendungsentwurf](../mfc/application-design-choices.md)

- [Schreiben von MFC-Anwendungen](../mfc/writing-mfc-applications.md)

- [Testen von Internetanwendungen](../mfc/testing-internet-applications.md)

- [Internetsicherheit](../mfc/internet-security-cpp.md)

- [ATL-Unterstützung für DHTML-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)

##  <a name="_core_web_sites_for_more_information"></a> Websites für Weitere Informationen

Weitere Informationen zu Microsoft Internet-Technologie, finden Sie unter den [Microsoft Developer Network (MSDN)](http://go.microsoft.com/fwlink/p/?linkid=56322) Website. (Links können ohne vorherige Ankündigung ändern.)

Diese Website für Entwickler enthält Informationen zur Verwendung von Microsoft-Entwicklungstools und Technologien und Top-Berichte über aktuelle und bevorstehende Konferenzen. Auf dieser Seite können Sie zu viele verwandte Websites für Entwickler, einschließlich .NET und XML-Developer Center wechseln. Sie können auch die Beta-SDKs und Beispiele herunterladen.

Die [World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/p/?linkid=37125) Spezifikationen für HTML, HTTP, CGI und andere Technologien www veröffentlicht.

##  <a name="_core_more_internet_help"></a> Weitere Internethilfe

Der OLE-Abschnitt des Windows SDK enthält zusätzliche Informationen zu OLE-Programmierung. Diese Informationen liefern Informationen zur Verwendung von der Win32-WinInet-Funktionen, sondern direkt über die MFC-Klassen. Es enthält auch allgemeine Informationen über das Internet-Technologien.

## <a name="see-also"></a>Siehe auch
