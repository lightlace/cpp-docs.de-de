---
title: "CGopherConnection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGopherConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherConnection class"
  - "Verbinden mit Server"
  - "Verbinden mit Server, gopher servers"
  - "Gopher-Protokoll"
  - "gopher server"
  - "Internet connections, gopher"
  - "Internet server, gopher"
  - "protocols, gopher"
  - "Server, Verbinden mit"
  - "Dienste, gopher"
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CGopherConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet die Verbindung zu einem Gopher Internetserver.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und Member sind veraltet, da sie nicht an der Windows XP\-Plattform verwenden, aber sie werden weiterhin, um an früheren Plattformen zu arbeiten.  
  
## Syntax  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](../Topic/CGopherConnection::CGopherConnection.md)|Erstellt ein `CGopherConnection`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md)|Erstellt ein Objekt [CGopherLocator](../../mfc/reference/cgopherlocator-class.md), um Dateien auf einem Gopherserver zu suchen.|  
|[CGopherConnection::GetAttribute](../Topic/CGopherConnection::GetAttribute.md)|Ruft Attributinformationen zum Gopher\-Objekt ab.|  
|[CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md)|Öffnet eine Gopher\-Datei.|  
  
## Hinweise  
 Der Gopher\-Dienst ist einer von drei Internetdiensten, die durch Klassen MFC\-WinInet\-Unterstützung erkannt werden.  
  
 Die Klasse `CGopherConnection` enthält einen Konstruktor und drei zusätzliche Memberfunktionen, die den Gopher\-Dienst verwalten: [OpenFile](../Topic/CGopherConnection::OpenFile.md), [CreateLocator](../Topic/CGopherConnection::CreateLocator.md) und [GetAttribute](../Topic/CGopherConnection::GetAttribute.md).  
  
 Um sich mit einem Internetserver Gopher kommunizieren kann, müssen Sie eine Instanz von [CInternetSession](../../mfc/reference/cinternetsession-class.md) zuerst erstellen und dann [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md) auf, die das `CGopherConnection`\-Objekt erstellt und einen Zeiger darauf zurückgibt.  Sie erstellen ein Objekt `CGopherConnection` nie direkt.  
  
 Um zu erfahren mehr zum `CGopherConnection` mit den anderen MFC\-Internetklassen funktioniert, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  Weitere Informationen zur Verwendung der beiden anderen unterstützten Internetdienste, wird HTTP FTP und die Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpConnection Class](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator Class](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession Class](../../mfc/reference/cinternetsession-class.md)