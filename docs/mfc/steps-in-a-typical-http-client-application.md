---
title: "Schritte in einer typischen HTTP-Clientanwendung"
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
  - "Anwendungen [MFC], HTTP-Client"
  - "Clientanwendungen [C++], HTTP"
  - "HTTP-Clientanwendungen"
  - "Internetanwendungen [C++], HTTP-Clientanwendungen"
  - "Internetclientanwendungen [C++], HTTP-Tabelle"
  - "WinInet-Klassen, HTTP"
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Schritte in einer typischen HTTP-Clientanwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle werden die Schritte angezeigt, die Sie in einer typischen HTTP\-Clientanwendung ausgeführt haben:  
  
|Das Ziel|Aktionen, die Sie ausführen|Effekte|  
|--------------|---------------------------------|-------------|  
|Starten Sie eine HTTP\-Sitzung.|Erstellen Sie ein [CInternetSession](../mfc/reference/cinternetsession-class.md)\-Objekt.|Initialisiert WinInet\-Klassen und schließt am Server an.|  
|Schließen Sie mit einem HTTP\-Server an.|Verwenden Sie [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md).|[CHttpConnection](../mfc/reference/chttpconnection-class.md) Gibt ein Objekt zurück.|  
|Öffnen Sie eine HTTP\-Anforderung.|Verwenden Sie [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md).|[CHttpFile](../mfc/reference/chttpfile-class.md) Gibt ein Objekt zurück.|  
|Sendet eine HTTP\-Anforderung.|Verwenden Sie [CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md) und [CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md).|Sucht die Datei.  Gibt FALSE zurück, wenn die Datei nicht gefunden wird.|  
|Lesen aus der Datei.|Verwenden Sie [CHttpFile](../mfc/reference/chttpfile-class.md).|Liest die angegebene Anzahl von Bytes mithilfe eines Puffers, den Sie angeben.|  
|Behandeln von Ausnahmen|Verwenden Sie die [CInternetException](../mfc/reference/cinternetexception-class.md)\-Klasse.|Behandelt alle gängigen Internet\-Ausnahmetypen.|  
|Beenden Sie die HTTP\-Sitzung.|Löschen Sie sich das Objekt unter [CInternetSession](../mfc/reference/cinternetsession-class.md).|Bereinigt automatisch geöffnet Dateihandles und Verbindungen.|  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC\-WinInet\-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)