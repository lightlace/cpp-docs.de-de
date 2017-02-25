---
title: "CFileTime Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CFileTime"
  - "CFileTime"
  - "ATL.CFileTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTime class"
  - "shared classes, CFileTime"
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CFileTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Verwalten der Datums\- und Uhrzeitwerte, die einer Datei zugeordnet werden.  
  
## Syntax  
  
```  
  
   class CFileTime :   
public FILETIME  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFileTime::CFileTime](../Topic/CFileTime::CFileTime.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](../Topic/CFileTime::GetCurrentTime.md)|Rufen Sie diese statische Funktion auf, um ein `CFileTime`\-Objekt abzurufen, das das aktuelle Systemdatum und \-zeit darstellt.|  
|[CFileTime::GetTime](../Topic/CFileTime::GetTime.md)|Rufen Sie diese Methode auf, um die Zeit vom `CFileTime`\-Objekt abzurufen.|  
|[CFileTime::LocalToUTC](../Topic/CFileTime::LocalToUTC.md)|Rufen Sie diese Methode auf, um eine lokale Dateizeit zu einer Dateizeit auf Grundlage der koordinierten Weltzeit \(UTC\) konvertiert.|  
|[CFileTime::SetTime](../Topic/CFileTime::SetTime.md)|Rufen Sie diese Methode auf, um das Datum und die Uhrzeit festzulegen, die vom `CFileTime`\-Objekt gespeichert werden.|  
|[CFileTime::UTCToLocal](../Topic/CFileTime::UTCToLocal.md)|Rufen Sie diese Methode auf, um Zeit auf Grundlage der koordinierten Weltzeit \(UTC\) der lokalen Dateizeit zu konvertieren.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFileTime::operator \-](../Topic/CFileTime::operator%20-.md)|Dieser Operator wird verwendet, um Subtraktion auf einem `CFileTime` oder `CFileTimeSpan`\-Objekt auszuführen.|  
|[CFileTime::operator \!\=](../Topic/CFileTime::operator%20!=.md)|Dieser Operator vergleicht zwei `CFileTime`\-Objekte für Ungleichheit.|  
|[CFileTime::operator \+](../Topic/CFileTime::operator%20+.md)|Dieser Operator wird verwendet, um Addition auf einem `CFileTimeSpan`\-Objekt auszuführen.|  
|[CFileTime::operator \+\=](../Topic/CFileTime::operator%20+=.md)|Dieser Operator wird verwendet, um Addition auf einem `CFileTimeSpan`\-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zugewiesen.|  
|[CFileTime::operator \<](../Topic/CFileTime::operator%20%3C.md)|Dieser Operator vergleicht zwei `CFileTime`\-Objekte, um die kleiner zu bestimmen.|  
|[CFileTime::operator \<\=](../Topic/CFileTime::operator%20%3C=.md)|Dieser Operator vergleicht zwei `CFileTime`\-Objekte, um die Gleichheit oder kleiner zu bestimmen.|  
|[CFileTime::operator \=](../Topic/CFileTime::operator%20=.md)|Der Zuweisungsoperator.|  
|[CFileTime::operator \-\=](../Topic/CFileTime::operator%20-=.md)|Dieser Operator wird verwendet, um Subtraktion auf einem `CFileTimeSpan`\-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zugewiesen.|  
|[CFileTime::operator \=\=](../Topic/CFileTime::operator%20==.md)|Dieser Operator vergleicht zwei `CFileTime`\-Objekte auf Gleichheit.|  
|[CFileTime::operator \>](../Topic/CFileTime::operator%20%3E.md)|Dieser Operator vergleicht zwei `CFileTime`\-Objekte, um das größere zu bestimmen.|  
|[CFileTime::operator \>\=](../Topic/CFileTime::operator%20%3E=.md)|Dieser Operator vergleicht zwei `CFileTime`\-Objekte, um Gleichheit oder das größere zu bestimmen.|  
  
### Öffentliche Konstanten  
  
|Name|Description|  
|----------|-----------------|  
|[CFileTime::Day](../Topic/CFileTime::Day.md)|Ein statischer Datenmember, der die Anzahl der Intervall von 100 Nanosekunden speichert, die einen Tag bilden.|  
|[CFileTime::Hour](../Topic/CFileTime::Hour.md)|Ein statischer Datenmember, der die Anzahl der Intervall von 100 Nanosekunden speichert, die eine Stunde bilden.|  
|[CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md)|Ein statischer Datenmember, der die Anzahl der Intervall von 100 Nanosekunden speichert, die eine Millisekunde bilden.|  
|[CFileTime::Minute](../Topic/CFileTime::Minute.md)|Ein statischer Datenmember, der die Anzahl der Intervall von 100 Nanosekunden speichert, die eine Minute bilden.|  
|[CFileTime::Second](../Topic/CFileTime::Second.md)|Ein statischer Datenmember, der die Anzahl der Intervall von 100 Nanosekunden speichert, die eine weitere bilden.|  
|[CFileTime::Week](../Topic/CFileTime::Week.md)|Ein statischer Datenmember, der die Anzahl der Intervall von 100 Nanosekunden speichert, die eine Woche bilden.|  
  
## Hinweise  
 Diese Klasse stellt Methoden zum Verwalten der Datums\- und Uhrzeitwerte, die mit der Erstellung, dem Zugriff und die Änderung von Dateien zugeordnet sind.  Die Methoden und die Daten dieser Klasse werden häufig in Verbindung mit `CFileTimeSpan`\-Objekte verwendet, die relative Zeitwerte verarbeiten.  
  
 Der Datums\- und Uhrzeitwert wird als 64\-Bit\-Wert gespeichert, der die Anzahl der Intervall von 100 Nanosekunden seit dem 1. Januar 1601 darstellt.  Dies ist das Format der koordinierten Weltzeit \(UTC\).  
  
 Die folgenden statischen const Membervariablen werden bereitgestellt, um Berechnungen zu vereinfachen:  
  
|Membervariable|Zahl Intervall von 100 Nanosekunden|  
|--------------------|-----------------------------------------|  
|Millisecond|10,000|  
|Sekunde|\* 1.000 Millisekunde|  
|Minute|Zweite \* 60|  
|Stunde|\* 60 Minute|  
|Tag|\* 24 Stunde|  
|Woche|\* 7 Tag|  
  
 **Hinweis**  nicht alle Dateisysteme kann Rekorderstellung und letzten Zugriffs und nicht alle Dateisysteme sie auf dieselbe Weise aufzeichnen.  Beispielsweise auf dem Windows NT FAT\-Dateisystem, hat Erstellungszeit eine Auflösung von 10 Millisekunden, schreiben Zeit hat eine Auflösung von 2 Sekunden, und Zugriffs hat eine Auflösung von 1 Tag \(das Zugriffs\).  Auf NTFS Zugriffs hat eine Auflösung von 1 Stunden.  Darüber hinaus FAT\-Datensatzzeiten auf dem Datenträger in Ortszeit\-, aber NTFS\-Datensatzzeiten auf dem Datenträger in UTC.  Weitere Informationen finden Sie unter [Datei\-Zeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## Vererbungshierarchie  
 `FILETIME`  
  
 `CFileTime`  
  
## Anforderungen  
 **Header:** atltime.h  
  
## Siehe auch  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan Class](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)