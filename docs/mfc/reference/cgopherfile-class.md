---
title: "CGopherFile Class"
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
  - "CGopherFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFile-Klasse"
  - "gopher protocol files"
  - "Internet, gopher"
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität bereit, um Dateien auf einem Gopherserver zu suchen und zu lesen.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und Member sind veraltet, da sie nicht an der Windows XP\-Plattform verwenden, aber sie werden weiterhin, um an früheren Plattformen zu arbeiten.  
  
## Syntax  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](../Topic/CGopherFile::CGopherFile.md)|Erstellt ein `CGopherFile`\-Objekt.|  
  
## Hinweise  
 Der Gopher\-Dienst nicht ermöglicht Benutzern, Daten in eine Gopher\-Datei da Funktionen dieses Diensts hauptsächlich als menügesteuerte Schnittstelle zum Suchen von Informationen zu schreiben.  Die `CGopherFile`\-Memberfunktionen **Write**, `WriteString` und `Flush` werden nicht für `CGopherFile` implementiert.  Diese Funktionen auf `CGopherFile` dazu, wenden Sie, gibt [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md) ein.  
  
 Um zu erfahren mehr zum `CGopherFile` mit den anderen MFC\-Internetklassen funktioniert, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator Class](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection Class](../../mfc/reference/cgopherconnection-class.md)