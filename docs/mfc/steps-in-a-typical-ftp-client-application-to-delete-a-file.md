---
title: "Die Schritte in einer Typischen FTP-Clientanwendung zum Löschen einer Datei | Microsoft Docs"
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
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77fecfb9c11c95d14c8816fe1c3b23046eae98c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>Schritte zum Löschen einer Datei in einer typischen FTP-Clientanwendung
Die folgende Tabelle zeigt die Schritte, die Sie in einer typischen FTP-Clientanwendung adäquat widerspiegelt, die eine Datei gelöscht wird.  
  
|Ihr Ziel|Die Aktion|Effekte|  
|---------------|----------------------|-------------|  
|Eine FTP-Sitzung zu starten.|Erstellen einer [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|WinInet initialisiert, und eine Verbindung mit dem Server her.|  
|Verbinden Sie mit einem FTP-Server.|Verwendung [CInternetSession:: GetFTPConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Gibt eine [CFtpConnection](../mfc/reference/cftpconnection-class.md) Objekt.|  
|Überprüfen Sie außerdem sicherstellen, dass Sie sich in das richtige Verzeichnis auf dem FTP-Server befinden.|Verwendung [CFtpConnection:: GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) oder [CFtpConnection::GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl).|Gibt den Namen oder die URL des Verzeichnisses, das Sie gerade auf dem Server, abhängig von der ausgewählten Memberfunktion verbunden sind.|  
|Ändern Sie in einer neuen FTP-Verzeichnis auf dem Server.|Verwendung [CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Ändert das Verzeichnis, das Sie gerade auf dem Server verbunden sind.|  
|Suchen Sie die erste Datei in das FTP-Verzeichnis.|Verwendung [CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|Sucht die erste Datei an. Gibt "false" zurück, wenn keine Dateien gefunden werden.|  
|Suchen Sie die nächste Datei im FTP-Verzeichnis.|Verwendung [CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Sucht die nächste Datei. Gibt "false" zurück, wenn die Datei nicht gefunden wird.|  
|Löschen Sie die Datei, die vom gefundenen **FindFile** oder `FindNextFile`.|Verwendung [CFtpConnection:: Remove](../mfc/reference/cftpconnection-class.md#remove), mit dem Dateinamen zurückgegebenes **FindFile** oder `FindNextFile`.|Löscht die Datei auf dem Server zum Lesen oder schreiben.|  
|Behandeln von Ausnahmen|Verwenden der [CInternetException](../mfc/reference/cinternetexception-class.md) Klasse.|Verarbeitet alle common Internet Ausnahmetypen an.|  
|Die FTP-Sitzung zu beenden.|Löschen Sie die [CInternetSession](../mfc/reference/cinternetsession-class.md) Objekt.|Automatisch bereinigt Handles von offenen Dateien und Verbindungen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC-WinInet-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
