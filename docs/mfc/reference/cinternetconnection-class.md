---
title: "CInternetConnection Class"
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
  - "CInternetConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous connections"
  - "CInternetConnection class"
  - "Internet connections"
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CInternetConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet die Verbindung zu einem Internetserver.  
  
## Syntax  
  
```  
class CInternetConnection : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](../Topic/CInternetConnection::CInternetConnection.md)|Erstellt ein `CInternetConnection`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetConnection::GetContext](../Topic/CInternetConnection::GetContext.md)|Ruft die Kontext\-ID für dieses Verbindungsobjekt ab.|  
|[CInternetConnection::GetServerName](../Topic/CInternetConnection::GetServerName.md)|Ruft den Namen des Servers ab, der der Verbindung zugeordnet ist.|  
|[CInternetConnection::GetSession](../Topic/CInternetConnection::GetSession.md)|Ruft einen Zeiger auf das [CInternetSession](../../mfc/reference/cinternetsession-class.md)\-Objekt, das der Verbindung zugeordnet ist.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](../Topic/CInternetConnection::operator%20HINTERNET.md)|Ein Handle für eine Internet\-Sitzung.|  
  
## Hinweise  
 Dies ist die Basisklasse für MFC\-Klassen [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  Jede dieser Klassen stellt zusätzliche Funktionen für die Kommunikation mit dem jeweiligen FTP, dem HTTP oder dem Gopherserver bereit.  
  
 Um direkt einen Internetserver zu kommunizieren, müssen Sie ein [CInternetSession](../../mfc/reference/cinternetsession-class.md)\-Objekt und ein Objekt `CInternetConnection` haben.  
  
 Um zu erfahren mehr über wie die WinInet\-Klassen arbeiten, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)