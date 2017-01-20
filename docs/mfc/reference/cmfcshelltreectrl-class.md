---
title: "CMFCShellTreeCtrl Class"
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
  - "CMFCShellTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellTreeCtrl class"
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
caps.latest.revision: 30
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCShellTreeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCShellTreeCtrl`\-Klasse erweitert [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)\-Funktionen, indem eine Hierarchie von Shellelementen anzeigt.  
  
## Syntax  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](../Topic/CMFCShellTreeCtrl::EnableShellContextMenu.md)|Aktiviert oder deaktiviert das Kontextmenü.|  
|[CMFCShellTreeCtrl::GetFlags](../Topic/CMFCShellTreeCtrl::GetFlags.md)|Gibt eine Kombination von Flags zurück, die auf [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066) übergeben werden.|  
|[CMFCShellTreeCtrl::GetItemPath](../Topic/CMFCShellTreeCtrl::GetItemPath.md)|Ruft den Pfad zu einem Element ab.|  
|[CMFCShellTreeCtrl::GetRelatedList](../Topic/CMFCShellTreeCtrl::GetRelatedList.md)|Gibt einen Zeiger auf [CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md)\-Objekt zurück, das zusammen mit diesem `CMFCShellTreeCtrl`\-Objekt verwendet wird, um ein Ähnliches Explorer Fenster zu erstellen.|  
|[CMFCShellTreeCtrl::OnChildNotify](../Topic/CMFCShellTreeCtrl::OnChildNotify.md)|Diese Memberfunktion wird durch das übergeordnete Fenster dieses Fensters aufgerufen, wenn eine Benachrichtigung empfängt, die auf dieses Fenster gilt.  \(Überschreibungen [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md).\)|  
|[CMFCShellTreeCtrl::OnGetItemIcon](../Topic/CMFCShellTreeCtrl::OnGetItemIcon.md)||  
|[CMFCShellTreeCtrl::OnGetItemText](../Topic/CMFCShellTreeCtrl::OnGetItemText.md)||  
|[CMFCShellTreeCtrl::Refresh](../Topic/CMFCShellTreeCtrl::Refresh.md)|Aktualisierungen und streicht das aktuelle `CMFCShellTreeCtrl`\-Objekt neu.|  
|[CMFCShellTreeCtrl::SelectPath](../Topic/CMFCShellTreeCtrl::SelectPath.md)|Wählt das entsprechende Strukturansicht\-Steuerelement\-Element auf Grundlage eines angegebenen PIDL\- oder Zeichenfolgenpfad aus.|  
|[CMFCShellTreeCtrl::SetFlags](../Topic/CMFCShellTreeCtrl::SetFlags.md)|Satzflags, um das Strukturkontexts zu filtern \(ähnlich den Flags wird von `IShellFolder::EnumObjects`\).|  
|[CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md)|Legt eine Beziehung zwischen dem aktuellen `CMFCShellTreeCtrl`\-Objekt und einem Objekt `CMFCShellListCtrl` fest.|  
  
## Hinweise  
 Diese Klasse erweitert die `CTreeCtrl`\-Klasse, indem sie das Programm ermöglicht, Windows\-Shell\-Elemente in der Struktur einzuschließen.  Diese Klasse kann mit einem `CMFCShellListCtrl`\-Objekt zugeordnet werden, um ein vollständiges Explorer\-Fenster zu erstellen.  Anschließend wird das Auswählen eines Elements in der Struktur eine Liste von Windows\-Shell\-Elementen in der zugeordneten Liste an.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)  
  
## Anforderungen  
 **Header:** afxshelltreeCtrl.h  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt der Klasse `CMFCShellTreeCtrl` erstellt.  Dieser Codeausschnitt ist Teil [Explorer\-Beispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_Explorer#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_Explorer#4)]  
[!CODE [NVC_MFC_Explorer#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_Explorer#5)]  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md)