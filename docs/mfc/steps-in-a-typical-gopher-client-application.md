---
title: "Schritte in einer typischen Gopher-Clientanwendung | Microsoft Docs"
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
  - "Gopher-Clientanwendungen"
  - "Internetanwendungen, gopher-Clientanwendungen"
  - "Internetclientanwendungen, Gophertabelle"
  - "WinInet-Klassen, Gopher"
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Schritte in einer typischen Gopher-Clientanwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle werden die Schritte angezeigt, die Sie in einer typischen Gopher\-Clientanwendung ausgeführt haben.  
  
|Das Ziel|Aktionen, die Sie ausführen|Effekte|  
|--------------|---------------------------------|-------------|  
|Starten Sie eine Gopher\-Sitzung.|Erstellen Sie ein [CInternetSession](../mfc/reference/cinternetsession-class.md)\-Objekt.|Initialisiert WinInet\-Klassen und schließt am Server an.|  
|Schließen Sie mit einem Gopherserver an.|Verwenden Sie [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md).|[CGopherConnection](../mfc/reference/cgopherconnection-class.md) Gibt ein Objekt zurück.|  
|Suchen Sie die erste Ressource im Gopher.|Verwenden Sie [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md).|Sucht die erste Datei.  Gibt FALSE zurück, wenn keine Dateien gefunden werden.|  
|Suchen Sie die folgende Ressource im Gopher.|Verwenden Sie [CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md).|Sucht die folgende Datei.  Gibt FALSE zurück, wenn die Datei nicht gefunden wird.|  
|Öffnen Sie die Datei, die von **FindFile** oder `FindNextFile` zum Lesen gefunden wird.|Rufen Sie einen Gopher\-Locator mithilfe von [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md) ab.  Verwenden Sie [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|Öffnet die Datei, die vom Locator angegeben wird.  `OpenFile` gibt ein Objekt zurück. [CGopherFile](../mfc/reference/cgopherfile-class.md)|  
|Öffnen Sie eine Datei mithilfe eines Gopher\-Locators, den Sie angeben.|Erstellen Sie einen Gopher\-Locator mit [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md) erstellt.  Verwenden Sie [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|Öffnet die Datei, die vom Locator angegeben wird.  `OpenFile` gibt ein Objekt zurück. [CGopherFile](../mfc/reference/cgopherfile-class.md)|  
|Lesen aus der Datei.|Verwenden Sie [CGopherFile](../mfc/reference/cgopherfile-class.md).|Liest die angegebene Anzahl von Bytes, mithilfe eines Puffers, den Sie angeben.|  
|Behandeln von Ausnahmen|Verwenden Sie die [CInternetException](../mfc/reference/cinternetexception-class.md)\-Klasse.|Behandelt alle gängigen Internet\-Ausnahmetypen.|  
|Beenden Sie die Gopher\-Sitzung.|Löschen Sie sich das Objekt unter [CInternetSession](../mfc/reference/cinternetsession-class.md).|Bereinigt automatisch geöffnet Dateihandles und Verbindungen.|  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC\-WinInet\-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)