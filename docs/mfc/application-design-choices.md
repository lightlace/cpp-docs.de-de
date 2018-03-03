---
title: Anwendungsentwurf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b78c4c086b40f786d86411c99279245704a48a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="application-design-choices"></a>Überlegungen zum Anwendungsentwurf
Dieser Artikel beschreibt einige der Entwurfsprobleme bei der Programmierung für das Internet zu berücksichtigen.  
  
 In diesem Artikel behandelten Themen werden behandelt:  
  
-   [Intranet und Internet](#_core_intranet_versus_internet)  
  
-   [Client oder Server-Anwendung](#_core_client_or_server_application)  
  
-   [](#_core_the_web_page)  
  
-   [Browser oder eine eigenständige Anwendung](#_core_browser_or_standalone)  
  
-   [COM im Internet](#_core_com_on_the_internet)  
  
-   [Clientdaten laden Services](#_core_client_data_download_services)  
  
 Wenn Sie bereit sind, starten Sie das Programm jetzt schreiben, finden Sie unter [Schreiben von MFC-Anwendungen](../mfc/writing-mfc-applications.md).  
  
##  <a name="_core_intranet_versus_internet"></a>Intranet und Internet  
 Viele Clientanwendungen im Internet ausgeführt werden und sind für Personen, die mit einem Browser und Zugriff auf das Internet zugegriffen werden kann. Unternehmen sind zusätzliche Intranets, implementieren die unternehmensweite Netzwerke, die über TCP/IP-Protokolle und Webbrowser. Intranets stellen eine einfach erweiterbare zentralen Quelle für die unternehmensweiten Informationen. Sie können zum Aktualisieren von Software, für die Bereitstellung und Tabellarisieren Umfragen, für den Kundensupport und für die Informationsübermittlung verwendet werden. Die folgende Tabelle vergleicht die Funktionen von Internet und Intranet.  
  
|Internet|Intranet|  
|--------------|--------------|  
|Nur eine geringe Bandbreite|Hohe Bandbreite|  
|Geringere Sicherheit von Daten und Systemen|Kontrollierten Zugriff auf Daten und Systeme|  
|Nur minimale Kontrolle des Inhalts|Hohe Steuerelement des Inhalts|  
  
##  <a name="_core_client_or_server_application"></a>Client oder Server-Anwendung  
 Die Anwendung möglicherweise auf einem Clientcomputer oder auf einem Servercomputer ausgeführt werden. Die Anwendung kann auch werden auf einem Server gespeichert und dann über das Internet heruntergeladen und auf einem Clientcomputer ausgeführt. MFC-WinInet-Klassen sind für Clientanwendungen verwendet, um Dateien herunterzuladen. MFC- und asynchrone Monikerklassen dienen zum Herunterladen von Dateien und Eigenschaften zu steuern. Klassen für ActiveX-Steuerelemente und aktive Dokumente werden verwendet, für Clientanwendungen und Anwendungen, die vom Server zur Ausführung auf einem Client heruntergeladen werden.  
  
##  <a name="_core_the_web_page"></a>Die Webseite: HTML, aktive Dokumente ActiveX-Steuerelemente  
 Microsoft bietet mehrere Methoden zum Bereitstellen von Inhalt auf einer Webseite. Standard HTML- oder HTML-Webseiten können Erweiterungen, z. B. das Objekttag, dynamische Inhalte wie z. B. ActiveX-Steuerelemente bereit.  
  
 Webbrowser anzeigen in der Regel HTML-Seiten. Aktive Dokumente können auch Ihre Anwendung Daten in die einfache Point-and-Click-Schnittstelle von einem COM-fähigen Browser anzeigen. Active Document-Server kann Ihrem Dokument, vollständigen Frame in der gesamte Clientbereich mit Menüs und Symbolleisten angezeigt werden.  
  
 ActiveX-Steuerelemente, die Sie schreiben können asynchron vom Server heruntergeladen und auf einer Webseite angezeigt werden. Sie können eine Skriptsprache wie VBScript verwenden, eine clientseitige gültigkeitsprüfung vor dem Senden von Informationen an den Server ausführen.  
  
##  <a name="_core_browser_or_standalone"></a>Browser oder eine eigenständige Anwendung  
 Sie können ActiveX-Steuerelemente schreiben, die eingebettet sind, in einer HTML-Seite und Server für aktive Dokumente, die in einem Browser angezeigt werden. Sie können HTML-Seiten schreiben, die eine Schaltfläche, um eine Anforderung zum Ausführen der ISAPI-Anwendung auf einem Webserver zu senden enthalten. Sie können eine eigenständige Anwendung schreiben, die Internetprotokolle zum Herunterladen von Dateien und die Informationen, die für Benutzer anzuzeigen, ohne jemals eine Browseranwendung verwendet.  
  
##  <a name="_core_com_on_the_internet"></a>COM im Internet  
 ActiveX-Steuerelemente, aktive Dokumente und asynchronen Monikern COM (Component Object Model)-Technologien verwendet werden.  
  
 ActiveX-Steuerelemente werden dynamische Inhalte für Dokumente und Seiten auf Internet-Sites bereitstellen. Bei COM können Sie ActiveX-Steuerelemente und aktive Dokumente mit Full-Frame-Dokumente erstellen.  
  
 Asynchrone Moniker stellen die Funktionen zum Aktivieren eines Steuerelements auszuführenden auch in einer Internet-Umgebung, z. B. eine inkrementelle oder progressives Herunterladen von Daten bedeutet, dass. Steuerelemente müssen auch gut mit anderen Steuerelementen arbeiten, die auch ihre Daten asynchron zur gleichen Zeit abgerufen werden kann.  
  
##  <a name="_core_client_data_download_services"></a>Clientdaten laden Services  
 Zwei Sätze von APIs, die Datenübertragung an den Client hilft sind WinInet und asynchronen Monikern. Wenn Sie große GIF- und AVI-Dateien und ActiveX-Steuerelemente in der HTML-Seite haben, können Sie die Reaktionszeit für den Benutzer asynchron ausgeführt wird, entweder durch Verwendung von asynchronen Monikern oder WinInet asynchron herunterladen erhöhen.  
  
 Eine häufige Aufgabe im Internet ist die Übertragung von Daten. Wenn Sie bereits verwenden Active-Technologie (z. B. haben ein ActiveX-Steuerelement), können Sie asynchrone Monikern, um Daten während des downloads progressiv zu rendern. WinInet können Daten mithilfe von common Internetprotokolle wie HTTP, FTP und Gopher übertragen werden. Beide Methoden sind protokollunabhängig und bieten eine abstrakte Ebene mithilfe von WinSock und TCP/IP. Sie können weiterhin [WinSock](../mfc/windows-sockets-in-mfc.md) direkt.  
  
 In der folgenden Tabelle werden verschiedene Methoden zur Verwendung von MFC zum Übertragen von Daten über das Internet zusammengefasst.  
  
|Verwenden Sie dieses Protokoll|Unter diesen Bedingungen|Verwenden diese Klassen|  
|-----------------------|----------------------------|-------------------------|  
|[Internet herunterladen mithilfe von asynchronen Monikern](../mfc/asynchronous-monikers-on-the-internet.md)|Für asynchrone Übertragung mithilfe von COM, ActiveX-Steuerelemente, und alle Internetprotokoll.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|  
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|Für Internetprotokolle HTTP, FTP und Gopher. Daten können synchron oder asynchron übertragen werden und werden in einem systemweiten Cache gespeichert.|[CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md), und vieles mehr.|  
|[WinSock](../mfc/windows-sockets-in-mfc.md)|Maximaler Effizienz und Steuerung. Erfordert Kenntnisse über Sockets und TCP/IP-Protokolle an.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [MFC-Internetprogrammiergrundlagen](../mfc/mfc-internet-programming-basics.md)   
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Asynchrone Moniker im Internet](../mfc/asynchronous-monikers-on-the-internet.md)

