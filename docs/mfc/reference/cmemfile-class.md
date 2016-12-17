---
title: "CMemFile Class"
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
  - "CMemFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemFile class"
  - "memory files"
  - "temporary files, memory files"
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CMemFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[Die C\-Datei](../../mfc/reference/cfile-class.md) von abgeleitete Klasse, die Arbeitsspeicherdateien unterstützt.  
  
## Syntax  
  
```  
class CMemFile : public CFile  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMemFile::CMemFile](../Topic/CMemFile::CMemFile.md)|Erstellt ein Arbeitsspeicherdateiobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMemFile::Attach](../Topic/CMemFile::Attach.md)|Fügt ein Speicherblock mit `CMemFile` an.|  
|[CMemFile::Detach](../Topic/CMemFile::Detach.md)|Trennt den Speicherblock von `CMemFile` und gibt einen Zeiger auf getrennten Speicherblock zurück.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMemFile::Alloc](../Topic/CMemFile::Alloc.md)|Überschreiben Sie, um des Speicherbelegungsverhaltens zu ändern.|  
|[CMemFile::Free](../Topic/CMemFile::Free.md)|Überschreiben Sie, um des Arbeitsspeicherfreigabenverhaltens zu ändern.|  
|[CMemFile::GrowFile](../Topic/CMemFile::GrowFile.md)|Überschreiben Sie, um das Verhalten zu ändern, wenn eine Datei gewachsen wird.|  
|[CMemFile::Memcpy](../Topic/CMemFile::Memcpy.md)|Überschreiben Sie, um des Arbeitsspeicherkopienverhaltens zu ändern, wenn Dateien gelesen und geschrieben werden.|  
|[CMemFile::Realloc](../Topic/CMemFile::Realloc.md)|Überschreiben Sie, um des Arbeitsspeicherneuzuordnungsverhaltens zu ändern.|  
  
## Hinweise  
 Diese Arbeitsspeicherdateien verhalten sich wie Datenträgerdateien, außer dass die Datei wird in RAM statt auf einem Datenträger gespeichert.  Eine Arbeitsspeicherdatei ist für schnelle temporäre Speicherung oder zum Übertragen von unformatierten Bytes oder serialisierter Objekten zwischen unabhängige Prozesse hilfreich.  
  
 `CMemFile`\-Objekte können ihren eigenen Speicher automatisch zuordnen, oder einen eigenen Speicherblock zum `CMemFile`\-Objekt anfügen, indem Sie [Anfügen](../Topic/CMemFile::Attach.md) aufrufen.  In jedem Fall wird für das nicht der Arbeitsspeicherdatei automatisch in groß Inkrementen `nGrowBytes` zugeordnet, wenn `nGrowBytes` nicht Null ist.  
  
 Der Speicherblock ist automatisch nach Zerstörung des `CMemFile`\-Objekts gelöscht, wenn der Arbeitsspeicher ursprünglich durch das `CMemFile`\-Objekt zugeordnet wurde, Andernfalls würden Sie zum Freigeben des Arbeitsspeichers verantwortlich, den Sie dem Objekt angefügt wurde.  
  
 Sie können auf den Speicherblock durch den Zeiger zugreifen, der angegeben wird, wenn Sie ihn im `CMemFile`\-Objekt trennen, indem Sie [Trennen Sie sich](../Topic/CMemFile::Detach.md) aufrufen.  
  
 Die häufigste Verwendung von `CMemFile` ist ein Objekt, `CMemFile` zu erstellen und es zu verwenden, indem sie [Die C\-Datei](../../mfc/reference/cfile-class.md)\-Memberfunktionen aufruft.  Beachten Sie, dass `CMemFile` öffnet erstellt es automatisch: Sie rufen nicht [CFile::Open](../Topic/CFile::Open.md) auf, für das nur Datenträgerdateien verwendet wird.  Da `CMemFile` keine Datenträgerdatei verwendet, wird der Datenmember `CFile::m_hFile` nicht verwendet und keine gültig.  
  
 Die `CFile`\-Memberfunktionen [Duplikat](../Topic/CFile::Duplicate.md), [LockRange](../Topic/CFile::LockRange.md) und [UnlockRange](../Topic/CFile::UnlockRange.md) werden nicht für `CMemFile` implementiert.  Wenn Sie aufrufen, gelten diese Funktionen auf `CMemFile`, erhalten Sie [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md) ein.  
  
 `CMemFile` verwendet die Laufzeitbibliotheksfunktionen [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md) und [frei](../../c-runtime-library/reference/free.md), Speicher zuzuordnen, neu belegen und freizugeben, und die systeminterne Funktion [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), um das Kopienarbeitsspeichers beim Lesen und Schreiben zu sperren.  Wenn Sie dieses Verhalten oder das Verhalten zu ändern, wenn `CMemFile` eine Datei vergrößert, leiten Sie die eigene Klasse von `CMemFile` und überschreiben Sie die entsprechenden Funktionen.  
  
 Weitere Informationen zu `CMemFile`, finden Sie in Artikel [Dateien in MFC](../../mfc/files-in-mfc.md) und [Speicherverwaltung \(MFC\)](../../mfc/memory-management.md) und [Datei\-Behandlung](../../c-runtime-library/file-handling.md) finden Sie unter in der Laufzeitbibliotheksreferenz.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)