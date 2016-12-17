---
title: "Schritte in einer typischen FTP-Clientanwendung"
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
  - "FTP (File Transfer Protocol)"
  - "FTP (File Transfer Protocol), Clientanwendungen"
  - "Internetanwendungen, FTP-Clientanwendungen"
  - "Internetclientanwendungen, FTP-Tabelle"
  - "WinInet-Klassen, FTP"
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Schritte in einer typischen FTP-Clientanwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine typische FTP\-Clientanwendung erstellt [CInternetSession](../mfc/reference/cinternetsession-class.md) und ein [CFtpConnection](../mfc/reference/cftpconnection-class.md)\-Objekt.  Beachten Sie, dass diese Klassen MFC\-WinInet\-Unterstützung nicht tatsächlich die Proxytypeinstellungen steuern; IIS ausgeführt.  
  
 Außerdem finden Sie diese Knowledge Base\-Artikel:  
  
-   HOWTO: FTP mit CERN\-basiertem Proxy mit WinInet\-API \(Artikel ID: Q166961\)  
  
-   SAMPLING: FTP mit CERN\-basiertes Kennwort geschütztem Proxy \(Artikel ID: Q216214\)  
  
-   Internetdienste\-Manager kann installiert Proxy\-Dienstleistungen anzeigen \(nicht Artikel ID: Q216802\)  
  
 In der folgenden Tabelle werden die Schritte angezeigt, die Sie in einer typischen FTP\-Clientanwendung ausgeführt haben.  
  
|Das Ziel|Aktionen, die Sie ausführen|Effekte|  
|--------------|---------------------------------|-------------|  
|Starten Sie eine FTP\-Sitzung.|Erstellen Sie ein [CInternetSession](../mfc/reference/cinternetsession-class.md)\-Objekt.|Initialisiert WinInet\-Klassen und schließt am Server an.|  
|Herstellen einer Verbindung mit einem FTP\-Server.|Verwenden Sie [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md).|[CFtpConnection](../mfc/reference/cftpconnection-class.md) Gibt ein Objekt zurück.|  
|Ändern in einem neuen FTP\-Verzeichnis auf dem Server.|Verwenden Sie [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|Ändert das Verzeichnis, das Sie gerade an auf dem Server hergestellt werden.|  
|Suchen Sie die erste Datei im FTP\-Verzeichnis.|Verwenden Sie [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|Sucht die erste Datei.  Gibt FALSE zurück, wenn keine Dateien gefunden werden.|  
|Suchen Sie die folgende Datei im FTP\-Verzeichnis.|Verwenden Sie [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Sucht die folgende Datei.  Gibt FALSE zurück, wenn die Datei nicht gefunden wird.|  
|Öffnen Sie die Datei, die von **FindFile** oder `FindNextFile` zum Lesen oder Schreiben gefunden wird.|Verwenden Sie [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md), mit dem Dateinamen, der durch [FindFile](../Topic/CFtpFileFind::FindFile.md) oder [FindNextFile](../Topic/CFtpFileFind::FindNextFile.md) zurückgegeben wird.|Öffnet die Datei auf dem Server zum Lesen oder Schreiben.  [CInternetFile](../mfc/reference/cinternetfile-class.md) Gibt ein Objekt zurück.|  
|Lesen oder Schreiben Sie zur Datei.|Verwenden Sie [CInternetFile::Read](../Topic/CInternetFile::Read.md) oder [CInternetFile::Write](../Topic/CInternetFile::Write.md).|Liest oder schreibt die angegebene Anzahl von Bytes, mithilfe eines Puffers, den Sie angeben.|  
|Behandeln von Ausnahmen|Verwenden Sie die [CInternetException](../mfc/reference/cinternetexception-class.md)\-Klasse.|Behandelt alle gängigen Internet\-Ausnahmetypen.|  
|Beenden Sie die FTP\-Sitzung.|Löschen Sie sich das Objekt unter [CInternetSession](../mfc/reference/cinternetsession-class.md).|Bereinigt automatisch geöffnet Dateihandles und Verbindungen.|  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC\-WinInet\-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)