---
title: "Vereinfachtes Erstellen von Internetclientanwendungen mit MFC | Microsoft Docs"
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
  - "Internetanwendungen, MFC"
  - "Internetclientanwendungen, MFC"
  - "MFC, Internetanwendungen"
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Vereinfachtes Erstellen von Internetclientanwendungen mit MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Classes kapseln die Funktionen der Win32\-Internet\-Erweiterung \(WinInet\-Klassen\) auf eine Weise gelöst, das einen vertrauten Kontext für MFC\-Programmierer bereitstellt.  MFC stellt drei Internetdateiklassen \([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md) und [CGopherFile](../mfc/reference/cgopherfile-class.md)\), ist von der Klasse [CStdioFile](../mfc/reference/cstdiofile-class.md).  Nicht nur stellen diese Klassen den Programmierer das Abrufen und Bearbeiten des Internet\-Datenvertrauten, die `CStdioFile` für lokale Dateien verwendet haben, jedoch mit diesen Klassen können Sie lokale Dateien und Internetdateien in einer konsistenten, transparente Weise bearbeiten.  
  
 Die Klassen MFC\-WinInet\-Unterstützung stellen dieselben Funktionen wie `CStdioFile` für Daten bereit, die über das Internet übertragen wird.  Diese Klassen extrahieren die Internetprotokolle für HTTP, FTP und Gopher in eine Anwendungsprogrammierschnittstelle auf hoher Ebene und stellen einen schnellen und einfachen Pfad zum Erstellen von Zugriff Internet\-bewusst bereit.  Beispielsweise erfordert die Verbindung mit einem FTP\-Server noch einige Schritte auf einer niedrigen Ebene, jedoch als MFC\-Entwickler, müssen Sie nur einen Aufruf dieser Verbindung erstellen lassen `CInternetSession::GetFTPConnection`.  
  
 Außerdem stellen die MFC\-WinInet\-Unterstützung Klassen die folgenden Vorteile:  
  
-   Manuelles Anzeigen von gepufferten E\/A  
  
-   Typsichere Handles für die Daten  
  
-   Standardparameter für viele Funktionen  
  
-   Ausnahmebehandlung für häufige Internet\-Fehler  
  
-   Automatische Bereinigung der geöffneten Handles und von Verbindungen  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Vereinfachtes Erstellen von Internetclientanwendungen mit WinInet](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)