---
title: "CInternetFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetFile class"
  - "Internet files"
  - "Internet files, CInternetFile class"
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CInternetFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht Zugriff auf Dateien auf Remotesystemen, die Internetprotokolle verwenden.  
  
## Syntax  
  
```  
  
class CInternetFile : public CStdioFile  
  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](../Topic/CInternetFile::CInternetFile.md)|Erstellt ein `CInternetFile`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetFile::Abort](../Topic/CInternetFile::Abort.md)|Schließt die Datei und ignoriert alle Warnungen und Fehler.|  
|[CInternetFile::Close](../Topic/CInternetFile::Close.md)|Schließt `CInternetFile` und gibt seine Ressourcen frei.|  
|[CInternetFile::Flush](../Topic/CInternetFile::Flush.md)|Leert den Inhalt des Pufferspeichers und stellt sicher, dass die Daten im Arbeitsspeicher zur Zielcomputers geschrieben werden.|  
|[CInternetFile::GetLength](../Topic/CInternetFile::GetLength.md)|Gibt die Größe der Datei zurück.|  
|[CInternetFile::Read](../Topic/CInternetFile::Read.md)|Liest die Anzahl der angegebenen Bytes.|  
|[CInternetFile::ReadString](../Topic/CInternetFile::ReadString.md)|Liest einen Stream von Zeichen.|  
|[CInternetFile::Seek](../Topic/CInternetFile::Seek.md)|Ordnet den Zeiger in einer geöffneten Datei neu.|  
|[CInternetFile::SetReadBufferSize](../Topic/CInternetFile::SetReadBufferSize.md)|Legt die Größe des Puffers fest, in dem Daten gelesen werden.|  
|[CInternetFile::SetWriteBufferSize](../Topic/CInternetFile::SetWriteBufferSize.md)|Legt die Größe des Puffers fest, in dem Daten geschrieben werden.|  
|[CInternetFile::Write](../Topic/CInternetFile::Write.md)|Schreibt die Anzahl der angegebenen Bytes.|  
|[CInternetFile::WriteString](../Topic/CInternetFile::WriteString.md)|Schreibt eine auf NULL endende Zeichenfolge in einer Datei.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](../Topic/CInternetFile::operator%20HINTERNET.md)|Ein Umwandlungsoperator für ein Internet\-Handle.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetFile::m\_hFile](../Topic/CInternetFile::m_hFile.md)|Ein Handle für eine Datei.|  
  
## Hinweise  
 Stellt eine Basisklasse für [CHttpFile](../../mfc/reference/chttpfile-class.md) bereit und [CGopherFile](../../mfc/reference/cgopherfile-class.md) Datei klassifiziert.  Sie erstellen ein Objekt `CInternetFile` nie direkt.  Stattdessen erstellen Sie ein Objekt von einer davon abgeleiteten Klasse, indem Sie [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md) oder [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md) aufrufen.  Sie können ein `CInternetFile`\-Objekt auch erstellen, indem Sie [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md) aufrufen.  
  
 Die `CInternetFile`\-Memberfunktionen **Öffnen**, `LockRange`, `UnlockRange` und `Duplicate` werden nicht für `CInternetFile` implementiert.  Wenn Sie aufrufen, gelten diese Funktionen auf `CInternetFile`, erhalten Sie [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md) ein.  
  
 Um zu erfahren mehr zum `CInternetFile` mit den anderen MFC\-Internetklassen funktioniert, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CStdioFile Class](../../mfc/reference/cstdiofile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)