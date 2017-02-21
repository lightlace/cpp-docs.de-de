---
title: "CFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive class, using with CFile"
  - "CFile class"
  - "Dateien [C++], classes for"
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für Microsoft Foundation Class\-Dateiklassen.  
  
## Syntax  
  
```  
class CFile : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFile::CFile](../Topic/CFile::CFile.md)|Erstellt ein Objekt `CFile` aus einem Pfad oder einem Dateihandle.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFile::Abort](../Topic/CFile::Abort.md)|Schließt eine Datei, die alle Warnungen und Fehler ignoriert.|  
|[CFile::Close](../Topic/CFile::Close.md)|Schließt eine Datei und löscht das Objekt.|  
|[CFile::Duplicate](../Topic/CFile::Duplicate.md)|Erstellt ein doppeltes Objekt auf Grundlage dieser Datei.|  
|[CFile::Flush](../Topic/CFile::Flush.md)|Leert alle noch zu schreibenden Daten.|  
|[CFile::GetFileName](../Topic/CFile::GetFileName.md)|Ruft den Dateinamen der ausgewählten Datei ab.|  
|[CFile::GetFilePath](../Topic/CFile::GetFilePath.md)|Ruft den vollständigen Pfad der ausgewählten Datei ab.|  
|[CFile::GetFileTitle](../Topic/CFile::GetFileTitle.md)|Ruft den Titel der ausgewählten Datei ab.|  
|[CFile::GetLength](../Topic/CFile::GetLength.md)|Ruft die Länge der Datei ab.|  
|[CFile::GetPosition](../Topic/CFile::GetPosition.md)|Ruft den Zeiger der aktuellen Datei ab.|  
|[CFile::GetStatus](../Topic/CFile::GetStatus.md)|Ruft den Status der Datei öffnen oder in der statischen Version abruft, den Status der angegebenen Funktion ab der Datei \(statische, virtuelles\).|  
|[CFile::LockRange](../Topic/CFile::LockRange.md)|Sperrt einen Bereich von Bytes in einer Datei.|  
|[CFile::Open](../Topic/CFile::Open.md)|Öffnet sicher eine Datei mit einer FehlerTests Option.|  
|[CFile::Read](../Topic/CFile::Read.md)|Liest \(ungepufferte\) Daten aus einer Datei in der Position der aktuellen Datei.|  
|[CFile::Remove](../Topic/CFile::Remove.md)|Löscht die angegebene Datei \(statische Funktion\).|  
|[CFile::Rename](../Topic/CFile::Rename.md)|Benennt die angegebene Datei \(statische Funktion\).|  
|[CFile::Seek](../Topic/CFile::Seek.md)|Positioniert den Zeiger der aktuellen Datei.|  
|[CFile::SeekToBegin](../Topic/CFile::SeekToBegin.md)|Positioniert den Zeiger der aktuellen Datei am Anfang der Datei.|  
|[CFile::SeekToEnd](../Topic/CFile::SeekToEnd.md)|Positioniert den Zeiger der aktuellen Datei am Ende der Datei.|  
|[CFile::SetFilePath](../Topic/CFile::SetFilePath.md)|Legt den vollständigen Pfad der ausgewählten Datei fest.|  
|[CFile::SetLength](../Topic/CFile::SetLength.md)|Ändert die Länge der Datei.|  
|[CFile::SetStatus](../Topic/CFile::SetStatus.md)|Legt den Status der angegebenen Funktion fest der Datei \(statische, virtuelles\).|  
|[CFile::UnlockRange](../Topic/CFile::UnlockRange.md)|Legt einen Bereich von Bytes in einer Datei frei.|  
|[CFile::Write](../Topic/CFile::Write.md)|Schreibt \(ungepufferte\) Daten in einer Datei zur Position der aktuellen Datei.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFile::operator HANDLE](../Topic/CFile::operator%20HANDLE.md)|Ein Handle für ein `CFile`\-Objekt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFile::hFileNull](../Topic/CFile::hFileNull.md)|Bestimmt, ob das Objekt `CFile` ein gültiges Handle verfügt.|  
|[CFile::m\_hFile](../Topic/CFile::m_hFile.md)|Enthält normalerweise das Dateihandle des Betriebssystems.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFile::m\_pTM](../Topic/CFile::m_pTM.md)|Zeiger auf `CAtlTransactionManager`\-Objekt.|  
  
## Hinweise  
 Es stellt direkt die nicht zwischengespeicherten, binäre Datenträgereingabe\/ausgabe\-Dienstleistungen, und unterstützt indirekt Textdateien und Arbeitsspeicherdateien durch seine abgeleitete Klassen.  `CFile` funktioniert in Verbindung mit der `CArchive`\-Klasse, um die Serialisierung von Microsoft Foundation Class\-Objekten zu unterstützen.  
  
 Die hierarchische Beziehung zwischen dieser Klasse und ihre abgeleiteten Klassen kann das Programm, um alle Dateiobjekte durch die polymorphe `CFile`\-Schnittstelle an auszuführen.  Eine Arbeitsspeicherdatei beispielsweise verhält sich wie eine Datenträgerdatei.  
  
 Verwenden Sie `CFile` und die abgeleiteten Klassen für allgemeine Datenträger\-E\/A.  Verwenden Sie `ofstream` oder andere Microsoft\-iostream Klassen für den formatierten Text, der in einer Datenträgerdatei gesendet wird.  
  
 Normalerweise ist eine Datenträgerdatei automatisch auf `CFile` Konstruktion geöffnet und geschlossen auf Zerstörung.  Statische Memberfunktionen, lassen Sie den Status einer Datei zu abfragen, ohne die Datei zu öffnen.  
  
 Weitere Informationen zur Verwendung von `CFile`, finden Sie in Artikel [Dateien in MFC](../../mfc/files-in-mfc.md) und [Datei\-Behandlung](../../c-runtime-library/file-handling.md) in der Laufzeitbibliotheksreferenz.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [MFC Sampling DRAWCLI](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStdioFile Class](../../mfc/reference/cstdiofile-class.md)   
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [Wie behebe ich: Verwenden Sie die C\-Datei Klasse?](http://go.microsoft.com/fwlink/?LinkId=128046)