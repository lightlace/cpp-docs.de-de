---
title: Die Schritte in einer Typischen Internetclientanwendung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1c7a7053b8378ea62dc0291dba1b79b794dd099
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381273"
---
# <a name="steps-in-a-typical-internet-client-application"></a>Schritte in einer typischen Internetclientanwendung
Die folgende Tabelle zeigt die Schritte, dass Sie in einer typischen Internetclientanwendung ausführen können.  
  
|Ihr Ziel|Die Aktion|Effekte|  
|---------------|----------------------|-------------|  
|Eine Internet-Sitzung zu starten.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|  
|Legen Sie eine Internet-Abfrageoption (Timeouts oder Anzahl der Wiederholungsversuche, z. B.).|Verwendung [CInternetSession:: SetOption](../mfc/reference/cinternetsession-class.md#setoption).|Gibt "false" zurück, wenn der Vorgang nicht erfolgreich war.|  
|Richten Sie eine Rückruffunktion zum Überwachen des Status der Sitzung.|Verwendung [CInternetSession:: EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback).|Richtet einen Rückruf zur [CInternetSession:: OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback). Überschreiben Sie `OnStatusCallback` eigene Rückrufroutine zu erstellen.|  
|Verbinden Sie mit einer Internet-Server, Intranetserver oder lokalen Datei.|Verwendung [OpenURL](../mfc/reference/cinternetsession-class.md#openurl).|Analysiert die URL, und öffnet eine Verbindung mit dem angegebenen Server. Gibt eine [CStdioFile](../mfc/reference/cstdiofile-class.md) (Wenn Sie übergeben `OpenURL` der Name einer lokalen Datei). Dies ist das Objekt, das über dem Sie aus dem Server oder die Datei abgerufene Daten zugreifen.|  
|Aus der Datei gelesen.|Verwendung [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|Liest die angegebene Anzahl von Bytes, die unter Verwendung eines Puffers an, das Sie angeben.|  
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Verarbeitet alle common Internet Ausnahmetypen an.|  
|Die Internet-Sitzung wird beendet.|Löschen Sie die [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt Handles von offenen Dateien und Verbindungen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
