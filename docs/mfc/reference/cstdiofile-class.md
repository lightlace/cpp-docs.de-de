---
title: "CStdioFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStdioFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStdioFile class"
  - "I/O [MFC], stream"
  - "stream I/O"
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CStdioFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Wechselstromablaufstreamdatei dar, wie durch die Laufzeitfunktion [fopen](../../c-runtime-library/reference/fopen-wfopen.md) geöffnet.  
  
## Syntax  
  
```  
class CStdioFile : public CFile  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CStdioFile::CStdioFile](../Topic/CStdioFile::CStdioFile.md)|Erstellt ein Objekt `CStdioFile` aus einem Pfad oder einem Dateizeiger.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStdioFile::Open](../Topic/CStdioFile::Open.md)|Überladen.  Open ist für die Verwendung mit dem Standard `CStdioFile`\-Konstruktor \(Überschreibungen [CFile::Open](../Topic/CFile::Open.md)\) entwickelt.|  
|[CStdioFile::ReadString](../Topic/CStdioFile::ReadString.md)|Liest eine einzelne Textzeile.|  
|[CStdioFile::Seek](../Topic/CStdioFile::Seek.md)|Positioniert den Zeiger der aktuellen Datei.|  
|[CStdioFile::WriteString](../Topic/CStdioFile::WriteString.md)|Schreibt eine einzelne Textzeile.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CStdioFile::m\_pStream](../Topic/CStdioFile::m_pStream.md)|Enthält einen Zeiger auf eine Datei öffnen.|  
  
## Hinweise  
 Streamdateien gepuffert werden und können im Textmodus \(Standard\) oder im binären Modus geöffnet werden.  
  
 Textmodus stellt das spezielle Verarbeitung für Wagenrücklauf\/Zeilenvorschub\-Paare bereit.  Wenn Sie ein Zeilenumbruchzeichen \(0x0A\) in ein `CStdioFile`\-Objekt im Textmodus schreiben, wird das Bytepaar \(0x0D, 0x0A\) an die Datei gesendet.  Als Sie lesen, wird das Bytepaar \(0x0D, 0x0A\) zu einem Byte 0x0A übersetzt.  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md) funktioniert [Duplikat](../Topic/CFile::Duplicate.md), [LockRange](../Topic/CFile::LockRange.md), und [UnlockRange](../Topic/CFile::UnlockRange.md) werden nicht für `CStdioFile` unterstützt.  
  
 Wenn Sie diese Funktionen auf `CStdioFile` aufrufen, rufen Sie [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md) ab.  
  
 Weitere Informationen zur Verwendung von `CStdioFile`, finden Sie in Artikel [Dateien in MFC](../../mfc/files-in-mfc.md) und [Datei\-Behandlung](../../c-runtime-library/file-handling.md) in der Laufzeitbibliotheksreferenz.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../Topic/CFile::Duplicate.md)   
 [CFile::LockRange](../Topic/CFile::LockRange.md)   
 [CFile::UnlockRange](../Topic/CFile::UnlockRange.md)   
 [CNotSupportedException Class](../../mfc/reference/cnotsupportedexception-class.md)   
 [Wie behebe ich: Verwenden Sie die C\-Datei Klasse?](http://go.microsoft.com/fwlink/?LinkId=128046)