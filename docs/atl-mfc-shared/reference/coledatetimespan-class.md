---
title: "COleDateTimeSpan Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.COleDateTimeSpan"
  - "COleDateTimeSpan"
  - "ATL::COleDateTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDateTimeSpan class"
  - "Date-Datentyp, MFC encapsulation of"
  - "shared classes, COleDateTimeSpan"
  - "time span"
  - "timespan"
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# COleDateTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine relative Zeit, eine Dauer dar.  
  
## Syntax  
  
```  
class COleDateTimeSpan  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](../Topic/COleDateTimeSpan::COleDateTimeSpan.md)|Erstellt ein `COleDateTimeSpan`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](../Topic/COleDateTimeSpan::Format.md)|Generiert eine formatierte Zeichenfolgendarstellung eines Objekts `COleDateTimeSpan`.|  
|[COleDateTimeSpan::GetDays](../Topic/COleDateTimeSpan::GetDays.md)|Gibt den Tagsteil der Spanne zurück, die dieses `COleDateTimeSpan`\-Objekt darstellt.|  
|[COleDateTimeSpan::GetHours](../Topic/COleDateTimeSpan::GetHours.md)|Gibt den Stundenteil der Spanne zurück, die dieses `COleDateTimeSpan`\-Objekt darstellt.|  
|[COleDateTimeSpan::GetMinutes](../Topic/COleDateTimeSpan::GetMinutes.md)|Gibt den winzigen Teil der Spanne zurück, die dieses `COleDateTimeSpan`\-Objekt darstellt.|  
|[COleDateTimeSpan::GetSeconds](../Topic/COleDateTimeSpan::GetSeconds.md)|Gibt den zweiten Teil der Spanne zurück, die dieses `COleDateTimeSpan`\-Objekt darstellt.|  
|[COleDateTimeSpan::GetStatus](../Topic/COleDateTimeSpan::GetStatus.md)|Ruft den Status \(Gültigkeit\) dieses `COleDateTimeSpan`\-Objekts ab.|  
|[COleDateTimeSpan::GetTotalDays](../Topic/COleDateTimeSpan::GetTotalDays.md)|Gibt die Anzahl von Tagen zurück, die dieses `COleDateTimeSpan`\-Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalHours](../Topic/COleDateTimeSpan::GetTotalHours.md)|Gibt die Anzahl von Stunden zurück, die dieses `COleDateTimeSpan`\-Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalMinutes](../Topic/COleDateTimeSpan::GetTotalMinutes.md)|Gibt die Anzahl von Minuten zurück, die dieses `COleDateTimeSpan`\-Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalSeconds](../Topic/COleDateTimeSpan::GetTotalSeconds.md)|Gibt die Anzahl der Sekunden zurück, die dieses `COleDateTimeSpan`\-Objekt darstellt.|  
|[COleDateTimeSpan::SetDateTimeSpan](../Topic/COleDateTimeSpan::SetDateTimeSpan.md)|Legt den Wert dieses `COleDateTimeSpan`\-Objekts fest.|  
|[COleDateTimeSpan::SetStatus](../Topic/COleDateTimeSpan::SetStatus.md)|Legt den Status \(Gültigkeit\) dieses `COleDateTimeSpan`\-Objekts fest.|  
  
### Öffentliche Operatoren  
  
|||  
|-|-|  
|[Operatoren \+, \-](../Topic/COleDateTimeSpan::operator%20+,%20-.md)|Hinzufügen, Subtrahieren und ändern Sie Zeichen für `COleDateTimeSpan`\-Werte.|  
|[Operator \+\=, \- \=](../Topic/COleDateTimeSpan::operator%20+=,%20-=.md)|Hinzufügen und Subtrahieren `COleDateTimeSpan` einen Wert von diesem `COleDateTimeSpan`\-Wert.|  
|[Operator \=](../Topic/COleDateTimeSpan::operator%20=.md)|Kopiert einen `COleDateTimeSpan`\-Wert.|  
|[Operator \=\=, \<, \<\=](../Topic/COleDateTimeSpan%20Relational%20Operators.md)|Vergleicht zwei Werte `COleDateTimeSpan`.|  
|[Operatordouble](../Topic/COleDateTimeSpan::operator%20double.md)|Konvertiert diesen `COleDateTimeSpan`\-Wert zu **double**.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleDateTimeSpan::m\_span](../Topic/COleDateTimeSpan::m_span.md)|Enthält zugrunde liegende **double**`COleDateTimeSpan` für dieses Objekt.|  
|[COleDateTimeSpan::m\_status](../Topic/COleDateTimeSpan::m_status.md)|Enthält den Status dieses `COleDateTimeSpan`\-Objekts.|  
  
## Hinweise  
 `COleDateTimeSpan` hat keine Basisklasse.  
  
 `COleDateTimeSpan` enthält Zeit in Tagen.  
  
 `COleDateTimeSpan` wird einer Assistentenklasse [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) verwendet.  `COleDateTime` kapselt den **DATE** Datentyp der OLE\-Automatisierung.  `COleDateTime` stellt absolute Zeitwerte dar.  Alle `COleDateTime` Berechnungen werden `COleDateTimeSpan`\-Werte mit ein.  Die Beziehung zwischen diesen Klassen ist bis die zwischen [CTime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md) analog.  
  
 Weitere Informationen über die `COleDateTime` und `COleDateTimeSpan`\-Klassen, finden Sie im Artikel [Datum und Uhrzeit: Automatisierungs\-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## Anforderungen  
 **Header:** ATLComTime.h  
  
## Siehe auch  
 [COleDateTime Class](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime Class](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)