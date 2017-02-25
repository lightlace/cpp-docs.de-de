---
title: "CHttpConnection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHttpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHttpConnection class"
  - "Verbinden mit Server"
  - "Verbinden mit Server, HTTP-Server"
  - "Verbindungen [C++], HTTP"
  - "HTTP-Verbindungen"
  - "HTTP-Server, Verbinden mit"
  - "Internet connections, HTTP"
  - "Internet protocols"
  - "Internet protocols, HTTP"
  - "Internet server, HTTP"
  - "protocols, HTTP"
  - "Server, Verbinden mit"
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHttpConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet die Verbindung zu einem HTTP\-Server.  
  
## Syntax  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHttpConnection::CHttpConnection](../Topic/CHttpConnection::CHttpConnection.md)|Erstellt ein `CHttpConnection`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md)|Öffnet eine HTTP\-Anforderung.|  
  
## Hinweise  
 HTTP ist eines der drei Internet\-Serverprotokollen, die durch Klassen MFC\-WinInet\-Unterstützung implementiert werden.  
  
 Die Klasse `CHttpConnection` enthält einen Konstruktor und eine einköpfige Funktion, [OpenRequest](../Topic/CHttpConnection::OpenRequest.md), die Verbindungen zu einem Server mit einem HTTP\-Protokoll verwaltet.  
  
 Um sich mit einem HTTP\-Server kommunizieren kann, müssen Sie eine Instanz von [CInternetSession](../../mfc/reference/cinternetsession-class.md) zuerst erstellen und erstellen dann ein [CHttpConnection](#_mfc_chttpconnection)\-Objekt.  Sie erstellen ein Objekt `CHttpConnection` nie direkt; und [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md) Aufruf, der das `CHttpConnection`\-Objekt erstellt und einen Zeiger darauf zurückgibt.  
  
 Um zu erfahren mehr zum `CHttpConnection` mit den anderen MFC\-Internetklassen funktioniert, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  Weitere Informationen zum Herstellen einer Verbindung mit Server mithilfe der beiden anderen unterstützten Internetprotokolle, sieht Gopher und FTP, Klassen [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) und [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)