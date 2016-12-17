---
title: "Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen"
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
  - "Internetanwendungen, Clientanwendungen"
  - "Internetanwendungen, WinInet"
  - "Internetclientanwendungen"
  - "Internetclientanwendungen, Schreiben"
  - "MFC, Internetanwendungen"
  - "WinInet-Klassen, Programmieren"
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Basis jeder Internet\-Clientanwendung ist die Internet\-Sitzung.  MFC implementiert Internet\-Sitzungen als Objekte der Klasse [CInternetSession](../mfc/reference/cinternetsession-class.md).  Mit dieser Klasse können Sie eine Internet\-Sitzung gleichzeitige oder mehrere Sitzungen erstellen.  
  
 Um sich mit einem Server kommunizieren, benötigen Sie ein Objekt unter [CInternetConnection](../mfc/reference/cinternetconnection-class.md) sowie auf `CInternetSession`.  Sie können `CInternetConnection` erstellen, indem Sie [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md) oder [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md) verwenden.  Jeder dieser Aufrufe ist z Protokolltyp bestimmt.  Diese Aufrufe öffnen keine Datei auf dem Server zum Lesen oder Schreiben.  Wenn Sie beabsichtigen, Daten zu lesen oder zu schreiben, müssen Sie die Datei öffnen als separater Schritt.  
  
 Für die meisten Internet\-Sitzungen die `CInternetSession`\-Objektarbeiten Blatt in Blatt mit einem [CInternetFile](../mfc/reference/cinternetfile-class.md)\-Objekt:  
  
-   Eine Internet\-Sitzung müssen Sie eine Instanz von [CInternetSession](../mfc/reference/cinternetsession-class.md) erstellen.  
  
-   Wenn die Internet\-Sitzung Daten liest oder schreibt, müssen Sie eine Instanz von `CInternetFile` \(oder ihre Unterklassen, [CHttpFile](../mfc/reference/chttpfile-class.md) oder [CGopherFile](../mfc/reference/cgopherfile-class.md)\) erstellen.  Die einfachste Methode, Daten zu lesen ist, [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md) aufzurufen.  Diese Funktion analysiert einen Universalitäts\-Ressourcen\-Locator \(URL\), die von Ihnen angegeben wird, wird eine Verbindung zum Server an, der durch die URL angegeben wird und einem schreibgeschützten `CInternetFile`\-Objekt zurück.  `CInternetSession::OpenURL` ist nicht zu einem Protokolltyp \- die gleichen Aufrufsarbeiten für entweder HTTP oder FTP, Gopher URL bestimmt.  Arbeiten `CInternetSession::OpenURL` sogar mit lokalen Dateien \(statt `CStdioFile``CInternetFile` zurückgeben\).  
  
-   Wenn die nicht Internet\-Sitzung liest oder schreibt, müssen ggf. Daten, aber andere Aufgaben ausführen, z Löschen einer Datei in einem FTP\-Verzeichnis, Sie keine Instanz von `CInternetFile` erstellen.  
  
 Es gibt zwei Möglichkeiten, ein `CInternetFile`\-Objekt zu erstellen:  
  
-   Wenn Sie `CInternetSession::OpenURL` verwenden, um die Serververbindung festzulegen, gibt der Aufruf von `OpenURL``CStdioFile` zurück.  
  
-   Wenn von **CInternetSession::GetFtpConnection**, `GetGopherConnection` oder `GetHttpConnection`, die Serververbindung, erstellen Sie `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile` oder **CHttpConnection::OpenRequest,** bzw. aufrufen muss, `CInternetFile`, `CGopherFile` oder `CHttpFile` zurückgeben, bzw.  
  
 Die Schritte, wenn eine Internet\-Clientanwendung implementieren, hängen davon ab, ob Sie einen generischen Internet\-Client auf Grundlage protokollspezifischen **OpenURL**  oder einen Client, der eine der **GetConnection**\-Funktionen verwendet erstellen.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Wie schreibe ich eine Internet\-Clientanwendung, die generisch mit HTTP, FTP und Gopher funktioniert?](../mfc/steps-in-a-typical-internet-client-application.md)  
  
-   [Wie schreibe ich eine FTP\-Clientanwendung, die eine Datei öffnet?](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [Wie schreibe ich eine FTP\-Clientanwendung, nicht geöffnet, die eine Datei vorhanden, aber wird einen Verzeichnisoperation, wie das Löschen einer Datei aus?](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [Wie schreibe ich eine Gopher\-Clientanwendung?](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [Wie schreibe ich eine HTTP\-Clientanwendung?](../mfc/steps-in-a-typical-http-client-application.md)  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [MFC\-Klassen für das Erstellen von Internetclientanwendungen](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)