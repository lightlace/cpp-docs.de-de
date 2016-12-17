---
title: "Einstellen des Tagesstatus f&#252;r ein Monatskalender-Steuerelement"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MCN_GETDAYSTATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonthCalCtrl-Klasse, Einstellen der Tagesstatusinfo"
  - "MCN_GETDAYSTATE-Benachrichtigung"
  - "Monatskalender-Steuerelement, Tagesstatusinfo"
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Einstellen des Tagesstatus f&#252;r ein Monatskalender-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eines der Attribute eines Monatskalender\-Steuerelements ist die Möglichkeit, die Informationen speichern, als der Tagszustand des Steuerelements, für jeden Tag des Monats.  Diese Informationen werden verwendet, um bestimmte Datumsangaben für den aktuell angezeigten Monat hervorzuheben.  
  
> [!NOTE]
>  Das `CMonthCalCtrl`\-Objekt muss das **MCS\_DAYSTATE** Formats, um von Tagszustandsinformationen anzuzeigen.  
  
 Tagszustandsinformationen werden als 32\-Bit\-Datentyp, **MONTHDAYSTATE** ausgedrückt.  Jedes Bit in einem **MONTHDAYSTATE** Bitfeld \(1 bis 31\) stellt den Zustand eines Tages in einem Monat dar.  Wenn ein Bit aktiviert ist, wird der entsprechende Tag fett formatiert; Andernfalls wird diese ohne Betonung angezeigt.  
  
 Es gibt zwei Methoden für das Festlegen des Tagszustandes des Monatskalender\-Steuerelements: explizit mit einem Aufruf von [CMonthCalCtrl::SetDayState](../Topic/CMonthCalCtrl::SetDayState.md) oder durch das Behandeln der **MCN\_GETDAYSTATE** Benachrichtigung.  
  
## Behandeln der MCN\_GETDAYSTATE\-Benachrichtigungsmeldung  
 Die **MCN\_GETDAYSTATE** Meldung wird vom Steuerelement gesendet, um zu bestimmen, z die Tage innerhalb der sichtbaren Monate angezeigt werden sollen.  
  
> [!NOTE]
>  Da das Steuerelement das vorherige zwischenspeichert und folgenden Monaten, in Bezug auf den sichtbaren Monat, erhalten Sie diese Benachrichtigung, wenn ein neuer Monat ausgewählt ist.  
  
 Für diese Meldung um ordnungsgemäß zu bearbeiten, müssen Sie bestimmen wie viele Monate Tagszustandsinformationen angefordert werden, initialisieren ein Array **MONTHDAYSTATE**\-Strukturen mit den richtigen Werten initialisieren und verknüpften Strukturmember mit den neuen Informationen.  In der folgenden Prozedur, die erforderlichen Schritte einzeln angezeigt, ist, dass Sie ein `CMonthCalCtrl`\-Objekt vorhanden ist, das `m_monthcal` und ein Array **MONTHDAYSTATE**\-Objekte aufgerufen wird, `mdState`.  
  
#### Um die MCN\_GETDAYSTATE\-Benachrichtigungsmeldung bearbeiten  
  
1.  Verwenden des Eigenschaftenfensters fügen Sie einem Benachrichtigungshandler für die **MCN\_GETDAYSTATE** Meldung dem `m_monthcal`\-Objekt hinzu \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  
  
2.  Im Text des Handlers, fügen Sie den folgenden Code hinzu:  
  
     [!CODE [NVC_MFCControlLadenDialog#26](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#26)]  
  
     Das Beispiel konvertiert den `pNMHDR` Zeiger in den richtigen Typ, dann bestimmt, wie viele Monate von Informationen angefordert werden \(`pDayState->cDayState`\).  Für jeden Monat wird das aktuelle Bitfeld \(`pDayState->prgDayState[i]`\) auf Null initialisiert und dann die erforderlichen Datumsangaben wird festgelegt \(in diesem Fall, also 15. jedes Monats\).  
  
## Siehe auch  
 [Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)