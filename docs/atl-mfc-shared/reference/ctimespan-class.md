---
title: "CTimeSpan Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CTimeSpan"
  - "CTimeSpan"
  - "timespan"
  - "ATL::CTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTimeSpan class"
  - "Verstrichene Zeit, CTimeSpan object"
  - "shared classes, CTimeSpan"
  - "time span"
  - "Uhrzeit, elapsed"
  - "timespan"
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Zeitdauer, die intern als Anzahl von Sekunden in der Zeitraum gespeichert wird.  
  
## Syntax  
  
```  
class CTimeSpan  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CTimeSpan::CTimeSpan](../Topic/CTimeSpan::CTimeSpan.md)|Erstellt `CTimeSpan`\-Objekte auf verschiedene Arten.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CTimeSpan::Format](../Topic/CTimeSpan::Format.md)|Konvertiert `CTimeSpan` in eine formatierte Zeichenfolge.|  
|[CTimeSpan::GetDays](../Topic/CTimeSpan::GetDays.md)|Gibt einen Wert zurück, der die Anzahl der vollständigen Tagen in diesem `CTimeSpan` darstellt.|  
|[CTimeSpan::GetHours](../Topic/CTimeSpan::GetHours.md)|Gibt einen Wert zurück, der die Anzahl der Stunden im aktuellen Tag darstellt \(\- 23 bis 23\).|  
|[CTimeSpan::GetMinutes](../Topic/CTimeSpan::GetMinutes.md)|Gibt einen Wert zurück, der die Anzahl der Minuten in der laufenden Stunde darstellt \(\- 59 bis 59\).|  
|[CTimeSpan::GetSeconds](../Topic/CTimeSpan::GetSeconds.md)|Gibt einen Wert zurück, der die Anzahl der Sekunden in der Stromminute darstellt \(\- 59 bis 59\).|  
|[CTimeSpan::GetTimeSpan](../Topic/CTimeSpan::GetTimeSpan.md)|Gibt den Wert des `CTimeSpan`\-Objekts zurück.|  
|[CTimeSpan::GetTotalHours](../Topic/CTimeSpan::GetTotalHours.md)|Gibt einen Wert zurück, der die Gesamtzahl der vollständigen Stunden in diesem `CTimeSpan` darstellt.|  
|[CTimeSpan::GetTotalMinutes](../Topic/CTimeSpan::GetTotalMinutes.md)|Gibt einen Wert zurück, der die Gesamtzahl der vollständigen Minuten in diesem `CTimeSpan` darstellt.|  
|[CTimeSpan::GetTotalSeconds](../Topic/CTimeSpan::GetTotalSeconds.md)|Gibt einen Wert zurück, der die Gesamtzahl der vollständigen Sekunden in diesem `CTimeSpan` darstellt.|  
|[CTimeSpan::Serialize64](../Topic/CTimeSpan::Serialize64.md)|Serialisiert Daten in oder aus einem Archiv.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \+ \-](../Topic/CTimeSpan::operator%20+,%20-.md)|Fügt und subtrahiert `CTimeSpan`\-Objekte.|  
|[Operator \+\= \- \=](../Topic/CTimeSpan::operator%20+=,%20-=.md)|Addiert und subtrahiert ein `CTimeSpan`\-Objekt nach und von diesem `CTimeSpan`.|  
|[Operator \=\= \< usw..](../Topic/CTimeSpan%20Comparison%20Operators.md)|Vergleicht zwei relative Zeitwerte.|  
  
## Hinweise  
 `CTimeSpan` hat keine Basisklasse.  
  
 `CTimeSpan`\-Funktionen konvertieren Sekunden zu verschiedenen Kombinationen von Tagen, Stunden, Minuten und Sekunden von aus.  
  
 Das `CTimeSpan`\-Objekt wird in einer **\_\_time64\_t**\-Struktur gespeichert, die 8 Bytes ist.  
  
 Eine Assistentenklasse, [CTime](../../atl-mfc-shared/reference/ctime-class.md), stellt eine absoluten Zeit dar.  
  
 Die `CTime` und `CTimeSpan`\-Klassen sind nicht für Ableitung vorgesehen.  Da keine virtuellen Funktionen gibt, ist die Größe beider `CTime` und `CTimeSpan`\-Objekte genau 8 Bytes.  Die meisten Memberfunktionen sind inline.  
  
 Weitere Informationen zur Verwendung von `CTimeSpan`, finden Sie in Artikel [Datum und Uhrzeit](../../atl-mfc-shared/date-and-time.md) und [Zeit\-Verwaltung](../../c-runtime-library/time-management.md) in der *Laufzeitbibliotheksreferenz*.  
  
## Anforderungen  
 **Header:** atltime.h  
  
## Siehe auch  
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)