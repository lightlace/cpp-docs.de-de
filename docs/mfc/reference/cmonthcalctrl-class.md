---
title: "CMonthCalCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMonthCalCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl class"
  - "Allgemeine Steuerelemente, Internet Explorer 4.0"
  - "Internet Explorer 4.0 common controls"
  - "month calendar controls"
  - "month calendar controls, CMonthCalCtrl class"
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMonthCalCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt die Funktionalität eines Monatskalender\-Steuerelements.  
  
## Syntax  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMonthCalCtrl::CMonthCalCtrl](../Topic/CMonthCalCtrl::CMonthCalCtrl.md)|Erstellt ein `CMonthCalCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMonthCalCtrl::Create](../Topic/CMonthCalCtrl::Create.md)|Erstellt ein Monatskalender\-Steuerelement und fügt es dem `CMonthCalCtrl`\-Objekt.|  
|[CMonthCalCtrl::GetCalendarBorder](../Topic/CMonthCalCtrl::GetCalendarBorder.md)|Ruft die Breite des Rahmens des aktuellen Monatskalender\-Steuerelements ab.|  
|[CMonthCalCtrl::GetCalendarCount](../Topic/CMonthCalCtrl::GetCalendarCount.md)|Ruft die Anzahl der Kalendern ab, die im aktuellen Monatskalender\-Steuerelement angezeigt werden.|  
|[CMonthCalCtrl::GetCalendarGridInfo](../Topic/CMonthCalCtrl::GetCalendarGridInfo.md)|Ruft Informationen über das aktuelle Monatskalender\-Steuerelement ab.|  
|[CMonthCalCtrl::GetCalID](../Topic/CMonthCalCtrl::GetCalID.md)|Ruft den Kalenderbezeichner für das aktuelle Monatskalender\-Steuerelement ab.|  
|[CMonthCalCtrl::GetColor](../Topic/CMonthCalCtrl::GetColor.md)|Ruft die Farbe eines angegebenen Bereichs eines Monatskalender\-Steuerelements ab.|  
|[CMonthCalCtrl::GetCurrentView](../Topic/CMonthCalCtrl::GetCurrentView.md)|Ruft die Ansicht ab, die derzeit vom aktuellen Monatskalender\-Steuerelement angezeigt wird.|  
|[CMonthCalCtrl::GetCurSel](../Topic/CMonthCalCtrl::GetCurSel.md)|Ruft die Systemzeit ab, wie bis zu dem derzeit ausgewählten Datum angegeben.|  
|[CMonthCalCtrl::GetFirstDayOfWeek](../Topic/CMonthCalCtrl::GetFirstDayOfWeek.md)|Ruft den ersten ab in der Spalte ganz links des Kalenders angezeigt werden Wochentag.|  
|[CMonthCalCtrl::GetMaxSelCount](../Topic/CMonthCalCtrl::GetMaxSelCount.md)|Ruft die aktuelle maximale Anzahl von Tagen ab, die in einem Monatskalender\-Steuerelement ausgewählt werden können.|  
|[CMonthCalCtrl::GetMaxTodayWidth](../Topic/CMonthCalCtrl::GetMaxTodayWidth.md)|Ruft die maximale Breite von "today" String für das aktuelle Monatskalender\-Steuerelement ab.|  
|[CMonthCalCtrl::GetMinReqRect](../Topic/CMonthCalCtrl::GetMinReqRect.md)|Ruft die minimale Größe ab, die erforderlich ist, einen vollständigen Monat in einem Monatskalender\-Steuerelement anzuzeigen.|  
|[CMonthCalCtrl::GetMonthDelta](../Topic/CMonthCalCtrl::GetMonthDelta.md)|Ruft die Bildlaufkinetik für ein Monatskalender\-Steuerelement ab.|  
|[CMonthCalCtrl::GetMonthRange](../Topic/CMonthCalCtrl::GetMonthRange.md)|Ruft die Datumsinformationen ab, die das Hoch und die Niedrigstände der Anzeige eines Monatskalender\-Steuerelements darstellen.|  
|[CMonthCalCtrl::GetRange](../Topic/CMonthCalCtrl::GetRange.md)|Ruft die laufenden minimale und maximale Datum ab, die in einem Monatskalender\-Steuerelement festgelegt werden.|  
|[CMonthCalCtrl::GetSelRange](../Topic/CMonthCalCtrl::GetSelRange.md)|Ruft die Datumsinformationen ab, die das der Ober\- und Untergrenze des Datumsbereichs darstellen, der derzeit vom Benutzer ausgewählt wird.|  
|[CMonthCalCtrl::GetToday](../Topic/CMonthCalCtrl::GetToday.md)|Ruft die Datumsinformationen für das Datum ab, das für ein Monatskalender\-Steuerelement angegeben wird als "today".|  
|[CMonthCalCtrl::HitTest](../Topic/CMonthCalCtrl::HitTest.md)|Bestimmt, die Abschnitt eines Monatskalender\-Steuerelements an einem angegebenen Punkt auf dem Bildschirm angezeigt wird.|  
|[CMonthCalCtrl::IsCenturyView](../Topic/CMonthCalCtrl::IsCenturyView.md)|Gibt an, ob die aktuelle Ansicht des aktuellen Monatskalender\-Steuerelements die Jahrhundertansicht ist.|  
|[CMonthCalCtrl::IsDecadeView](../Topic/CMonthCalCtrl::IsDecadeView.md)|Gibt an, ob die aktuelle Ansicht des aktuellen Monatskalender\-Steuerelements die Jahrzehntansicht ist.|  
|[CMonthCalCtrl::IsMonthView](../Topic/CMonthCalCtrl::IsMonthView.md)|Gibt an, ob die aktuelle Ansicht des aktuellen Monatskalender\-Steuerelements die Monatsansicht ist.|  
|[CMonthCalCtrl::IsYearView](../Topic/CMonthCalCtrl::IsYearView.md)|Gibt an, ob die aktuelle Ansicht des aktuellen Monatskalender\-Steuerelements die Jahransicht ist.|  
|[CMonthCalCtrl::SetCalendarBorder](../Topic/CMonthCalCtrl::SetCalendarBorder.md)|Gibt die Breite des Rahmens des aktuellen Monatskalender\-Steuerelements fest.|  
|[CMonthCalCtrl::SetCalendarBorderDefault](../Topic/CMonthCalCtrl::SetCalendarBorderDefault.md)|Legt die Standardbreite des Rahmens des aktuellen Monatskalender\-Steuerelements fest.|  
|[CMonthCalCtrl::SetCalID](../Topic/CMonthCalCtrl::SetCalID.md)|Legt den Kalenderbezeichner für das aktuelle Monatskalender\-Steuerelement fest.|  
|[CMonthCalCtrl::SetCenturyView](../Topic/CMonthCalCtrl::SetCenturyView.md)|Legt das aktuelle Monatskalender\-Steuerelement fest, um die Jahrhundertansicht anzuzeigen.|  
|[CMonthCalCtrl::SetColor](../Topic/CMonthCalCtrl::SetColor.md)|Legt die Farbe eines angegebenen Bereichs eines Monatskalender\-Steuerelements fest.|  
|[CMonthCalCtrl::SetCurrentView](../Topic/CMonthCalCtrl::SetCurrentView.md)|Legt das aktuelle Monatskalender\-Steuerelement fest, um die angegebene Ansicht anzuzeigen.|  
|[CMonthCalCtrl::SetCurSel](../Topic/CMonthCalCtrl::SetCurSel.md)|Legt das derzeit ausgewählte Datum für ein Monatskalender\-Steuerelement fest.|  
|[CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md)|Legt die Anzeige für Tage in einem Monatskalender\-Steuerelement fest.|  
|[CMonthCalCtrl::SetDecadeView](../Topic/CMonthCalCtrl::SetDecadeView.md)|Legt das aktuelle Monatskalender\-Steuerelement zur Jahrzehntansicht fest.|  
|[CMonthCalCtrl::SetFirstDayOfWeek](../Topic/CMonthCalCtrl::SetFirstDayOfWeek.md)|Legt den fest in der Spalte ganz links des Kalenders angezeigt werden Wochentag.|  
|[CMonthCalCtrl::SetMaxSelCount](../Topic/CMonthCalCtrl::SetMaxSelCount.md)|Legt die maximale Anzahl von Tagen fest, die in einem Monatskalender\-Steuerelement ausgewählt werden können.|  
|[CMonthCalCtrl::SetMonthDelta](../Topic/CMonthCalCtrl::SetMonthDelta.md)|Legt die Bildlaufkinetik für ein Monatskalender\-Steuerelement fest.|  
|[CMonthCalCtrl::SetMonthView](../Topic/CMonthCalCtrl::SetMonthView.md)|Legt das aktuelle Monatskalender\-Steuerelement fest, um die Monatsansicht anzuzeigen.|  
|[CMonthCalCtrl::SetRange](../Topic/CMonthCalCtrl::SetRange.md)|Legt die minimalen und maximalen zulässigen Datumsangaben für ein Monatskalender\-Steuerelement fest.|  
|[CMonthCalCtrl::SetSelRange](../Topic/CMonthCalCtrl::SetSelRange.md)|Legt die Auswahl für ein Monatskalender\-Steuerelement zu einem angegebenen Datumsbereich fest.|  
|[CMonthCalCtrl::SetToday](../Topic/CMonthCalCtrl::SetToday.md)|Legt das Calendar\-Steuerelement während des aktuellen Tages fest.|  
|[CMonthCalCtrl::SetYearView](../Topic/CMonthCalCtrl::SetYearView.md)|Legt das aktuelle Monatskalender\-Steuerelement zur Jahransicht fest.|  
|[CMonthCalCtrl::SizeMinReq](../Topic/CMonthCalCtrl::SizeMinReq.md)|Streicht das Monatskalender\-Steuerelement auf den minimalen, einmonatige Größe neu.|  
|[CMonthCalCtrl::SizeRectToMin](../Topic/CMonthCalCtrl::SizeRectToMin.md)|Für das aktuelle Monatskalender\-Steuerelement berechnet das kleinste Rechteck, das alle Kalender diese Anpassung in einem angegebenen Rechteck enthalten kann.|  
  
