---
title: Die Schritte in einer Typischen HTTP-Clientanwendung | Microsoft Docs
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
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 936914a816f109736d38259908608b42b7bdcb00
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-http-client-application"></a>Schritte in einer typischen HTTP-Clientanwendung
Die folgende Tabelle zeigt die Schritte, dass Sie möglicherweise in einer typischen HTTP-Clientanwendung ausführen:  
  
|Ihr Ziel|Die Aktion|Effekte|  
|---------------|----------------------|-------------|  
|Eine HTTP-Sitzung zu starten.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|  
|Verbinden Sie mit einem HTTP-Server.|Verwendung [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection).|Gibt eine [CHttpConnection](../mfc/reference/chttpconnection-class.md) Objekt.|  
|Öffnen Sie eine HTTP-Anforderung.|Verwendung [CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest).|Gibt eine [CHttpFile](../mfc/reference/chttpfile-class.md) Objekt.|  
|Senden einer HTTP-Anforderung.|Verwendung [CHttpFile:: AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) und [CHttpFile:: SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|Sucht nach der Datei. Gibt "false" zurück, wenn die Datei nicht gefunden wird.|  
|Aus der Datei gelesen.|Verwendung [CHttpFile](../mfc/reference/chttpfile-class.md).|Liest die angegebene Anzahl von Bytes, die unter Verwendung eines Puffers an, das Sie angeben.|  
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Verarbeitet alle common Internet Ausnahmetypen an.|  
|Die HTTP-Sitzung zu beenden.|Löschen Sie die [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt Handles von offenen Dateien und Verbindungen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
