---
title: "CTime Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CTime"
  - "CTime"
  - "ATL::CTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTime class"
  - "shared classes, CTime"
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine absoluten Zeit und ein Datum dar.  
  
## Syntax  
  
```  
class CTime  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTime::CTime](../Topic/CTime::CTime.md)|Erstellt `CTime`\-Objekte auf verschiedene Arten.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTime::Format](../Topic/CTime::Format.md)|Konvertiert ein Objekt in `CTime` ein formatiertes zeichenfolgenbasiertes auf der lokalen Zeitzone.|  
|[CTime::FormatGmt](../Topic/CTime::FormatGmt.md)|Konvertiert ein Objekt in `CTime` ein formatiertes zeichenfolgenbasiertes auf UTC.|  
|[CTime::GetAsDBTIMESTAMP](../Topic/CTime::GetAsDBTIMESTAMP.md)|Konvertiert die Zeitinformationen, die im `CTime`\-Objekt einer Win32\-compatible <xref:System.Data.OleDb.OleDbType>\-Struktur gespeichert werden.|  
|[CTime::GetAsSystemTime](../Topic/CTime::GetAsSystemTime.md)|Konvertiert die Zeitinformationen, die im `CTime`\-Objekt einer Win32\-compatible [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)\-Struktur gespeichert werden.|  
|[CTime::GetCurrentTime](../Topic/CTime::GetCurrentTime.md)|Erstellt ein `CTime`\-Objekt, das die aktuelle Uhrzeit \(statische Memberfunktion\) darstellt.|  
|[CTime::GetDay](../Topic/CTime::GetDay.md)|Gibt den Tag darstellen `CTime` durch das Objekt zurück.|  
|[CTime::GetDayOfWeek](../Topic/CTime::GetDayOfWeek.md)|Gibt den Wochentag zurück, der durch das `CTime`\-Objekt dargestellt wird.|  
|[CTime::GetGmtTm](../Topic/CTime::GetGmtTm.md)|Stellt ein `CTime`\-Objekt in Komponenten auf Grundlage UTC auf.|  
|[CTime::GetHour](../Topic/CTime::GetHour.md)|Gibt die Stunde zurück, die vom `CTime`\-Objekt dargestellt wird.|  
|[CTime::GetLocalTm](../Topic/CTime::GetLocalTm.md)|Stellt ein `CTime`\-Objekt in Komponenten basierend auf die lokale Zeitzone auf.|  
|[CTime::GetMinute](../Topic/CTime::GetMinute.md)|Gibt die Minute zurück, die vom `CTime`\-Objekt dargestellt wird.|  
|[CTime::GetMonth](../Topic/CTime::GetMonth.md)|Gibt den Monat zurück, der durch das `CTime`\-Objekt dargestellt wird.|  
|[CTime::GetSecond](../Topic/CTime::GetSecond.md)|Gibt das zweite dargestellt durch das `CTime`\-Objekt zurück.|  
|[CTime::GetTime](../Topic/CTime::GetTime.md)|Gibt einen **\_\_time64\_t**\-Wert für das angegebene Objekt `CTime` zurück.|  
|[CTime::GetYear](../Topic/CTime::GetYear.md)|Gibt das Jahr zurück, das durch das `CTime`\-Objekt dargestellt wird.|  
|[CTime::Serialize64](../Topic/CTime::Serialize64.md)|Serialisiert Daten in oder aus einem Archiv.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \+ \-](../Topic/CTime::operator%20+,%20-.md)|Diese Operatoren hinzufügen und entfernen `CTimeSpan` und `CTime`\-Objekte.|  
|[Operator \+\=, \- \=](../Topic/CTime::operator%20+=,%20-=.md)|Diese Operatoren hinzufügen und entfernen `CTimeSpan` ein Objekt nach und von diesem `CTime`\-Objekt.|  
|[Operator \=](../Topic/CTime::operator%20=.md)|Der Zuweisungsoperator.|  
|[Operator \=\=, \<, usw..](../Topic/CTime%20Comparison%20Operators.md)|Vergleichsoperatoren.|  
  
## Hinweise  
 `CTime` hat keine Basisklasse.  
  
 `CTime`\-Werte basieren auf koordinierte Weltzeit \(UTC\), die zur koordinierten Weltzeit \(Greenwich Mean Time, GMT\) entspricht.  Siehe [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) zu Informationen darüber, wie die Zeitzone bestimmt wird.  
  
 Wenn Sie ein `CTime`\-Objekt erstellen, legen Sie den `nDST`\-Parameter auf 0 fest, um anzugeben, dass Normalzeit gültig ist, oder einen Wert, der größer ist als 0, anzugeben, dass Sommerzeit gültig ist, oder auf einen Wert kleiner als null für das die C\-Laufzeitbibliotheks\-Codeberechnung, ob Normalzeit oder Sommerzeit gültig ist.  `tm_isdst` ist ein Pflichtfeld.  Wenn nicht festgelegt ist, wird der Wert undefiniert und der Rückgabewert von [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) ist unvorhersehbar.  Wenn `timeptr` zu einer TM\-Struktur zeigt, die durch einen früheren Aufruf [asctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), zu [\_gmtime\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md) oder zu [localtime\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) zurückgegeben wird, enthält das `tm_isdst` Feld den richtigen Wert.  
  
 Eine Assistentenklasse, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), bietet ein Zeitintervall dar.  
  
 Die `CTime` und `CTimeSpan`\-Klassen sind nicht für Ableitung vorgesehen.  Da keine virtuellen Funktionen gibt, ist die Größe von `CTime` und von `CTimeSpan`\-Objekten genau 8 Bytes.  Die meisten Memberfunktionen sind inline.  
  
> [!NOTE]
>  Die obere Datumsgrenze 31.12.3000 ist.  Die Untergrenze ist 1\/1\/1970 12:00: GMT 00 fest.  
  
 Weitere Informationen zur Verwendung von `CTime`, finden Sie in Artikel [Datum und Uhrzeit](../../atl-mfc-shared/date-and-time.md) und [Zeit\-Verwaltung](../../c-runtime-library/time-management.md) in der Laufzeitbibliotheksreferenz.  
  
> [!NOTE]
>  Die `CTime`\-Struktur geändert von MFC 7.1 zu MFC 8.0.  Wenn Sie eine `CTime`\-Struktur serialisieren, indem Sie `operator <<` unter MFC 8.0 oder einer höheren Version verwenden, ist die resultierende Datei nicht auf früheren Versionen von MFC lesbar.  
  
## Anforderungen  
 **Header:** atltime.h  
  
## Siehe auch  
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)