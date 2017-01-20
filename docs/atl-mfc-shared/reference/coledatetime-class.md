---
title: "COleDateTime Class"
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
  - "COleDateTime"
  - "ATL.COleDateTime"
  - "ATL::COleDateTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDateTime class"
  - "Date-Datentyp, MFC encapsulation of"
  - "Datumsangaben, handling in MFC"
  - "shared classes, COleDateTime"
  - "Uhrzeit, handling in MFC"
  - "time-only values"
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 34
caps.handback.revision: "26"
ms.author: "mblome"
manager: "ghogen"
---
# COleDateTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt den `DATE` Datentyp, der in der OLE\-Automatisierung verwendet wird.  
  
## Syntax  
  
```  
class COleDateTime  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](../Topic/COleDateTime::COleDateTime.md)|Erstellt ein `COleDateTime`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDateTime::Format](../Topic/COleDateTime::Format.md)|Generiert eine formatierte Zeichenfolgendarstellung eines Objekts `COleDateTime`.|  
|[COleDateTime::GetAsDBTIMESTAMP](../Topic/COleDateTime::GetAsDBTIMESTAMP.md)|Rufen Sie diese Methode auf, um die Zeit im `COleDateTime`\-Objekt als **DBTIMESTAMP** Datenstruktur zu erhalten.|  
|[COleDateTime::GetAsSystemTime](../Topic/COleDateTime::GetAsSystemTime.md)|Rufen Sie diese Methode auf, um die Zeit im `COleDateTime`\-Objekt als [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Datenstruktur zu erhalten.|  
|[COleDateTime::GetAsUDATE](../Topic/COleDateTime::GetAsUDATE.md)|Rufen Sie diese Methode auf, um die Zeit in `COleDateTime` als **UDATE** Datenstruktur zu erhalten.|  
|[COleDateTime::GetCurrentTime](../Topic/COleDateTime::GetCurrentTime.md)|Erstellt ein `COleDateTime`\-Objekt, das die aktuelle Uhrzeit \(statische Memberfunktion\) darstellt.|  
|[COleDateTime::GetDay](../Topic/COleDateTime::GetDay.md)|Gibt den Tag zurück, den dieses Objekt `COleDateTime` darstellt \(1 \- 31\).|  
|[COleDateTime::GetDayOfWeek](../Topic/COleDateTime::GetDayOfWeek.md)|Gibt den Wochentag zurück, den dieses Objekt `COleDateTime` darstellt \(Sonntag \= 1\).|  
|[COleDateTime::GetDayOfYear](../Topic/COleDateTime::GetDayOfYear.md)|Gibt den Tag des Jahres zurück, das dieses Objekt darstellt `COleDateTime` \(1. Januar \= 1\).|  
|[COleDateTime::GetHour](../Topic/COleDateTime::GetHour.md)|Gibt die Stunde zurück, die dieses `COleDateTime`\-Objekt darstellt \(0 \- 23\).|  
|[COleDateTime::GetMinute](../Topic/COleDateTime::GetMinute.md)|Gibt die Minute zurück, die dieses `COleDateTime`\-Objekt darstellt \(0 \- 59\).|  
|[COleDateTime::GetMonth](../Topic/COleDateTime::GetMonth.md)|Gibt den Monat zurück, den dieses Objekt `COleDateTime` darstellt \(1 \- 12\).|  
|[COleDateTime::GetSecond](../Topic/COleDateTime::GetSecond.md)|Gibt das zweite dieses Objekt darstellt `COleDateTime` zurück \(0 \- 59\).|  
|[COleDateTime::GetStatus](../Topic/COleDateTime::GetStatus.md)|Ruft den Status \(Gültigkeit\) dieses `COleDateTime`\-Objekts ab.|  
|[COleDateTime::GetYear](../Topic/COleDateTime::GetYear.md)|Gibt das Jahr zurück, das `COleDateTime` dieses Objekt darstellt.|  
|[COleDateTime::ParseDateTime](../Topic/COleDateTime::ParseDateTime.md)|Liest einen Datums\-\/Uhrzeitwert einer Zeichenfolge und legt den Wert von `COleDateTime` fest.|  
|[COleDateTime::SetDate](../Topic/COleDateTime::SetDate.md)|Legt den Wert `COleDateTime` dieses \- Objekts mit dem angegebenen nur für Datum Wert fest.|  
|[COleDateTime::SetDateTime](../Topic/COleDateTime::SetDateTime.md)|Legt den Wert `COleDateTime` dieses \- Objekts mit dem angegebenen Datum\/den Zeitwert fest.|  
|[COleDateTime::SetStatus](../Topic/COleDateTime::SetStatus.md)|Legt den Status \(Gültigkeit\) dieses `COleDateTime`\-Objekts fest.|  
|[COleDateTime::SetTime](../Topic/COleDateTime::SetTime.md)|Legt den Wert `COleDateTime` dieses \- Objekts mit dem angegebenen nur für Zeit Wert fest.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDateTime::operator\-\=\=, COleDateTime::operator \<, usw..](../Topic/COleDateTime%20Relational%20Operators.md)|Vergleicht zwei Werte `COleDateTime`.|  
|[COleDateTime::operator \+, \- COleDateTime::operator](../Topic/COleDateTime::operator%20+,%20-.md)|Hinzufügen und Subtrahieren `COleDateTime`\-Werte.|  
|[COleDateTime::operator \+\=, COleDateTime::operator \- \=](../Topic/COleDateTime::operator%20+=,%20-=.md)|Hinzufügen und Subtrahieren `COleDateTime` einen Wert von diesem `COleDateTime`\-Objekt.|  
|[COleDateTime::operator \=](../Topic/COleDateTime::operator%20=.md)|Kopiert einen `COleDateTime`\-Wert.|  
|[COleDateTime::operator\-DATUM, COleDateTime::operator Date\*](../Topic/COleDateTime::operator%20DATE.md)|Konvertiert einen Wert in `COleDateTime``DATE` oder in `DATE*`.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleDateTime::m\_dt](../Topic/COleDateTime::m_dt.md)|Enthält zugrunde liegende **date**`COleDateTime` für dieses Objekt.|  
|[COleDateTime::m\_status](../Topic/COleDateTime::m_status.md)|Enthält den Status dieses `COleDateTime`\-Objekts.|  
  
## Hinweise  
 `COleDateTime` hat keine Basisklasse.  
  
 Sie ist einer der möglichen Typen für den [VARIANTE](assetId:///e305240e-9e11-4006-98cc-26f4932d2118) Datentyp der OLE\-Automatisierung.  Ein `COleDateTime`\-Wert stellt einen absoluten Datums\- und Uhrzeitwert.  
  
 Der `DATE`\-Typ wird als Gleitkommawert implementiert.  Tage werden ab dem 30. Dezember 1899, um Mitternacht gemessen.  In der folgenden Tabelle sind bestimmte Datumsangaben und die zugehörigen Werte an:  
  
|Datum|Wert|  
|-----------|----------|  
|29. Dezember 1899 Mitternacht|\-1.0|  
|29. Dezember 1899 6 A.m.|\-1.25|  
|30. Dezember 1899 Mitternacht|0.0|  
|31. Dezember 1899 Mitternacht|1.0|  
|1. Januar 1900 6 Uhr..|2.25|  
  
> [!CAUTION]
>  Hinweis in der Tabelle über dem, obwohl Tagswerte vor Mitternacht am 30. Dezember 1899 negativ werden, und Uhrzeitwerte dies jedoch nicht.  Beispielsweise wird 6:00 AM immer über einen Bruchen Wert 0,25 unabhängig von dargestellt, dass die ganze Zahl, die den Tag darstellt, positiv \(nach dem 30. Dezember 1899\) oder negative ist \(vor dem 30. Dezember 1899\).  Dies bedeutet, dass ein einfacher Gleitkommavergleich fälschlicherweise `COleDateTime`, das 6:00 AM auf 12\/29\/1899 darstellt, als **später** sortieren als eines, das 7:00 AM am selben Tag darstellt.  
  
 Die `COleDateTime`\-Klasse behandelt Datumsangaben vom 1. Januar, 100 9999 bis zum 31. Dezember.  Die `COleDateTime`\-Klasse verwendet den gregorianischen Kalender, sie nicht unterstützt julianische Datumsangaben.  `COleDateTime` ignoriert Sommerzeit.  \(Siehe [Datum und Uhrzeit: Automatisierungs\-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).\)  
  
> [!NOTE]
>  Sie können das `%y` Format verwenden, um eine zweistellige Jahresangabe nur für Datumsangaben abzurufen beginnend bei 1900.  Wenn Sie das `%y` Format auf einem Datum bis 1900 verwenden, generiert der Code einen ASSERTIONSfehler.  
  
 Dieser Typ wird auch verwendet, um die nur für Datum oder Uhrzeit nur für Werte darzustellen.  Standardmäßig wird das Datum 0 \(30. Dezember 1899\) nur für Zeitwerte und die Zeit 00:00 \(Mitternacht\) wird nur für Datumswerte verwendet.  
  
 Wenn Sie ein `COleDateTime`\-Objekt erstellen, indem Sie ein Datum weniger als 100 verwenden, wird das Datum, aber nachfolgende Aufrufe `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute` und `GetSecond` Fail und geben \-1 akzeptiert.  Zuvor konnten Sie zweistellige Datumsangaben verwenden, aber Datumsangaben müssen in MFC 4.2 100 oder größer sein und höher.  
  
 Um Probleme zu vermeiden, geben Sie ein vierstelliges Datum an.  Beispiel:  
  
 [!CODE [NVC_ATLMFC_Utilities#1](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#1)]  
  
 Grundlegende arithmetische Operationen für die `COleDateTime`\-Werte verwenden die Assistentenklasse [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md).  `COleDateTimeSpan`\-Werte definieren ein Zeitintervall.  Die Beziehung zwischen diesen Klassen ist bis die zwischen [CTime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md) ähnlich.  
  
 Weitere Informationen über die `COleDateTime` und `COleDateTimeSpan`\-Klassen, finden Sie im Artikel [Datum und Uhrzeit: Automatisierungs\-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## Anforderungen  
 **Header:** ATLComTime.h  
  
## Siehe auch  
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CTime Class](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)