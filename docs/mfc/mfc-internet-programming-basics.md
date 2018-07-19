---
title: MFC-Internetprogrammiergrundlagen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6896daddc0eb900f9e2a29497eb2dd8a1dc78446
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255608"
---
# <a name="mfc-internet-programming-basics"></a>Grundlagen der MFC-Internetprogrammierung
Microsoft bietet viele APIs zur Programmierung von Client- und serveranwendungen. Viele neue Anwendungen für das Internet geschrieben werden, und als Technologien, Browserfunktionen und Optionen sicherheitsänderung, neue Typen von Anwendungen geschrieben werden. Webbrowsertypen auf Clientcomputern Bereitstellen des Zugriffs auf das World Wide Web und Anzeigen von HTML-Seiten, die Text, Grafiken, ActiveX-Steuerelemente und Dokumente enthalten. Server FTP, HTTP und Gopher-Dienste bereitstellen und Ausführen von CGI-Erweiterung serveranwendungen. Die benutzerdefinierte Anwendung kann Abrufen von Informationen und Daten im Internet angeben.  
  
 ![Client- und serveranwendungen](../mfc/media/vc38bq1.gif "vc38bq1")  
  
 MFC enthält Klassen, die internetprogrammierung unterstützen. Sie können [COleControl](../mfc/reference/colecontrol-class.md) und [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) und verwandten MFC-Klassen zum Schreiben von ActiveX-Steuerelemente und aktive Dokumente. Sie können MFC-Klassen wie z. B. [CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md), und [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) zum Abrufen von Dateien und Informationen über Internet-Protokolle wie FTP, HTTP- und Gopher.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
-   [Internetbezogene MFC-Klassen](../mfc/internet-related-mfc-classes.md)  
  
-   [Themenliste für Internetinformationen](../mfc/internet-information-by-topic.md)  
  
-   [Internetinformation – nach Aufgaben geordnet](../mfc/internet-information-by-task.md)  
  
-   [Active Technology für das Internet](../mfc/active-technology-on-the-internet.md)  
  
-   [WinInet-Grundlagen](../mfc/wininet-basics.md)  
  
-   [Grundlagen zu HTML](../mfc/html-basics.md)  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
-   [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md)  
  
-   [Aktive Dokumente für das Internet](../mfc/active-documents-on-the-internet.md)  
  
-   [Asynchrone Moniker im Internet](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)  
  
-   [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)  
  
-   [Überlegungen zum Anwendungsentwurf](../mfc/application-design-choices.md)  
  
-   [Schreiben von MFC-Anwendungen](../mfc/writing-mfc-applications.md)  
  
-   [Testen von Internetanwendungen](../mfc/testing-internet-applications.md)  
  
-   [Internetsicherheit](../mfc/internet-security-cpp.md)  
  
-   [ATL-Unterstützung für DHTML-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)  
  
##  <a name="_core_web_sites_for_more_information"></a> Websites für Weitere Informationen  
 Weitere Informationen über die Microsoft Internet-Technologie finden Sie unter der [Microsoft Developer Network (MSDN)](http://go.microsoft.com/fwlink/p/?linkid=56322) Website. (Links können ohne vorherige Ankündigung ändern.)  
  
 Diese Website für Entwickler enthält Informationen zum Verwenden von Entwicklungstools von Microsoft und Technologien und Top Storys zum aktuellen und zukünftigen Konferenzen. Auf dieser Seite können Sie zu viele Verwandte Entwicklerwebsites, einschließlich .NET und XML Developer Center wechseln. Sie können auch Beta-SDKs und Beispiele herunterladen.  
  
 Die [World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/p/?linkid=37125) veröffentlicht Spezifikationen für HTML, HTTP, CGI und anderen World Wide Web-Technologien.  
  
##  <a name="_core_more_internet_help"></a> Weitere Internethilfe  
 OLE-Abschnitt des Windows SDK enthält zusätzliche Informationen zur OLE-Programmierung. Diese Informationen liefern Weitere Informationen zur Verwendung der Win32-WinInet-Funktionen, sondern direkt über die MFC-Klassen. Es enthält auch allgemeine Informationen über das Internet-Technologien.  
  
## <a name="see-also"></a>Siehe auch  



