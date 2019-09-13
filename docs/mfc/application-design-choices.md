---
title: Überlegungen zum Anwendungsentwurf
ms.date: 09/12/2019
helpviewer_keywords:
- design
- application design [MFC], design goals
- application design [MFC], Internet applications
- Internet applications [MFC], designing applications
- Internet [MFC], vs. intranets
- applications [MFC], Internet
- server applications [MFC], vs. client applications on Internet
- client applications [MFC], vs. server applications on Internet
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
ms.openlocfilehash: b205599ed3bf33e84516120b1855482797b86c9b
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924915"
---
# <a name="application-design-choices"></a>Überlegungen zum Anwendungsentwurf

In diesem Artikel werden einige der Entwurfs Probleme erläutert, die beim Programmieren für das Internet zu beachten sind.

Zu den in diesem Artikel behandelten Themen gehören:

- [Intranet und Internet](#_core_intranet_versus_internet)

- [Client-oder Server Anwendung](#_core_client_or_server_application)

- [Die Webseite](#_core_the_web_page)

- [Browser oder eigenständige Anwendung](#_core_browser_or_standalone)

- [COM im Internet](#_core_com_on_the_internet)

- [Download Dienste für Client Daten](#_core_client_data_download_services)

Wenn Sie bereit sind, das Programm jetzt zu schreiben, finden Sie weitere Informationen unter [Schreiben von MFC-Anwendungen](../mfc/writing-mfc-applications.md).

##  <a name="_core_intranet_versus_internet"></a>Intranet und Internet

Viele Anwendungen werden im Internet ausgeführt und sind für alle Benutzer mit Browser-und Internet Zugriff zugänglich. Unternehmen implementieren auch Intranets, bei denen es sich um unternehmensweite Netzwerke mit TCP/IP-Protokollen und Webbrowser handelt. Intranets bieten eine leicht erweiterbare, zentrale Quelle für unternehmensweite Informationen. Sie können zum Aktualisieren von Software, zum Bereitstellen und Tabulieren von Umfragen, zum Kundensupport und zur Informationsübermittlung verwendet werden. In der folgenden Tabelle werden die Features von Internet und Intranets verglichen.

|Internet|Intranet|
|--------------|--------------|
|Geringe Bandbreite|Hohe Bandbreite|
|Reduzierte Sicherheit von Daten und Systemen|Kontrollierter Zugriff auf Daten und Systeme|
|Minimale Kontrolle von Inhalten|Hohe Kontrolle über Inhalte|

##  <a name="_core_client_or_server_application"></a>Client-oder Server Anwendung

Die Anwendung kann auf einem Client Computer oder auf einem Server Computer ausgeführt werden. Die Anwendung kann auch auf einem Server gespeichert und dann über das Internet heruntergeladen und auf einem Client Computer ausgeführt werden. MFC-WinInet-Klassen werden für Client Anwendungen verwendet, um Dateien herunterzuladen. MFC-und asynchrone Monikerklassen werden verwendet, um Dateien herunterzuladen und Eigenschaften zu steuern. Klassen für ActiveX-Steuerelemente und aktive Dokumente werden für Client Anwendungen und Anwendungen verwendet, die vom Server zum Ausführen auf einem Client heruntergeladen werden.

##  <a name="_core_the_web_page"></a>Die Webseite: HTML, aktive Dokumente, ActiveX-Steuerelemente

Microsoft bietet verschiedene Methoden zum Bereitstellen von Inhalten auf einer Webseite. Webseiten können Standard-HTML-oder HTML-Erweiterungen, wie z. b. das Objekttag, verwenden, um dynamischen Inhalt wie ActiveX-Steuerelemente bereitzustellen.

Webbrowser zeigen in der Regel HTML-Seiten an. Aktive Dokumente können die Daten Ihrer Anwendung auch in der einfachen Point-and-Click-Schnittstelle eines com-fähigen Browsers anzeigen. Der aktive Dokument Server kann das Dokument, den vollständigen Frame im gesamten Client Bereich, mit eigenen Menüs und Symbolleisten anzeigen.

ActiveX-Steuerelemente, die Sie schreiben, können asynchron vom Server heruntergeladen und auf einer Webseite angezeigt werden. Sie können eine Skriptsprache wie VBScript verwenden, um die Client seitige Validierung vor dem Senden von Informationen an den Server auszuführen.

##  <a name="_core_browser_or_standalone"></a>Browser oder eigenständige Anwendung

Sie können ActiveX-Steuerelemente schreiben, die in eine HTML-Seite und aktive Dokument Server eingebettet sind, die in einem Browser angezeigt werden. Sie können HTML-Seiten schreiben, die eine Schaltfläche enthalten, um eine Anforderung zum Ausführen Ihrer ISAPI-Anwendung auf einem Webserver zu übermitteln. Sie können eine eigenständige Anwendung schreiben, die Internet Protokolle zum Herunterladen von Dateien und zum Anzeigen der Informationen für Ihren Benutzer verwendet, ohne eine Browser Anwendung zu verwenden.

##  <a name="_core_com_on_the_internet"></a>COM im Internet

ActiveX-Steuerelemente, aktive Dokumente und asynchrone Moniker verwenden alle com-Technologien (Component Object Model).

ActiveX-Steuerelemente stellen dynamische Inhalte für Dokumente und Seiten auf Internet Sites bereit. Mit com können Sie ActiveX-Steuerelemente und vollständige Frame Dokumente mithilfe aktiver Dokumente erstellen.

Asynchrone Moniker stellen Funktionen bereit, mit denen ein Steuerelement in einer Internet Umgebung gut funktionieren kann, einschließlich einer inkrementellen oder progressiven Möglichkeit zum Herunterladen von Daten. Steuerelemente müssen auch gut mit anderen Steuerelementen funktionieren, die Ihre Daten möglicherweise gleichzeitig asynchron abrufen.

##  <a name="_core_client_data_download_services"></a>Download Dienste für Client Daten

Zwei Gruppen von APIs, die bei der Übertragung von Daten an Ihren Client helfen, sind WinInet-und asynchrone Moniker. Wenn Sie über umfangreiche GIF-und AVI-Dateien und ActiveX-Steuerelemente auf der HTML-Seite verfügen, können Sie die Reaktionsfähigkeit des Benutzers erhöhen, indem Sie asynchron herunterladen, indem Sie asynchrone Moniker verwenden oder WinInet asynchron verwenden.

Eine gängige Aufgabe im Internet ist das Übertragen von Daten. Wenn Sie bereits aktive Technologie verwenden (z. b. Wenn Sie über ein ActiveX-Steuerelement verfügen), können Sie asynchrone Moniker verwenden, um beim Herunterladen progressiv Daten zu erzeugen. Sie können WinInet zum Übertragen von Daten mithilfe allgemeiner Internet Protokolle wie http, FTP und Gopher verwenden. Beide Methoden stellen die Protokoll Unabhängigkeit bereit und bieten eine abstrakte Ebene für die Verwendung von Winsock und TCP/IP. Sie können [Winsock](../mfc/windows-sockets-in-mfc.md) weiterhin direkt verwenden.

In der folgenden Tabelle werden verschiedene Möglichkeiten für die Verwendung von MFC zum Übertragen von Daten über das Internet zusammengefasst.

|Dieses Protokoll verwenden|Unter diesen Bedingungen|Verwenden dieser Klassen|
|-----------------------|----------------------------|-------------------------|
|[Internet Download mithilfe von asynchronen Monikern](../mfc/asynchronous-monikers-on-the-internet.md)|Für die asynchrone Übertragung mit com, ActiveX-Steuerelementen und einem beliebigen Internet Protokoll.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|Für Internet Protokolle für http, FTP und Gopher. Daten können synchron oder asynchron übertragen und in einem systemweiten Cache gespeichert werden.|[Cinternetzession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)und vieles mehr.|
|[WinSock](../mfc/windows-sockets-in-mfc.md)|Für maximale Effizienz und Kontrolle. Erfordert Kenntnisse der Sockets-und TCP/IP-Protokolle.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|

## <a name="see-also"></a>Siehe auch

[MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)<br/>
[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Asynchrone Moniker im Internet](../mfc/asynchronous-monikers-on-the-internet.md)
