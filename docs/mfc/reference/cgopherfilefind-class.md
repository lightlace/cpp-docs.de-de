---
title: "CGopherFileFind Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGopherFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFileFind class"
  - "Dateisuche [C++]"
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CGopherFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unterstützt in den Internetdateisuchen von Gopherservern.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und Member sind veraltet, da sie nicht an der Windows XP\-Plattform verwenden, aber sie werden weiterhin, um an früheren Plattformen zu arbeiten.  
  
## Syntax  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](../Topic/CGopherFileFind::CGopherFileFind.md)|Erstellt ein `CGopherFileFind`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md)|Wenn eine Datei auf einem Gopherserver.|  
|[CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md)|Fügt eine Dateisuche aus einem früheren Aufruf [FindFile](../Topic/CGopherFileFind::FindFile.md) fort.|  
|[CGopherFileFind::GetCreationTime](../Topic/CGopherFileFind::GetCreationTime.md)|Ruft die Zeit ab, die die angegebene Datei erstellt wurde.|  
|[CGopherFileFind::GetLastAccessTime](../Topic/CGopherFileFind::GetLastAccessTime.md)|Ruft die Zeit ab, die auf die angegebene Datei zuletzt verwendet wurden.|  
|[CGopherFileFind::GetLastWriteTime](../Topic/CGopherFileFind::GetLastWriteTime.md)|Ruft die Zeit ab, die die angegebene Datei zuletzt geschrieben wurde.|  
|[CGopherFileFind::GetLength](../Topic/CGopherFileFind::GetLength.md)|Ruft die Länge der gesuchten Datei, in Bytes ab.|  
|[CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md)|Rufen Sie ein `CGopherLocator`\-Objekt ab.|  
|[CGopherFileFind::GetScreenName](../Topic/CGopherFileFind::GetScreenName.md)|Ruft den Namen eines Gopher\-Bildschirms ab.|  
|[CGopherFileFind::IsDots](../Topic/CGopherFileFind::IsDots.md)|Tests für die Markierung des aktuellen Verzeichnisses und des übergeordneten Verzeichnisses beim Durchlaufen von Dateien.|  
  
## Hinweise  
 `CGopherFileFind` enthält Memberfunktionen ein, die eine Suche starten, eine Datei suchen und die URL einer Datei zurückgeben.  
  
 Andere MFC\-Klassen, die für das Internet und lokale Datei gefunden werden entworfen wurden, enthalten [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md).  Zusammen mit `CGopherFileFind` stellen diese Klassen einen nahtlosen Mechanismus bereit, sodass der Benutzer bestimmte Dateien, unabhängig vom Serverprotokoll, den Dateityp oder den Speicherort sucht \(entweder ein lokaler Computer oder einen Remoteserver\). Beachten Sie, dass keine MFC\-Klasse für das Suchen von HTTP\-Servern gibt, da HTTP nicht die direkte Bearbeitung der Datei unterstützt, die von Suchen benötigt wird.  
  
> [!NOTE]
>  `CGopherFileFind` unterstützt nicht die folgenden Memberfunktionen ihrer Basisklasse [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
-   [GetRoot](../Topic/CFileFind::GetRoot.md)  
  
-   [GetFileName](../Topic/CFileFind::GetFileName.md)  
  
-   [GetFilePath](../Topic/CFileFind::GetFilePath.md)  
  
-   [GetFileTitle](../Topic/CFileFind::GetFileTitle.md)  
  
-   [GetFileURL](../Topic/CFileFind::GetFileURL.md)  
  
 Wenn sie mit `CGopherFileFind` verwendet wird, ist die `CFileFind`\-Memberfunktion [IsDots](../Topic/CFileFind::IsDots.md) immer **FALSE**.  
  
 Weitere Informationen dazu, wie `CGopherFileFind` und die anderen WinInet\-Klassen, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md) verwendet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)