---
title: Überlegungen zum Anwendungsentwurf
ms.date: 11/04/2016
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
ms.openlocfilehash: cdb294e4ab808a7e4cbcec457f6e744eff9f12cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394662"
---
# <a name="application-design-choices"></a>Überlegungen zum Anwendungsentwurf

Dieser Artikel beschreibt einige der am Entwurfsprobleme bei der Programmierung für das Internet zu berücksichtigen.

In diesem Artikel behandelten Themen umfassen:

- [Intranet und Internet](#_core_intranet_versus_internet)

- [Client oder Server-Anwendung](#_core_client_or_server_application)

- [](#_core_the_web_page)

- [Browser oder eigenständige Anwendung](#_core_browser_or_standalone)

- [COM über das Internet](#_core_com_on_the_internet)

- [Clientdaten herunterladen Services](#_core_client_data_download_services)

Wenn Sie bereit sind, starten Sie jetzt Ihr Programm zu schreiben, finden Sie unter [Schreiben von MFC-Anwendungen](../mfc/writing-mfc-applications.md).

##  <a name="_core_intranet_versus_internet"></a> Intranet und Internet

Viele Anwendungen im Internet ausführen und für alle Benutzer mit einem Browser und der Zugriff auf das Internet zugänglich sind. Unternehmen sind auch Intranets, implementieren die unternehmensweite-Netzwerke, die über TCP/IP-Protokolle und Webbrowsern. Intranets bieten eine einfach zu erweiterbar, zentrale Quelle für unternehmensweiten Informationen. Sie können zum Aktualisieren von Software, für die Bereitstellung und Tabellarisieren "Surveys", für den Kundensupport und für die Informationsübermittlung verwendet werden. Die folgende Tabelle vergleicht die Funktionen von im Internet und Intranet.

|Internet|Intranet|
|--------------|--------------|
|Geringe Bandbreite|Hohe Bandbreite|
|Geringere Sicherheit der Daten und Systeme|Kontrollierten Zugriff auf Daten und Systeme|
|Nur minimale Kontrolle des Inhalts|Starke Kontrolle über Inhalte|

##  <a name="_core_client_or_server_application"></a> Client oder Server-Anwendung

Ihre Anwendung kann auf einem Clientcomputer oder auf einem Servercomputer ausgeführt werden. Ihre Anwendung kann auch werden gespeichert, die auf einem Server, und klicken Sie dann über das Internet heruntergeladen und auf einem Clientcomputer ausführen. MFC-WinInet-Klassen sind für Clientanwendungen zum Herunterladen von Dateien verwendet. MFC und asynchrone Monikerklassen dienen zum Herunterladen von Dateien und Steuerelementeigenschaften. Klassen für das ActiveX-Steuerelemente und aktive Dokumente werden verwendet, für Clientanwendungen und für Anwendungen, die vom Server zur Ausführung auf einem Client heruntergeladen werden.

##  <a name="_core_the_web_page"></a> Die Webseite: HTML, aktive Dokumente-ActiveX-Steuerelemente

Microsoft bietet mehrere Methoden zum Bereitstellen von Inhalt auf einer Webseite. Standard HTML oder HTML-Webseiten können Erweiterungen, z. B. Object-Tag, um dynamischen Inhalt wie z. B. ActiveX-Steuerelemente bereitzustellen.

Webbrowser anzeigen in der Regel HTML-Seiten. Aktive Dokumente können auch die Daten Ihrer Anwendung in der einfachen Point-and-Click-Schnittstelle von einem COM-fähigen Browser anzeigen. Ihre Active Document-Server kann Ihr Dokument, ein voller Frame in den gesamten Clientbereich, mit dem eigenen Menüs und Symbolleisten angezeigt werden.

ActiveX-Steuerelemente, die Sie schreiben, asynchron vom Server heruntergeladen, und auf einer Webseite angezeigt werden können. Sie können eine Skriptsprache wie VBScript verwenden, die clientseitige Validierung vor dem Senden von Informationen an den Server ausführen.

##  <a name="_core_browser_or_standalone"></a> Browser oder eigenständige Anwendung

Sie können ActiveX-Steuerelemente schreiben, die eingebettet sind, in eine HTML-Seite und der Server für aktive Dokumente, die in einem Browser angezeigt werden. Sie können HTML-Seiten schreiben, die eine Schaltfläche, um eine Anforderung zum Ausführen der ISAPI-Anwendung auf einem Webserver senden enthalten. Sie können eine eigenständige Anwendung schreiben, die Internetprotokolle zum Herunterladen von Dateien und die Informationen für Ihre Benutzer anzuzeigen, ohne jemals eine Browser-Anwendung verwendet.

##  <a name="_core_com_on_the_internet"></a> COM über das Internet

Verwenden ActiveX-Steuerelemente, aktive Dokumente und asynchronen Monikern COM (Component Object Model)-Technologien.

ActiveX-Steuerelemente bieten dynamische Inhalte auf Dokumente und Seiten auf Internet-Sites. Bei COM können Sie ActiveX-Steuerelemente und vollständige-Frame-Dokumente, die über aktive Dokumente erstellen.

Asynchrone Moniker bieten Funktionen zum Aktivieren eines Steuerelements auch in einer Internet-Umgebung, einschließlich eine inkrementelle Durchführung oder bedeutet, dass progressives Herunterladen von Daten. Steuerelemente müssen auch gut mit anderen Steuerelementen arbeiten, die auch ihre Daten asynchron zur gleichen Zeit abgerufen werden kann.

##  <a name="_core_client_data_download_services"></a> Clientdaten herunterladen Services

Zwei Sätze an APIs, mit dem Übertragen von Daten an den Client sind WinInet und asynchronen Monikern auf. Wenn Sie große GIF- und AVI-Dateien und ActiveX-Steuerelemente auf der HTML-Seite haben, können Sie die Reaktionsfähigkeit gegenüber dem Benutzer durch Herunterladen asynchron durch die Verwendung von asynchroner Monikern oder WinInet asynchrone Verwendung erhöhen.

Eine gängige Aufgabe über das Internet übertragen von Daten ist. Wenn Sie bereits verwenden Active-Technologie (z. B., wenn Sie ein ActiveX-Steuerelement verfügen), können Sie asynchrone Moniker, um Daten während des downloads progressiv zu rendern. WinInet können Sie Daten mithilfe von gängigen Internet-Protokollen wie HTTP, FTP und Gopher übertragen. Beide Methoden sind protokollunabhängig, und geben eine abstrakte Ebene, für die Verwendung WinSock und TCP/IP. Sie können weiterhin verwenden [WinSock](../mfc/windows-sockets-in-mfc.md) direkt.

Die folgende Tabelle enthält verschiedene Möglichkeiten der Verwendung von MFC zum Übertragen von Daten über das Internet.

|Verwenden Sie dieses Protokoll|Unter diesen Bedingungen|Die Verwendung dieser Klassen|
|-----------------------|----------------------------|-------------------------|
|[Internet herunterladen mithilfe von asynchronen Monikern](../mfc/asynchronous-monikers-on-the-internet.md)|Für die asynchrone Übertragung mithilfe von COM, ActiveX-Steuerelemente und alle Internetprotokoll.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|Für Internetprotokolle für HTTP, FTP und Gopher. Daten können synchron oder asynchron übertragen werden und werden in einem systemweiten-Cache gespeichert.|[CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md), und vieles mehr.|
|[WinSock](../mfc/windows-sockets-in-mfc.md)|Für maximale Effizienz und Kontrolle. Muss über Sockets und TCP/IP-Protokolle.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|

## <a name="see-also"></a>Siehe auch

[MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)<br/>
[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Asynchrone Moniker im Internet](../mfc/asynchronous-monikers-on-the-internet.md)
