---
title: "Schritte zum L&#246;schen einer Datei in einer typischen FTP-Clientanwendung | Microsoft Docs"
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
  - "FTP (File Transfer Protocol), Clientanwendungen"
  - "Internetanwendungen, FTP-Clientanwendungen"
  - "Internetclientanwendungen, FTP-Löschung"
  - "WinInet-Klassen, FTP"
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Schritte zum L&#246;schen einer Datei in einer typischen FTP-Clientanwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle werden die Schritte angezeigt, die Sie in einer typischen FTP\-Clientanwendung ausgeführt haben, die eine Datei gelöscht wird.  
  
|Das Ziel|Aktionen, die Sie ausführen|Effekte|  
|--------------|---------------------------------|-------------|  
|Starten Sie eine FTP\-Sitzung.|Erstellen Sie ein [CInternetSession](../mfc/reference/cinternetsession-class.md)\-Objekt.|Initialisiert WinInet\-Klassen und schließt am Server an.|  
|Herstellen einer Verbindung mit einem FTP\-Server.|Verwenden Sie [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md).|[CFtpConnection](../mfc/reference/cftpconnection-class.md) Gibt ein Objekt zurück.|  
|Überprüfen Sie, um sicherzustellen, dass Sie im rechten Verzeichnis auf dem FTP\-Server sind.|Verwenden Sie [CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md) oder [CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md).|Gibt den Namen oder die URL des Verzeichnisses, das Sie gerade an auf dem Server hergestellt werden zurückgegeben, abhängig von der ausgewählten Memberfunktion.|  
|Ändern in einem neuen FTP\-Verzeichnis auf dem Server.|Verwenden Sie [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|Ändert das Verzeichnis, das Sie gerade an auf dem Server hergestellt werden.|  
|Suchen Sie die erste Datei im FTP\-Verzeichnis.|Verwenden Sie [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|Sucht die erste Datei.  Gibt FALSE zurück, wenn keine Dateien gefunden werden.|  
|Suchen Sie die folgende Datei im FTP\-Verzeichnis.|Verwenden Sie [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Sucht die folgende Datei.  Gibt FALSE zurück, wenn die Datei nicht gefunden wird.|  
|Löschen Sie die Datei, die von **FindFile** oder `FindNextFile` gefunden wird.|Verwenden Sie [CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md), mit dem Dateinamen, der von **FindFile** oder `FindNextFile` zurückgegeben wird.|Löscht die Datei auf dem Server zum Lesen oder Schreiben.|  
|Behandeln von Ausnahmen|Verwenden Sie die [CInternetException](../mfc/reference/cinternetexception-class.md)\-Klasse.|Behandelt alle gängigen Internet\-Ausnahmetypen.|  
|Beenden Sie die FTP\-Sitzung.|Löschen Sie sich das Objekt unter [CInternetSession](../mfc/reference/cinternetsession-class.md).|Bereinigt automatisch geöffnet Dateihandles und Verbindungen.|  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC\-WinInet\-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)