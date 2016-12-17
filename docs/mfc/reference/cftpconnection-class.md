---
title: "CFtpConnection Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CFtpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFtpConnection class"
  - "FTP (File Transfer Protocol), Herstellen von Verbindungen"
  - "Internet connections, FTP"
  - "Internet services, FTP"
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
caps.latest.revision: 23
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CFtpConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet die FTP\-Verbindung zu einem Internetserver und ermöglicht direkte Bearbeitung von Verzeichnissen und Dateien auf dem Server.  
  
## Syntax  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFtpConnection::CFtpConnection](../Topic/CFtpConnection::CFtpConnection.md)|Erstellt ein `CFtpConnection`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFtpConnection::Command](../Topic/CFtpConnection::Command.md)|Sendet einen Befehl direkt auf einem FTP\-Server.|  
|[CFtpConnection::CreateDirectory](../Topic/CFtpConnection::CreateDirectory.md)|Erstellt ein Verzeichnis auf dem Server.|  
|[CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md)|Ruft das aktuelle Verzeichnis für diese Verbindung ab.|  
|[CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md)|Ruft das aktuelle Verzeichnis für diese Verbindung als URL ab.|  
|[CFtpConnection::GetFile](../Topic/CFtpConnection::GetFile.md)|Ruft eine Datei auf dem verbundenen Server ab|  
|[CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md)|Öffnet eine Datei auf dem verbundenen Server.|  
|[CFtpConnection::PutFile](../Topic/CFtpConnection::PutFile.md)|Setzt eine Datei auf dem Server.|  
|[CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md)|Entfernt eine Datei vom Server.|  
|[CFtpConnection::RemoveDirectory](../Topic/CFtpConnection::RemoveDirectory.md)|Entfernt das angegebene Verzeichnis vom Server.|  
|[CFtpConnection::Rename](../Topic/CFtpConnection::Rename.md)|Benennt eine Datei auf dem Server.|  
|[CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md)|Legt das Verzeichnis des aktuellen FTP fest.|  
  
## Hinweise  
 FTP ist einer der drei Internetdienste, die durch Klassen MFC\-WinInet\-Unterstützung erkannt werden.  
  
 Um sich mit einem FTP\-Internet\-Server kommunizieren kann, müssen Sie eine Instanz von [CInternetSession](../../mfc/reference/cinternetsession-class.md) zuerst erstellen und erstellen dann ein `CFtpConnection`\-Objekt.  Sie erstellen ein Objekt `CFtpConnection` nie direkt; und [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md) Aufruf, der das `CFtpConnection`\-Objekt erstellt und einen Zeiger darauf zurückgibt.  
  
 Um zu erfahren mehr zum `CFtpConnection` mit den anderen MFC\-Internetklassen funktioniert, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  Weitere Informationen zum Kommunizieren mit den anderen beiden unterstützten Dienste, finden HTTP und Gopher, Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## Beispiel  
 Im Beispiel in der [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)\-Klassenübersicht.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession Class](../../mfc/reference/cinternetsession-class.md)