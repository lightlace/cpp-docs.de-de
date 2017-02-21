---
title: "CDateTimeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDateTimeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl class"
  - "date-picking functionality"
  - "DateTimePicker control [MFC]"
  - "DateTimePicker control [MFC], CDateTimeCtrl class"
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDateTimeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt die Funktionalität eines Steuerelements für die Datums\- und Zeitauswahl.  
  
## Syntax  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](../Topic/CDateTimeCtrl::CDateTimeCtrl.md)|Erstellt ein `CDateTimeCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](../Topic/CDateTimeCtrl::CloseMonthCal.md)|Schließt das aktuelle Datum und das Steuerelement für die Zeitauswahl.|  
|[CDateTimeCtrl::Create](../Topic/CDateTimeCtrl::Create.md)|Erstellt das Steuerelement für die Datums\- und Zeitauswahl und fügt es dem `CDateTimeCtrl`\-Objekt.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](../Topic/CDateTimeCtrl::GetDateTimePickerInfo.md)|Ruft Informationen über das aktuelle Datum und das Steuerelement für die Zeitauswahl ab.|  
|[CDateTimeCtrl::GetIdealSize](../Topic/CDateTimeCtrl::GetIdealSize.md)|Gibt die ideale Größe des Steuerelements für die Datums\- und Zeitauswahl zurück, das erforderlich ist, um das aktuelle Datum oder Uhrzeit anzuzeigen.|  
|[CDateTimeCtrl::GetMonthCalColor](../Topic/CDateTimeCtrl::GetMonthCalColor.md)|Ruft die Farbe für einen bestimmten Teil des Monatskalenders im Steuerelement für die Datums\- und Zeitauswahl ab.|  
|[CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)|Ruft das `CMonthCalCtrl`\-Objekt ab, das dem Steuerelement für die Datums\- und Zeitauswahl zugeordnet ist.|  
|[CDateTimeCtrl::GetMonthCalFont](../Topic/CDateTimeCtrl::GetMonthCalFont.md)|Ruft die Schriftart ab, die derzeit durch das untergeordnete Monatskalender\-Steuerelement des Steuerelements für die Datums\- und Zeitauswahl verwendet wird.|  
|[CDateTimeCtrl::GetMonthCalStyle](../Topic/CDateTimeCtrl::GetMonthCalStyle.md)|Ruft das Format des aktuellen Datums und des Steuerelements für die Zeitauswahl ab.|  
|[CDateTimeCtrl::GetRange](../Topic/CDateTimeCtrl::GetRange.md)|Ruft das aktuelle Mindest\- und den Höchstwert ab, das Systemzeiten für ein Steuerelement für die Datums\- und Zeitauswahl zulässig ist.|  
|[CDateTimeCtrl::GetTime](../Topic/CDateTimeCtrl::GetTime.md)|Ruft die aktuell ausgewählte Zeit von einem Steuerelement für die Datums\- und Zeitauswahl ab und legt sie in eine angegebene `SYSTEMTIME`\-Struktur ein.|  
|[CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md)|Legt die Anzeige eines Steuerelements für die Datums\- und Zeitauswahl in Übereinstimmung mit einer angegebenen Formatzeichenfolge fest.|  
|[CDateTimeCtrl::SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md)|Legt die Farbe für einen bestimmten Teil des Monatskalenders innerhalb eines Steuerelements für die Datums\- und Zeitauswahl fest.|  
|[CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md)|Legt die Schriftart fest, die das untergeordnete Monatskalender\-Steuerelement des Steuerelements für die Datums\- und Zeitauswahl verwendet.|  
|[CDateTimeCtrl::SetMonthCalStyle](../Topic/CDateTimeCtrl::SetMonthCalStyle.md)|Legt das Format des aktuellen Datums und des Steuerelements für die Zeitauswahl fest.|  
|[CDateTimeCtrl::SetRange](../Topic/CDateTimeCtrl::SetRange.md)|Legt die minimalen und maximalen zulässigen Systemzeiten für ein Steuerelement für die Datums\- und Zeitauswahl fest.|  
|[CDateTimeCtrl::SetTime](../Topic/CDateTimeCtrl::SetTime.md)|Legt die Zeit in einem Steuerelement für die Datums\- und Zeitauswahl fest.|  
  
## Hinweise  
 Das Steuerelement für die Datums\- und Zeitauswahl \(DTP\-Steuerelement\) stellt eine einfache Schnittstelle, um Datums\- und Uhrzeitinformationen mit einem Benutzer auszutauschen.  Diese Schnittstelle enthält Felder, von denen jedes einen Teil der Datums\- und Uhrzeitinformationen enthält, die im Steuerelement gespeichert sind.  Der Benutzer kann Informationen ändern, die im \- Steuerelement gespeichert werden, indem der Inhalt der Zeichenfolge auf einem angegebenen Feld ändert.  Der Benutzer kann von Feld zu Feld mit der Maus oder der Tastatur wechseln.  
  
 Sie können das Steuerelement für die Datums\- und Zeitauswahl anpassen, indem Sie eine Vielzahl von Formaten auf das Objekt anwenden, wenn Sie sie erstellen.  Siehe [Steuerelement für die Datums\- und Zeitauswahl\-Formate](http://msdn.microsoft.com/library/windows/desktop/bb761728) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] weitere Informationen über die Stile, die für das Steuerelement für die Datums\- und Zeitauswahl spezifisch sind.  Sie können das Anzeigeformat des DTP\-Steuerelements mithilfe der Formatformate festlegen.  Diese Formatformate werden unter "Format formatiert" im Thema [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)][Steuerelement für die Datums\- und Zeitauswahl\-Formate](http://msdn.microsoft.com/library/windows/desktop/bb761728) beschrieben.  
  
 Das Steuerelement für die Datums\- und Zeitauswahl verwendet auch Benachrichtigungen und Rückrufe, die in [Verwenden CDateTimeCtrl](../../mfc/using-cdatetimectrl.md) beschrieben werden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## Anforderungen  
 **Header:**  afxdtctl.h  
  
## Siehe auch  
 [Das MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl Class](../../mfc/reference/cmonthcalctrl-class.md)