---
title: "CHeaderCtrl Class"
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
  - "CHeaderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeaderCtrl class"
  - "header controls, CHeaderCtrl class"
  - "Windows common controls [C++], CHeaderCtrl"
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
caps.latest.revision: 24
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CHeaderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen Header\-Steuerelements Windows bereit.  
  
## Syntax  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](../Topic/CHeaderCtrl::CHeaderCtrl.md)|Erstellt ein `CHeaderCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](../Topic/CHeaderCtrl::ClearAllFilters.md)|Löscht alle Filter für ein Header\-Steuerelement.|  
|[CHeaderCtrl::ClearFilter](../Topic/CHeaderCtrl::ClearFilter.md)|Löscht den Filter für ein Header\-Steuerelement.|  
|[CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md)|Erstellt ein und fügt es Header\-Steuerelement zu einem `CHeaderCtrl`\-Objekt.|  
|[CHeaderCtrl::CreateDragImage](../Topic/CHeaderCtrl::CreateDragImage.md)|Erstellt eine transparente Version des Bilds eines Elements innerhalb eines Header\-Steuerelements.|  
|[CHeaderCtrl::CreateEx](../Topic/CHeaderCtrl::CreateEx.md)|Erstellt ein Header\-Steuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CListCtrl`\-Objekt.|  
|[CHeaderCtrl::DeleteItem](../Topic/CHeaderCtrl::DeleteItem.md)|Löscht ein Element aus einem Header\-Steuerelement.|  
|[CHeaderCtrl::DrawItem](../Topic/CHeaderCtrl::DrawItem.md)|Zeichnet das angegebene Element eines Header\-Steuerelements.|  
|[CHeaderCtrl::EditFilter](../Topic/CHeaderCtrl::EditFilter.md)|beginnt, die den angegebenen Filter eines Header\-Steuerelements bearbeiten.|  
|[CHeaderCtrl::GetBitmapMargin](../Topic/CHeaderCtrl::GetBitmapMargin.md)|Ruft die Breite des Rands einer Bitmap in einem Header\-Steuerelement ab.|  
|[CHeaderCtrl::GetFocusedItem](../Topic/CHeaderCtrl::GetFocusedItem.md)|Ruft den Bezeichner des Elements im aktuellen Header\-Steuerelement ab, das den Fokus besitzt.|  
|[CHeaderCtrl::GetImageList](../Topic/CHeaderCtrl::GetImageList.md)|Ruft das Handle einer Bildliste ab, die zum Zeichnen von Headerelementen in einem Header\-Steuerelement verwendet wird.|  
|[CHeaderCtrl::GetItem](../Topic/CHeaderCtrl::GetItem.md)|Ruft Informationen über ein Element in einem Header\-Steuerelement ab.|  
|[CHeaderCtrl::GetItemCount](../Topic/CHeaderCtrl::GetItemCount.md)|Ruft die Anzahl der Elemente in einem Header\-Steuerelement ab.|  
|[CHeaderCtrl::GetItemDropDownRect](../Topic/CHeaderCtrl::GetItemDropDownRect.md)|Ruft die Informationen des umgebenden Rechtecks für die angegebene Dropdownschaltfläche in einem Header\-Steuerelement ab.|  
|[CHeaderCtrl::GetItemRect](../Topic/CHeaderCtrl::GetItemRect.md)|Ruft das umschließende Rechteck für ein angegebenes Element in einem Header\-Steuerelement ab.|  
|[CHeaderCtrl::GetOrderArray](../Topic/CHeaderCtrl::GetOrderArray.md)|Ruft das Reihenfolge von links nach rechts von Elementen in einem Header\-Steuerelement ab.|  
|[CHeaderCtrl::GetOverflowRect](../Topic/CHeaderCtrl::GetOverflowRect.md)|Ruft das umschließende Rechteck der Überlaufschaltfläche für das aktuelle Header\-Steuerelement ab.|  
|[CHeaderCtrl::HitTest](../Topic/CHeaderCtrl::HitTest.md)|Bestimmt, HeaderItem ggf. an einem angegebenen Punkt befindet.|  
|[CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md)|Fügt ein neues Element in ein Header\-Steuerelement ein.|  
|[CHeaderCtrl::Layout](../Topic/CHeaderCtrl::Layout.md)|Ruft die Größe und Position eines Header\-Steuerelements innerhalb eines angegebenen Rechtecks ab.|  
|[CHeaderCtrl::OrderToIndex](../Topic/CHeaderCtrl::OrderToIndex.md)|Ruft den Indexwert für ein Element auf Grundlage der Reihenfolge im Header\-Steuerelement ab.|  
|[CHeaderCtrl::SetBitmapMargin](../Topic/CHeaderCtrl::SetBitmapMargin.md)|Gibt die Breite des Rands einer Bitmap in einem Header\-Steuerelement fest.|  
|[CHeaderCtrl::SetFilterChangeTimeout](../Topic/CHeaderCtrl::SetFilterChangeTimeout.md)|Legt das Timeoutintervall zwischen der Zeit fest, die eine Änderung in den Filterattributen und in der Aufgabe einer `HDN_FILTERCHANGE` Benachrichtigung stattfindet.|  
|[CHeaderCtrl::SetFocusedItem](../Topic/CHeaderCtrl::SetFocusedItem.md)|Legt den Fokus zu einem angegebenen Headerelement im aktuellen Header\-Steuerelement fest.|  
|[CHeaderCtrl::SetHotDivider](../Topic/CHeaderCtrl::SetHotDivider.md)|Ändert den Unterteiler zwischen Headerelementen, um einen manuellen Drag & Drop eines Headerelements anzugeben.|  
|[CHeaderCtrl::SetImageList](../Topic/CHeaderCtrl::SetImageList.md)|Weist eine Bildliste zu einem Header\-Steuerelement zu.|  
|[CHeaderCtrl::SetItem](../Topic/CHeaderCtrl::SetItem.md)|Legt die Attribute des angegebenen Elements in einem Header\-Steuerelement fest.|  
|[CHeaderCtrl::SetOrderArray](../Topic/CHeaderCtrl::SetOrderArray.md)|Legt die Reihenfolge von links nach rechts von Elementen in einem Header\-Steuerelement fest.|  
  
## Hinweise  
 Ein Header\-Steuerelement ist ein Fenster, das normalerweise über einen Satz von Spalten von Text oder Nummern positioniert wird.  Sie enthält einen Namen für jede Spalte, und es kann in Bereiche unterteilt werden.  Der Benutzer kann die Unterteiler ziehen, die die Teile trennen, um die Breite jeder Spalte festzulegen.  Eine Abbildung eines Zeilen\-, finden Sie unter [Header\-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 Dieses Steuerelement \(und daher die `CHeaderCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Die Funktionalität, die für Windows 95\/Internet Explorer 4.0 allgemeine Steuerelemente hinzugefügt wird, enthält Folgendes:  
  
-   Benutzerdefinierte Reihenfolge des Headerelements.  
  
-   Headerelement\-Drag & Drop, für das Neu anordnen von Headerelementen.  Verwenden Sie das `HDS_DRAGDROP` Format, wenn Sie das `CHeaderCtrl`\-Objekt erstellen.  
  
-   Headerspaltentext ständig sichtbar während der Spaltengrößenanpassung.  Verwenden Sie das `HDS_FULLDRAG` Format, wenn Sie ein `CHeaderCtrl`\-Objekt erstellen.  
  
-   Headerhottracking, das HeaderItem hervorhebt, wenn der Mauszeiger darauf zeigt.  Verwenden Sie das `HDS_HOTTRACK` Format, wenn Sie das `CHeaderCtrl`\-Objekt erstellen.  
  
-   Bildlistenunterstützung.  Headerelemente können die Bilder enthalten, die in einem `CImageList`\-Objekt gespeichert werden oder Text.  
  
 Weitere Informationen zur Verwendung von `CHeaderCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden Steuerelement\-MFC\-Klassen](../../mfc/using-cheaderctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## Anforderungen  
 **Header:** afxcmn.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CTabCtrl Class](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)