## Hinweise  
 Das Monatskalender\-Steuerelement stellt dem Benutzer mit einer einfachen Kalenderschnittstelle, aus der der Benutzer ein Datum auswählen kann.  Der Benutzer kann die Anzeige von ändern:  
  
-   Das Bildlauf rückwärts und leiten, von Monat zu Monat weiter.  
  
-   Auf den heutigen Tag klicken, Text Sie, um den aktuellen Tag anzuzeigen \(wenn das **MCS\_NOTODAY** Format nicht verwendet wird\).  
  
-   Auswählen eines Monats oder des Jahres von einem Popupmenü.  
  
 Sie können das Monatskalender\-Steuerelement anpassen, indem Sie eine Vielzahl von Formaten auf das Objekt anwenden, wenn Sie sie erstellen.  Diese Formate werden in [Monatskalender\-Steuerelement\-Formate](http://msdn.microsoft.com/library/windows/desktop/bb760919) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] beschrieben.  
  
 Das Monatskalender\-Steuerelement kann mehr als einen Monat anzeigen, und es kann spezielle Tage \(wie Feiertage\) durch das Datum fett formatieren angeben.  
  
 Weitere Informationen zum Verwenden des Monatskalender\-Steuerelements, finden Sie unter [Verwenden CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CMonthCalCtrl`  
  
## Anforderungen  
 **Header:**  afxdtctl.h  
  
## Siehe auch  
 [MFC Sampling CMNCTRL1](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl Class](../../mfc/reference/cdatetimectrl-class.md)