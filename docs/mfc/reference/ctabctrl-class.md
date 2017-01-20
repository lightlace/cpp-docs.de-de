---
title: "CTabCtrl Class"
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
  - "CTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl class"
  - "CTabCtrl class, Allgemeine Steuerelemente"
  - "Registerkarten-Steuerelemente"
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen Tab\-Steuerelements Windows bereit.  
  
## Syntax  
  
```  
class CTabCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](../Topic/CTabCtrl::CTabCtrl.md)|Erstellt ein `CTabCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](../Topic/CTabCtrl::AdjustRect.md)|Berechnet den Anzeigebereich einem Registersteuerelement, der ein Fensterrechteck angegeben ist oder berechnet das Fensterrechteck, das einem angegebenen Anzeigebereich entsprechen würde.|  
|[CTabCtrl::Create](../Topic/CTabCtrl::Create.md)|Erstellt ein Tab\-Steuerelement und fügt es einer Instanz eines Objekts `CTabCtrl` an.|  
|[CTabCtrl::CreateEx](../Topic/CTabCtrl::CreateEx.md)|Erstellt ein Tab\-Steuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es einer Instanz eines Objekts `CTabCtrl` an.|  
|[CTabCtrl::DeleteAllItems](../Topic/CTabCtrl::DeleteAllItems.md)|Entfernt alle Elemente aus einem Tab\-Steuerelement.|  
|[CTabCtrl::DeleteItem](../Topic/CTabCtrl::DeleteItem.md)|Entfernt ein Element aus einem Tab\-Steuerelement.|  
|[CTabCtrl::DeselectAll](../Topic/CTabCtrl::DeselectAll.md)|Fügt Elemente in einem Tab\-Steuerelement zurück und löscht alle, die gedrückt wurden.|  
|[CTabCtrl::DrawItem](../Topic/CTabCtrl::DrawItem.md)|Zeichnet ein angegebenes Element einem Registersteuerelement.|  
|[CTabCtrl::GetCurFocus](../Topic/CTabCtrl::GetCurFocus.md)|Ruft die Registerkarte mit dem aktuellen Fokus einem Registersteuerelement ab.|  
|[CTabCtrl::GetCurSel](../Topic/CTabCtrl::GetCurSel.md)|Bestimmt die aktuell ausgewählte Registerkarte in einem Tab\-Steuerelement.|  
|[CTabCtrl::GetExtendedStyle](../Topic/CTabCtrl::GetExtendedStyle.md)|Ruft die erweiterten Stile ab, die für das Tab\-Steuerelement derzeit verwendet werden.|  
|[CTabCtrl::GetImageList](../Topic/CTabCtrl::GetImageList.md)|Ruft die Bildliste ab, die mit einem Tab\-Steuerelement zugeordnet ist.|  
|[CTabCtrl::GetItem](../Topic/CTabCtrl::GetItem.md)|Ruft Informationen zu einer Registerkarte in einem Tab\-Steuerelement ab.|  
|[CTabCtrl::GetItemCount](../Topic/CTabCtrl::GetItemCount.md)|Ruft die Anzahl von Registerkarten im Tab\-Steuerelement ab.|  
|[CTabCtrl::GetItemRect](../Topic/CTabCtrl::GetItemRect.md)|Ruft das umschließende Rechteck für eine Registerkarte in einem Tab\-Steuerelement ab.|  
|[CTabCtrl::GetItemState](../Topic/CTabCtrl::GetItemState.md)|Ruft den Zustand des angegebenen Tab\-Steuerelements ab.|  
|[CTabCtrl::GetRowCount](../Topic/CTabCtrl::GetRowCount.md)|Ruft die aktuelle Anzahl von Zeilen von Registerkarten in einem Tab\-Steuerelement ab.|  
|[CTabCtrl::GetToolTips](../Topic/CTabCtrl::GetToolTips.md)|Ruft das Handle des ToolTip\-Steuerelements ab, das einem Tab\-Steuerelement zugeordnet ist.|  
|[CTabCtrl::HighlightItem](../Topic/CTabCtrl::HighlightItem.md)|Legt den Hervorhebungszustand eines Registerkartenelements fest.|  
|[CTabCtrl::HitTest](../Topic/CTabCtrl::HitTest.md)|Bestimmt, die mit der TAB\-TASTE, sofern in einer angegebenen Bildschirmposition ist.|  
|[CTabCtrl::InsertItem](../Topic/CTabCtrl::InsertItem.md)|Fügt eine neue Registerkarte in einem Tab\-Steuerelement ein.|  
|[CTabCtrl::RemoveImage](../Topic/CTabCtrl::RemoveImage.md)|Entfernt ein Bild aus der Bildliste einem Registersteuerelement.|  
|[CTabCtrl::SetCurFocus](../Topic/CTabCtrl::SetCurFocus.md)|Legt den Fokus zu einer angegebenen Registerkarte in einem Tab\-Steuerelement fest.|  
|[CTabCtrl::SetCurSel](../Topic/CTabCtrl::SetCurSel.md)|Wählt eine Registerkarte in einem Tab\-Steuerelement aus.|  
|[CTabCtrl::SetExtendedStyle](../Topic/CTabCtrl::SetExtendedStyle.md)|Legt die erweiterten Formate für ein Tab\-Steuerelement fest.|  
|[CTabCtrl::SetImageList](../Topic/CTabCtrl::SetImageList.md)|Weist eine Bildliste zu einem Tab\-Steuerelement zu.|  
|[CTabCtrl::SetItem](../Topic/CTabCtrl::SetItem.md)|Legt mehrere oder alle Attribute einer Registerkarte fest.|  
|[CTabCtrl::SetItemExtra](../Topic/CTabCtrl::SetItemExtra.md)|Legt die Anzahl von Bytes pro die Registerkarte fest, die für anwendungsdefinierte Daten in einem Tab\-Steuerelement reserviert ist.|  
|[CTabCtrl::SetItemSize](../Topic/CTabCtrl::SetItemSize.md)|Gibt die Breite und die Höhe des Elements fest.|  
|[CTabCtrl::SetItemState](../Topic/CTabCtrl::SetItemState.md)|Legt den Zustand des angegebenen Tab\-Steuerelements fest.|  
|[CTabCtrl::SetMinTabWidth](../Topic/CTabCtrl::SetMinTabWidth.md)|Legt die Mindestbreite von Elementen in einem Tab\-Steuerelement fest.|  
|[CTabCtrl::SetPadding](../Topic/CTabCtrl::SetPadding.md)|Legt den Platz \(Auffüllung\) das Symbol und die Bezeichnung jeder Registerkarte in einem Tab\-Steuerelement fest.|  
|[CTabCtrl::SetToolTips](../Topic/CTabCtrl::SetToolTips.md)|Weist ein QuickInfo\-Steuerelement zu einem Tab\-Steuerelement zu.|  
  
## Hinweise  
 Ein "Tab\-Steuerelement" ist den Trennblättern in einem Ordner oder den Bezeichnungen in einer Hängeregistratur.  Durch ein Tab\-Steuerelement können durch eine Anwendung mehrere Seiten für denselben Bereich in einem Fenster oder Dialogfeld definiert werden.  Jede Seite besteht aus einem Satz von Informationen oder Gruppe von Steuerelementen, die für die Anwendung angezeigt wird, wenn der Benutzer die entsprechende Registerkarte auswählt.  Ein besonderer Typ Tab\-Steuerelement zeigt Registerkarten an, die wie Schaltflächen aussehen.  Durch Klicken auf eine Schaltfläche sollte einen Befehl sofort ausführen, anstatt eine Seite anzuzeigen.  
  
 Dieses Steuerelement \(und daher die `CTabCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Weitere Informationen zur Verwendung von `CTabCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CTabCtrl](../../mfc/using-ctabctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl Class](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)