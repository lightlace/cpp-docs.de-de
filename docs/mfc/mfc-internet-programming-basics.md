---
title: "Grundlagen der MFC-Internetprogrammierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Active Technology [C++]"
  - "ActiveX-Steuerelemente [C++], Internet"
  - "Internetanwendungen [C++]"
  - "Internetanwendungen [C++], Active Technology"
  - "Internetanwendungen [C++], ActiveX-Steuerelemente"
  - "Internetanwendungen [C++], Schreiben"
  - "Internetinhalt [C++]"
  - "ISAPI"
  - "ISAPI-Erweiterungen, Programmieren mit ISAPI"
  - "ISAPI-Filter, Programmieren mit ISAPI"
  - "[C++]-Programmierung, Internet"
  - "Webanwendungen [C++], MFC-Klassen"
  - "WinInet-Klassen"
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Grundlagen der MFC-Internetprogrammierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft stellt viele APIs für Programmierungs Client\- und Serveranwendungen bereit.  Viele neue Anwendungen werden für Internet geschrieben, und wenn Technologien, Browserfunktionen und Sicherheitsoptionen ändern, werden neue Typen von Anwendungen geschrieben.  Browser ausgeführt auf die Clientcomputer, Zugriff auf das World Wide Web bereitzustellen und zeigen HTML\-Seiten an, die Text\-, Grafik\-, ActiveX\-Steuerelemente und Dokumente umfasst.  Server stellen HTTP, FTP und Gopher\-Dienstleistungen und Ausführungsservererweiterungs\-Anwendungen mithilfe CGI bereit.  die benutzerdefinierte Anwendung kann Informationen abrufen und Daten im Internet bereitstellen.  
  
 ![Client&#45; und Serveranwendungen](../mfc/media/vc38bq1.png "vc38BQ1")  
  
 MFC stellt Klassen bereit, die Internet\-Programmierung unterstützen.  Sie können [COleControl](../mfc/reference/colecontrol-class.md) und [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) und verwandte MFC\-Klassen verwenden, ActiveX\-Steuerelemente und Active Documents zu schreiben.  Sie können MFC\-Klassen wie [CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md) und [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) verwenden, um Dateien und Informationen über Internetprotokolle wie HTTP, FTP und Gopher abzurufen.  
  
## In diesem Abschnitt  
  
-   [Internet\-verknüpfte MFC\-Klassen](../mfc/internet-related-mfc-classes.md)  
  
-   [Internet\-Informationen durch Thema](../mfc/internet-information-by-topic.md)  
  
-   [Internet\-Informationen von Aufgabe](../mfc/internet-information-by-task.md)  
  
-   [Active Technology im Internet](../mfc/active-technology-on-the-internet.md)  
  
-   [WinInet\-Grundlagen](../mfc/wininet-basics.md)  
  
-   [Grundlagen von HTML](../mfc/html-basics.md)  
  
-   [Grundlagen von HTTP](../mfc/http-basics.md)  
  
## Verwandte Abschnitte  
  
-   [ActiveX\-Steuerelemente im Internet](../mfc/activex-controls-on-the-internet.md)  
  
-   [Active Documents im Internet](../mfc/active-documents-on-the-internet.md)  
  
-   [Asynchrone Moniker im Internet](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Win32\-Internet\-Erweiterungen \(WinInet\-Klassen\)](../mfc/win32-internet-extensions-wininet.md)  
  
-   [MFC\-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)  
  
-   [Anwendungs\-Entwurfs\-Auswahlen](../mfc/application-design-choices.md)  
  
-   [Schreiben\-MFC\-Anwendungen](../mfc/writing-mfc-applications.md)  
  
-   [Tests\-Internet\-Anwendungen](../mfc/testing-internet-applications.md)  
  
-   [Bei](../mfc/internet-security-cpp.md)  
  
-   [ATL\-Unterstützung für DHTML\-Kontrollen](../atl/atl-support-for-dhtml-controls.md)  
  
##  <a name="_core_web_sites_for_more_information"></a> Websites zu Informationen  
 Weitere Informationen über Microsoft\-Internet\-Technologie finden Sie unter [Microsoft Developer Network \(MSDN\)](http://go.microsoft.com/fwlink/?LinkID=56322) auf der Website. \(Links ändern kann ohne Ankündigung.\)  
  
 Diese Website für Entwickler enthält Informationen über das Einfügen von Microsoft\-Entwicklungswerkzeugen und Technologien und Topnachrichten zu neuen und bevorstehenden Konferenzen.  Auf dieser Seite können Sie mit zahlreichen verknüpfte Entwicklersites, einschließlich .NET wechseln und an XML\-DeveloperCentern.  Sie können Beta\-SDKs und Beispiele herunterladen.  
  
 [World Wide Web Consortium \(W3C\)](http://go.microsoft.com/fwlink/?LinkID=37125) Veröffentlicht Spezifikation für HTML\-Code, HTTP, CGI und andere World Wide Web\-Technologien.  
  
##  <a name="_core_more_internet_help"></a> Weitere Internet\-Hilfe  
 Der OLE\-Abschnitt [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] enthält zusätzliche Informationen über OLE\-Programmierung.  Diese Informationen geben Informationen über die Features Win32\- WinInet\-Klassen direkt verwenden, statt die von MFC\-Klassen bereit.  Außerdem enthält Übersichtsinformationen über Internet\-Technologien.  
  
## Siehe auch  
 [MFC Internet Programming \(NIB\)](assetId:///0f7a1f3a-385b-4d56-a55b-0d766840c58a)