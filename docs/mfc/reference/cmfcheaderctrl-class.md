---
title: "CMFCHeaderCtrl Class"
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
  - "CMFCHeaderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCHeaderCtrl class"
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
caps.latest.revision: 29
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCHeaderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCHeaderCtrl`\-Klasse unterstützt mehrere Spalten der Sortierung in einem Header\-Steuerelement.  
  
## Syntax  
  
```  
class CMFCHeaderCtrl : public CHeaderCtrl  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCHeaderCtrl::CMFCHeaderCtrl](../Topic/CMFCHeaderCtrl::CMFCHeaderCtrl.md)|Erstellt ein `CMFCHeaderCtrl`\-Objekt.|  
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCHeaderCtrl::EnableMultipleSort](../Topic/CMFCHeaderCtrl::EnableMultipleSort.md)|Aktiviert oder deaktiviert *mehrere Spaltensortierungsmodus* für das aktuelle Header\-Steuerelement.|  
|[CMFCHeaderCtrl::GetColumnState](../Topic/CMFCHeaderCtrl::GetColumnState.md)|Gibt, an, ob eine Spalte nicht sortiert wird, oder wird in aufsteigender oder absteigender Reihenfolge sortiert.|  
|[CMFCHeaderCtrl::GetSortColumn](../Topic/CMFCHeaderCtrl::GetSortColumn.md)|Ruft den nullbasierten Index der ersten sortierten Spalte im Header\-Steuerelement ab.|  
|`CMFCHeaderCtrl::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCHeaderCtrl::IsAscending](../Topic/CMFCHeaderCtrl::IsAscending.md)|Gibt an, ob eine Spalte im Header\-Steuerelement in aufsteigender Reihenfolge sortiert wird.|  
|[CMFCHeaderCtrl::IsDialogControl](../Topic/CMFCHeaderCtrl::IsDialogControl.md)|Gibt an, ob das übergeordnete Fenster des aktuellen Zeilen\- ein Dialogfeld ist.|  
|[CMFCHeaderCtrl::IsMultipleSort](../Topic/CMFCHeaderCtrl::IsMultipleSort.md)|Gibt an, ob das aktuelle Header\-Steuerelement *in mehreren Spaltensortierungsmodus* ist.|  
|[CMFCHeaderCtrl::RemoveSortColumn](../Topic/CMFCHeaderCtrl::RemoveSortColumn.md)|Entfernt die angegebene Spalte aus der Liste der Sortierungsspalten.|  
|[CMFCHeaderCtrl::SetSortColumn](../Topic/CMFCHeaderCtrl::SetSortColumn.md)|Legt die Sortierreihenfolge einer angegebenen Spalte in einem Header\-Steuerelement fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCHeaderCtrl::OnDrawItem](../Topic/CMFCHeaderCtrl::OnDrawItem.md)|Aufgerufen vom Framework, um eine Header\-Steuerelement\-Spalte zu zeichnen.|  
|[CMFCHeaderCtrl::OnDrawSortArrow](../Topic/CMFCHeaderCtrl::OnDrawSortArrow.md)|Aufgerufen vom Framework, um den Sortierungspfeil zu zeichnen.|  
|[CMFCHeaderCtrl::OnFillBackground](../Topic/CMFCHeaderCtrl::OnFillBackground.md)|Aufgerufen vom Framework, um den Hintergrund einer Header\-Steuerelement\-Spalte auszufüllen.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt der Klasse `CMFCHeaderCtrl` erstellt und wie *mehrere Spaltensortierungsmodus* für das aktuelle Header\-Steuerelement aktiviert.  
  
 [!CODE [NVC_MFC_RibbonApp#24](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#24)]  
  
## Hinweise  
 Die `CMFCHeaderCtrl`\-Klasse zeichnet einen Sortierungspfeil auf einer Header\-Steuerelement\-Spalte, um anzugeben, dass die Spalte sortiert wird.  Verwenden Sie *mehrere Spaltensortierungsmodus*, wenn ein Satz von Spalten im übergeordneten Listensteuerelement \([CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)\) gleichzeitig sortiert werden kann.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [Steuerelement\-MFC\-Klassen](../../mfc/reference/cheaderctrl-class.md)  
  
 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)  
  
## Anforderungen  
 **Header:** afxheaderctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)