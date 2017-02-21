---
title: "CMFCShellListCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCShellListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellListCtrl class"
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCShellListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse stellt `CMFCShellListCtrl` Windows\-Listensteuerelementfunktionalität und erweitert sie, indem sie die Möglichkeit enthält, eine Liste von Shellelementen anzuzeigen.  
  
## Syntax  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](../Topic/CMFCShellListCtrl::DisplayFolder.md)|Zeigt eine Liste von Elementen an, die in einem angegebenen Ordner enthalten sein.|  
|[CMFCShellListCtrl::DisplayParentFolder](../Topic/CMFCShellListCtrl::DisplayParentFolder.md)|Zeigt eine Liste von Elementen an, die im Ordner enthalten sein, der das übergeordnete Element des aktuell angezeigten Ordners ist.|  
|[CMFCShellListCtrl::EnableShellContextMenu](../Topic/CMFCShellListCtrl::EnableShellContextMenu.md)|Aktiviert oder deaktiviert das Kontextmenü.|  
|[CMFCShellListCtrl::GetCurrentFolder](../Topic/CMFCShellListCtrl::GetCurrentFolder.md)|Ruft den Pfad des aktuellen Ordners ab.|  
|[CMFCShellListCtrl::GetCurrentFolderName](../Topic/CMFCShellListCtrl::GetCurrentFolderName.md)|Ruft den Namen des aktuellen Ordners ab.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](../Topic/CMFCShellListCtrl::GetCurrentItemIdList.md)|Gibt das PIDL des aktuellen Listensteuerelementelements zurück.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](../Topic/CMFCShellListCtrl::GetCurrentShellFolder.md)|Gibt einen Zeiger auf das aktuelle Shellordner zurück.|  
|[CMFCShellListCtrl::GetItemPath](../Topic/CMFCShellListCtrl::GetItemPath.md)|Gibt den Textpfad eines Elements zurück.|  
|[CMFCShellListCtrl::GetItemTypes](../Topic/CMFCShellListCtrl::GetItemTypes.md)|EINGABETASTE\-Shellelementtypen, die durch das Listensteuerelement angezeigt werden.|  
|[CMFCShellListCtrl::IsDesktop](../Topic/CMFCShellListCtrl::IsDesktop.md)|Überprüft, ob der aktuell ausgewählten Ordner der Tischplattenordner ist.|  
|[CMFCShellListCtrl::OnCompareItems](../Topic/CMFCShellListCtrl::OnCompareItems.md)|Das Framework ruft diese Methode auf, wenn zwei Elemente verglichen werden.  \(Überschreibungen [CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md).\)|  
|[CMFCShellListCtrl::OnFormatFileDate](../Topic/CMFCShellListCtrl::OnFormatFileDate.md)|Aufgerufen, wenn das Framework beim abrufen, das durch das Listensteuerelement angezeigt wird.|  
|[CMFCShellListCtrl::OnFormatFileSize](../Topic/CMFCShellListCtrl::OnFormatFileSize.md)|Aufgerufen, wenn das Framework die Dateigröße eines Listensteuerelements konvertiert.|  
|[CMFCShellListCtrl::OnGetItemIcon](../Topic/CMFCShellListCtrl::OnGetItemIcon.md)|Aufgerufen, wenn das Framework das Symbol eines Listensteuerelementelements abruft.|  
|[CMFCShellListCtrl::OnGetItemText](../Topic/CMFCShellListCtrl::OnGetItemText.md)|Aufgerufen, wenn das Framework den Text eines Listensteuerelementelements konvertiert.|  
|[CMFCShellListCtrl::OnSetColumns](../Topic/CMFCShellListCtrl::OnSetColumns.md)|Aufgerufen vom Framework, wenn die Namen der Spalten festgelegt wird.|  
|[CMFCShellListCtrl::Refresh](../Topic/CMFCShellListCtrl::Refresh.md)|Aktualisierungen und streicht das Listensteuerelement neu.|  
|[CMFCShellListCtrl::SetItemTypes](../Topic/CMFCShellListCtrl::SetItemTypes.md)|Legt den Typ von Elementen ab, die durch das Listensteuerelement angezeigt werden.|  
  
## Hinweise  
 Die `CMFCShellListCtrl`\-Klasse erweitert die Funktionalität [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md), indem sie das Programm ermöglicht, Windows\-Shell\-Elemente aufzulisten.  Das Anzeigeformat, das verwendet wird, ist wie das einer Listenansicht für ein Explorer\-Fenster.  
  
 Ein Objekt [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) kann mit einem `CMFCShellListCtrl`\-Objekt zugeordnet werden, um ein vollständiges Explorer\-Fenster zu erstellen.  Anschließend wird das Auswählen eines Elements in `CMFCShellTreeCtrl``CMFCShellListCtrl`\-Objekt, das den Inhalt des ausgewählten Elements aufzulisten.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt der Klasse `CMFCShellListCtrl` erstellt und wie der übergeordneten Ordner des aktuell angezeigten Ordner angezeigt wird.  Dieser Codeausschnitt ist Teil [Explorer\-Beispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_Explorer#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_Explorer#1)]  
[!CODE [NVC_MFC_Explorer#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_Explorer#2)]  
[!CODE [NVC_MFC_Explorer#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_Explorer#3)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)  
  
## Anforderungen  
 **Header:** afxshelllistCtrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)