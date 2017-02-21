---
title: "CMFCListCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCListCtrl class"
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCListCtrl`\-Klasse erweitert die Funktionalität von [CListCtrl Class](../../mfc/reference/clistctrl-class.md)\-Klasse, indem sie die erweiterte Header\-Steuerelement\-Funktionalität [CMFCHeaderCtrl Class](../../mfc/reference/cmfcheaderctrl-class.md) unterstützt.  
  
## Syntax  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](../Topic/CMFCListCtrl::EnableMarkSortedColumn.md)|Aktiviert die Möglichkeit, eine sortierte Spalte mit einer anderen Hintergrundfarbe zu markieren.|  
|[CMFCListCtrl::EnableMultipleSort](../Topic/CMFCListCtrl::EnableMultipleSort.md)|Aktiviert mehrere Sortiermodus.|  
|[CMFCListCtrl::GetHeaderCtrl](../Topic/CMFCListCtrl::GetHeaderCtrl.md)|Gibt einen Verweis auf den unterstrichenen Header\-Steuerelement zurück.|  
|[CMFCListCtrl::IsMultipleSort](../Topic/CMFCListCtrl::IsMultipleSort.md)|Überprüft, ob das Listensteuerelement in mehreren Sortiermodus ist.|  
|[CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md)|Aufgerufen vom Framework, wenn sich zwei Listensteuerelementelemente vergleichen muss.|  
|[CMFCListCtrl::OnGetCellBkColor](../Topic/CMFCListCtrl::OnGetCellBkColor.md)|Aufgerufen vom Framework, wenn die Hintergrundfarbe einer einzelnen Zelle bestimmen muss.|  
|[CMFCListCtrl::OnGetCellFont](../Topic/CMFCListCtrl::OnGetCellFont.md)|Aufgerufen vom Framework, wenn abrufen muss die Schriftart für die Zelle, die gezeichnet wird.|  
|[CMFCListCtrl::OnGetCellTextColor](../Topic/CMFCListCtrl::OnGetCellTextColor.md)|Aufgerufen vom Framework, wenn die Textfarbe einer einzelnen Zelle bestimmen muss.|  
|[CMFCListCtrl::RemoveSortColumn](../Topic/CMFCListCtrl::RemoveSortColumn.md)|Entfernt eine Sortierungsspalte aus der Liste der sortierten Spalten.|  
|[CMFCListCtrl::SetSortColumn](../Topic/CMFCListCtrl::SetSortColumn.md)|Legt den aktuellen sortierte Spalte und die Sortierreihenfolge fest.|  
|[CMFCListCtrl::Sort](../Topic/CMFCListCtrl::Sort.md)|Sortiert das Listensteuerelement.|  
  
## Hinweise  
 `CMFCListCtrl` bietet zwei Erweiterungen [CListCtrl Class](../../mfc/reference/clistctrl-class.md)\-Klasse an.  Zunächst ist dies an, dass das Sortieren eine verfügbare Option ist, indem automatisch ein Sortierungspfeil im Header zeichnet.  Zweitens unterstützt sie Datensortierung für mehrere Spalten gleichzeitig.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCListCtrl` verwendet.  Im Beispiel wird gezeigt, wie ein Listensteuerelement, Einfügungsspalten, Einfügungselemente, legen Sie den Text eines Elements und legen Sie die Schriftart des Listensteuerelements erstellt.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#25](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#25)]  
[!CODE [NVC_MFC_VisualStudioDemo#26](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#26)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## Anforderungen  
 **Header:** afxlistctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)