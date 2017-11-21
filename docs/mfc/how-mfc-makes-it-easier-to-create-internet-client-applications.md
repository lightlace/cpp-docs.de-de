---
title: Wie MFC zum Erstellen von Internetclientanwendungen erleichtert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 396d1327583be515f262231e4533c00df61ba0a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>Vereinfachtes Erstellen von Internetclientanwendungen mit MFC
Die Microsoft Foundation Classes kapseln die Win32-Internet (WinInet) Erweiterungsfunktionen in einer Weise, die einen vertrauten Kontext für MFC-Programmierer bereitstellt. MFC stellt drei Klassen für Internet-Datei ([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), und [CGopherFile](../mfc/reference/cgopherfile-class.md)) abgeleitet wurde. die [CStdioFile](../mfc/reference/cstdiofile-class.md) Klasse . Nicht nur diese Klassen machen abrufen und Bearbeiten von Daten für das Internet Programmierer, die verwendet wurden `CStdioFile` für lokale Dateien, jedoch mit diesen Klassen Sie können lokale Dateien und behandeln Internetdateien konsistent und transparent.  
  
 Die MFC-WinInet-Klassen bieten die gleiche Funktionalität wie `CStdioFile` für Daten, die über das Internet übertragen werden. Diese Klassen abstrahieren die Internetprotokolle für HTTP, FTP und Gopher in einer allgemeinen Anwendung Programmierschnittstelle, die einen Pfad schnellen und einfachen auf das Erstellen von Internet-fähigen Anwendungen bereitstellen. Z. B. Herstellen einer Verbindung mit einem FTP-Server weiterhin erfordert mehrere Schritte auf niedriger Ebene, jedoch als eine MFC-Entwickler müssen Sie nur einen Aufruf `CInternetSession::GetFTPConnection` diese Verbindung zu erstellen.  
  
 Darüber hinaus bieten die MFC-WinInet-Klassen, die folgenden Vorteile:  
  
-   Gepufferte e/a  
  
-   Als typsicherer für Ihre Daten verarbeitet  
  
-   Standardparameter für viele Funktionen  
  
-   Ausnahmebehandlung für common Internet-Fehler  
  
-   Automatische Bereinigung von geöffneten Handles und Verbindungen  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Vereinfachtes Erstellen von Internetclientanwendungen mit WinInet](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

