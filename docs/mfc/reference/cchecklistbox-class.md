---
title: "CCheckListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCheckListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCheckListBox class"
  - "checklist boxes"
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CCheckListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Windows\-Kontrolllistenfelds bereit.  
  
## Syntax  
  
```  
  
class CCheckListBox : public CListBox  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCheckListBox::CCheckListBox](../Topic/CCheckListBox::CCheckListBox.md)|Erstellt ein `CCheckListBox`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCheckListBox::Create](../Topic/CCheckListBox::Create.md)|Stellt das Windows\-Kontrolllistenfeld erstellt und fügt es an den `CCheckListBox`\-Objekt.|  
|[CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md)|Aufgerufen vom \- Framework ausgelöst, wenn ein visueller Aspekt eines Ownerdrawnlistenfelds ändert.|  
|[CCheckListBox::Enable](../Topic/CCheckListBox::Enable.md)|Aktiviert oder deaktiviert Kontrolllistenfeldelement ein.|  
|[CCheckListBox::GetCheck](../Topic/CCheckListBox::GetCheck.md)|Ruft den Zustand des Kontrollkästchens eines Elements ab.|  
|[CCheckListBox::GetCheckStyle](../Topic/CCheckListBox::GetCheckStyle.md)|Ruft das Format der Kontrollkästchen des Steuerelements ab.|  
|[CCheckListBox::IsEnabled](../Topic/CCheckListBox::IsEnabled.md)|Bestimmt, ob ein Element aktiviert ist.|  
|[CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md)|Aufgerufen vom \- Framework ausgelöst, wenn ein Listenfeld mit einem Ownerdrawnformat erstellt wird.|  
|[CCheckListBox::OnGetCheckPosition](../Topic/CCheckListBox::OnGetCheckPosition.md)|Aufgerufen durch das Framework, um die Position des Kontrollkästchens eines Elements abzurufen.|  
|[CCheckListBox::SetCheck](../Topic/CCheckListBox::SetCheck.md)|Legt den Status des Kontrollkästchens eines Elements fest.|  
|[CCheckListBox::SetCheckStyle](../Topic/CCheckListBox::SetCheckStyle.md)|Legt das Format der Kontrollkästchen des Steuerelements fest.|  
  
## Hinweise  
 Ein "Kontrolllistenfeld" zeigt eine Liste von Elementen, wie Dateinamen an.  Jedes Element in der Liste weist ein Kontrollkästchen daneben, dass der Benutzer überprüfen oder löschen kann.  
  
 `CCheckListBox` ist nur für Ownerdrawn\-Steuerelemente, da die Liste mehrere Textzeichenfolgen enthält.  Im einfachsten Fall enthält ein Kontrolllistenfeld Textzeichenfolgen und Kontrollkästchen, aber Sie müssen nicht, um Text zu haben vorhanden.  Beispielsweise können Sie eine Liste von kleinen Bitmap mit einem Kontrollkästchen neben jedem Element haben.  
  
 Um ein eigenes Kontrolllistenfeld zu erstellen, müssen Sie die eigene Klasse von `CCheckListBox` berechnen.  Um eine eigene Klasse ableiten, schreiben Sie einen Konstruktor für die abgeleitete Klasse, und rufen Sie dann **Create** auf.  
  
 Wenn Sie Windows\-Benachrichtigungsmeldungen bearbeiten möchten, die durch ein Listenfeld zu seinem übergeordneten Element gesendet werden \(normalerweise eine Klasse wird von abgeleitet [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)\), fügen Sie eine Meldungszuordnungseintrags\- und Meldungshandlermemberfunktion der übergeordneten Klasse für jede Meldung hinzu.  
  
 Jeder Eintrag in der Meldungszuordnung weist folgende Form auf:  
  
 **ON\_** Benachrichtigung **\(**`id`, `memberFxn`**\)**  
  
 wobei `id` die ID des untergeordneten Fensters sendenden des Steuerelements, ist die Benachrichtigungen und `memberFxn` der Name der übergeordneten Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu bearbeiten.  
  
 Der Funktionsprototyp des übergeordneten Elements ist, wie folgt:  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 Es gibt nur einen Eintrag in der Meldungszuordnung, der speziell **CCheckListBox**  betrifft \(aber finden Sie auch die Meldungszuordnungseinträge für [CListBox](../../mfc/reference/clistbox-class.md)\):  
  
-   **ON\_CLBN\_CHKCHANGE** hat der Benutzer den Status des Kontrollkästchens eines Elements geändert.  
  
 Wenn das Kontrolllistenfeld ein Standard Kontrolllistenfeld \(eine Liste von Zeichenfolgen mit den Standard\-groß Kontrollkästchen auf der linken Seite jedes\) ist, können Sie die Standardeinstellung [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) verwenden, um das Kontrolllistenfeld zu zeichnen.  Andernfalls müssen Sie die [CListBox::CompareItem](../Topic/CListBox::CompareItem.md)\-Funktion und die [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) und [CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md)\-Funktionen überschreiben.  
  
 Sie können ein Kontrolllistenfeld entweder einer Dialogfeldvorlage oder direkt im Code erstellen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel TSTCON](../../top/visual-cpp-samples.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)