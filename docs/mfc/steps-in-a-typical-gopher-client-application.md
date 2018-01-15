---
title: Die Schritte in einer Typischen Gopher-Clientanwendung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5108e997336e53434ad33030c0e79be027aa4a98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-gopher-client-application"></a>Schritte in einer typischen Gopher-Clientanwendung
Die folgende Tabelle zeigt die Schritte, dass Sie möglicherweise in einer typischen Gopher-Clientanwendung ausführen.  
  
|Ihr Ziel|Die Aktion|Effekte|  
|---------------|----------------------|-------------|  
|Gophersitzung zu starten.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|  
|Verbindung zu einem Gopherserver.|Verwendung [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection).|Gibt eine [CGopherConnection](../mfc/reference/cgopherconnection-class.md) Objekt.|  
|Suchen Sie die erste Ressource im Gopher.|Verwendung [CGopherFileFind:: FindFile](../mfc/reference/cgopherfilefind-class.md#findfile).|Sucht die erste Datei an. Gibt "false" zurück, wenn keine Dateien gefunden werden.|  
|Suchen Sie die nächste Ressource im Gopher.|Verwendung [CGopherFileFind:: FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile).|Sucht die nächste Datei. Gibt "false" zurück, wenn die Datei nicht gefunden wird.|  
|Öffnen Sie die Datei, die vom gefundenen **FindFile** oder `FindNextFile` zum Lesen.|Abrufen ein mithilfe von Gopher-Locators [CGopherFileFind:: GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Verwendung [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Öffnet die Datei, die gemäß des Locators. `OpenFile`Gibt eine [CGopherFile](../mfc/reference/cgopherfile-class.md) Objekt.|  
|Öffnen Sie eine Datei mit einem Gopher-Locator, den Sie angeben.|Erstellen Sie einen Gopher-Locator mit [CGopherConnection:: CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator). Verwendung [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Öffnet die Datei, die gemäß des Locators. `OpenFile`Gibt eine [CGopherFile](../mfc/reference/cgopherfile-class.md) Objekt.|  
|Aus der Datei gelesen.|Verwendung [CGopherFile](../mfc/reference/cgopherfile-class.md).|Liest die angegebene Anzahl von Bytes, die unter Verwendung eines Puffers an, das Sie angeben.|  
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Verarbeitet alle common Internet Ausnahmetypen an.|  
|Gophersitzung zu beenden.|Löschen Sie die [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt Handles von offenen Dateien und Verbindungen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
