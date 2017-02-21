---
title: "CFtpFileFind Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFtpFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFtpFileFind class"
  - "Dateisuche [C++]"
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CFtpFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unterstützt in den Internetdateisuchen von FTP\-Servern.  
  
## Syntax  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](../Topic/CFtpFileFind::CFtpFileFind.md)|Erstellt ein `CFtpFileFind`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md)|Wenn eine Datei auf einem FTP\-Server.|  
|[CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md)|Fügt eine Dateisuche aus einem früheren Aufruf [FindFile](../Topic/CFtpFileFind::FindFile.md) fort.|  
|[CFtpFileFind::GetFileURL](../Topic/CFtpFileFind::GetFileURL.md)|Ruft die URL, einschließlich Pfad, der gesuchten Datei ab.|  
  
## Hinweise  
 `CFtpFileFind` enthält Memberfunktionen ein, die eine Suche starten, eine Datei suchen und die URL oder andere beschreibende Informationen über die Datei zurückgeben.  
  
 Andere MFC\-Klassen, die für das Internet und lokale Datei gefunden werden entworfen wurden, enthalten [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md).  Zusammen mit `CFtpFileFind` stellen diese Klassen einen nahtlosen Mechanismus bereit, damit der Client bestimmte Dateien, unabhängig vom Serverprotokoll oder den Dateityp sucht \(entweder ein lokaler Computer oder einen Remoteserver\).  Beachten Sie, dass keine MFC\-Klasse für das Suchen von HTTP\-Servern gibt, da HTTP nicht die direkte Bearbeitung der Datei unterstützt, die für Suchen benötigt wird.  
  
 Weitere Informationen dazu, wie `CFtpFileFind` und die anderen WinInet\-Klassen, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md) verwendet.  
  
## Beispiel  
 Der folgende Code zeigt, wie alle Dateien im aktuellen Verzeichnis des FTP\-Servers auflistet.  
  
 [!CODE [NVC_MFCWinInet#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWinInet#8)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)