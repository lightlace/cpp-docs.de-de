---
title: "&#220;berlegungen zum Anwendungsentwurf"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsentwurf [C++], Entwurfsziele"
  - "Anwendungsentwurf [C++], Internetanwendungen"
  - "Anwendungen [MFC], Internet"
  - "Clientanwendungen [C++], kontra Serveranwendungen im Internet"
  - "Entwurf"
  - "Internet [C++], kontra Intranets"
  - "Internetanwendungen [C++], Entwerfen von Anwendungen"
  - "Serveranwendungen, kontra Clientanwendungen im Internet"
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;berlegungen zum Anwendungsentwurf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel enthält einige der Entwurfsprobleme, um bei der Programmierung zu berücksichtigen für Internet.  
  
 Themen beschrieben in diesem Artikeleinschließung:  
  
-   [Intranet und Internet](#_core_intranet_versus_internet)  
  
-   [Client oder Serveranwendung](#_core_client_or_server_application)  
  
-   [Die Webseite: HTML, aktive Dokumente, ActiveX\-Steuerelemente](#_core_the_web_page.3a_.html.2c_.activex_documents.2c_.activex_controls)  
  
-   [Browser oder eigenständige Anwendung](#_core_browser_or_stand.2d.alone_application)  
  
-   [COM auf dem Internet](#_core_com_on_the_internet)  
  
-   [Client\-Daten\-Download\-Dienstleistungen](#_core_client_data_download_services)  
  
 Wenn Sie bereit sind, das Programm jetzt schreiben starten können, finden Sie unter [Schreiben\-MFC\-Anwendungen](../mfc/writing-mfc-applications.md).  
  
##  <a name="_core_intranet_versus_internet"></a> Intranet und Internet  
 Viele Anwendungen, die auf das Internet ausgeführt und sind zu jeder mit einem Browser und einen Internetzugang verfügbar.  Unternehmen implementieren auch Intranets, die Unternehmen\-weite Netzwerke mit TCP\/IP\-Protokolle und \-Webbrowser sind.  Intranet ermöglichen eine leicht aktualisierbare, zentrale Quelle zu Unternehmen\-weiter Informationen an.  Sie können zum Aktualisieren der Software, für die Realisierung und das Tabellieren von Umfragen, für den Produktsupport und für Informationszustellung verwendet werden.  In der folgenden Tabelle werden Features des Internet und Intranet der.  
  
|Internet|Intranet|  
|--------------|--------------|  
|Niedrige Bandbreite|Hohe Bandbreite|  
|Reduzierte Sicherheit von Daten von Systemen und|Kontrollierter Zugriff auf Daten sowie auf Systemen|  
|Minimales Steuerung des Inhalts|Hohes Steuerung des Inhalts|  
  
##  <a name="_core_client_or_server_application"></a> Client oder Serveranwendung  
 Die Anwendung ist möglicherweise auf einen Clientcomputer oder auf einem Servercomputer ausgeführt.  Die Anwendung ist auf einen Server auch gespeichert werden und dann über das Internet und Ausführung auf einem Clientcomputer heruntergeladen werden.  Klassen MFC\-WinInet\-Unterstützung werden verwendet, damit Clientanwendungen Dateien herunterladen.  MFC und asynchrone Monikerklassen werden verwendet, um Dateien und Steuerelementeigenschaften herunterzuladen.  Klassen für ActiveX\-Steuerelemente und aktiven Dokumente sind für Clientanwendungen und für Anwendungen verwendet, die vom Server heruntergeladen werden, um auf einem Clientcomputer ausgeführt werden.  
  
##  <a name="_core_the_web_page.3a_.html.2c_.activex_documents.2c_.activex_controls"></a> Die Webseite: HTML, aktive Dokumente, ActiveX\-Steuerelemente  
 Microsoft bietet mehrere Möglichkeiten zum Bereitstellen von Inhalt auf einer Webseite.  Webseiten können standardmäßige HTML oder HTML\-Erweiterungen, wie das Objekttag verwenden, um dynamischen Inhalt wie ActiveX\-Steuerelemente bereitzustellen.  
  
 Der Webbrowser HTML\-Seiten Anzeige in der Regel.  Active Documents können die Daten der Anwendung in einfacher Schnittstelle zum Anzeigen und Klicken eines COM\-aktivierten Browser anzeigen.  das Active Document\-Server kann das Dokument, vollständige Frame anzeigen im gesamten Clientbereich, mit seinen eigenen Menüs und Symbolleisten.  
  
 ActiveX\-Steuerelemente, die Sie schreiben, können vom Server asynchron heruntergeladen und auf einer Webseite angezeigt werden.  Sie können einer Skriptsprache wie VBScript verwenden, um clientseitige Validierungen auszuführen, bevor Sie Informationen an den Server senden.  
  
##  <a name="_core_browser_or_stand.2d.alone_application"></a> Browser oder eigenständige Anwendung  
 Sie können ActiveX\-Steuerelemente schreiben, die in einer HTML\-Seite und in den Active Document\-Servern eingebettet werden, die in einem Browser angezeigt werden.  Sie können HTML\-Seiten schreiben, die eine Schaltfläche enthält, um eine Anforderung gesendet werden, die ISAPI\-Anwendung auf einem Webserver auszuführen.  Sie können keine eigenständige Anwendung, die Internetprotokolle verwendet, um Dateien herunterzuladen und die Informationen für den Benutzer anzuzeigen, ohne jemals mit eine Browseranwendung schreiben.  
  
##  <a name="_core_com_on_the_internet"></a> COM auf dem Internet  
 ActiveX\-Steuerelemente, aktive Dokumente und asynchrone Moniker alle verwenden Technologien COM \(Component Object Model\).  
  
 ActiveX\-Steuerelemente stellen dynamischen Inhalt zu Dokumenten und den Seiten auf Internetsites bereit.  Mit COM ActiveX\-Steuerelemente und FULLFramedokumente mit der aktiven Dokumente erstellen.  
  
 Asynchrone Moniker bieten Funktionen, um ein Steuerelement zu aktivieren, um die in einer Internet\-Umgebung, darunter ein inkrementelles oder Progressistmittel auszuführen, die Daten herunterzuladen.  Steuerelemente müssen sich mit anderen Steuerelementen bearbeiten, die möglicherweise auch ihre Daten asynchron gleichzeitig abrufen.  
  
##  <a name="_core_client_data_download_services"></a> Client\-Daten\-Download\-Dienstleistungen  
 Zwei Sätze APIs, die Daten auf dem Client unterstützen, sind WinInet\-Klassen und asynchrone Moniker.  Wenn Sie ein großes .gif und AVI\-Dateien und ActiveX\-Steuerelemente auf der HTML\-Seite haben, können Sie die Reaktionszeit auf den Benutzer erhöhen, indem Sie asynchron, entweder herunterladen, indem Sie asynchron asynchrone Moniker verwenden oder WinInet\-Klassen verwenden.  
  
 Eine übliche Aufgabe im Internet überträgt Daten.  Wenn bereits Active Technology ablegen \(beispielsweise, wenn Sie ein ActiveX\-Steuerelement haben\), können Sie asynchrone Moniker verwenden, um Daten als es progressiv zu rendern herunterladen.  Sie können WinInet\-Klassen für Datenübertragung mit der allgemeinen Internetprotokolle wie HTTP, FTP und Gopher verwenden.  Beide Methoden übergeben Protokollunabhängigkeit und stellen eine abstrakte Ebene zur Anwendung von Winsock\-Schnittstelle und von TCP\/IP bereit.  Sie können [Winsock\-Schnittstelle](../mfc/windows-sockets-in-mfc.md) noch direkt verwenden.  
  
 In der folgenden Tabelle werden einige Möglichkeiten der Verwendung der MFC\-Features für Datenübertragung über das Internet. zusammen  
  
|Verwenden Sie dieses Protokoll|Unter diesen Bedingungen|Mit diesen Klassen|  
|------------------------------------|------------------------------|------------------------|  
|[Internet\-Downloading mithilfe asynchroner Moniker](../mfc/asynchronous-monikers-on-the-internet.md)|Für asynchrone Übertragung mit COM, ActiveX\-Steuerelemente und beliebigen h.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|  
|[WinInet\-Klassen](../mfc/win32-internet-extensions-wininet.md)|Für Internetprotokolle für HTTP, FTP und Gopher.  Daten können synchron oder asynchron übergeben werden und werden in einen systemweiten Cache gespeichert.|[CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) und viele andere mehr.|  
|[Winsock\-Schnittstelle](../mfc/windows-sockets-in-mfc.md)|Um maximale Effizienz und Steuerelement.  Requires Verständnis von und Sockets OF TCP\/IP\-Protokollen.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|  
  
## Siehe auch  
 [MFC\-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)   
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Asynchrone Moniker im Internet](../mfc/asynchronous-monikers-on-the-internet.md)