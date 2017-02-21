---
title: "CDockSite Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockSite class"
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CDockSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Stellt Funktionalität bereit, um Bereiche, die von [CPane Class](../../mfc/reference/cpane-class.md) abgeleitet sind, in Zeilengruppen anzuordnen.  
  
## Syntax  
  
```  
class CDockSite: public CBasePane  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDockSite::AddRow](../Topic/CDockSite::AddRow.md)||  
|[CDockSite::AdjustDockingLayout](../Topic/CDockSite::AdjustDockingLayout.md)|\(Überschreibt [CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md).\)|  
|[CDockSite::AdjustLayout](../Topic/CDockSite::AdjustLayout.md)|\(Überschreibt [CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md).\)|  
|[CDockSite::AlignDockSite](../Topic/CDockSite::AlignDockSite.md)||  
|[CDockSite::CalcFixedLayout](../Topic/CDockSite::CalcFixedLayout.md)|\(Überschreibt [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CDockSite::CanAcceptPane](../Topic/CDockSite::CanAcceptPane.md)|\(Überschreibt [CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md).\)|  
|[CDockSite::CreateEx](../Topic/CDockSite::CreateEx.md)|\(Überschreibt [CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md).\)|  
|[CDockSite::CreateRow](../Topic/CDockSite::CreateRow.md)||  
|[CDockSite::DockPane](../Topic/CDockSite::DockPane.md)|\(Überschreibt [CBasePane::DockPane](../Topic/CBasePane::DockPane.md).\)|  
|[CDockSite::DoesAllowDynInsertBefore](../Topic/CDockSite::DoesAllowDynInsertBefore.md)|\(Überschreibt [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CDockSite::FindRowIndex](../Topic/CDockSite::FindRowIndex.md)||  
|[CDockSite::FixupVirtualRects](../Topic/CDockSite::FixupVirtualRects.md)||  
|[CDockSite::GetDockSiteID](../Topic/CDockSite::GetDockSiteID.md)||  
|[CDockSite::GetDockSiteRowsList](../Topic/CDockSite::GetDockSiteRowsList.md)||  
|[CDockSite::IsAccessibilityCompatible](../Topic/CDockSite::IsAccessibilityCompatible.md)|\(Überschreibt `CBasePane::IsAccessibilityCompatible`.\)|  
|[CDockSite::IsDragMode](../Topic/CDockSite::IsDragMode.md)||  
|[CDockSite::IsLastRow](../Topic/CDockSite::IsLastRow.md)||  
|[CDockSite::IsRectWithinDockSite](../Topic/CDockSite::IsRectWithinDockSite.md)||  
|[CDockSite::IsResizable](../Topic/CDockSite::IsResizable.md)|\(Überschreibt [CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md).\)|  
|[CDockSite::MovePane](../Topic/CDockSite::MovePane.md)||  
|[CDockSite::OnInsertRow](../Topic/CDockSite::OnInsertRow.md)||  
|[CDockSite::OnRemoveRow](../Topic/CDockSite::OnRemoveRow.md)||  
|[CDockSite::OnResizeRow](../Topic/CDockSite::OnResizeRow.md)||  
|[CDockSite::OnSetWindowPos](../Topic/CDockSite::OnSetWindowPos.md)||  
|[CDockSite::OnShowRow](../Topic/CDockSite::OnShowRow.md)||  
|[CDockSite::OnSizeParent](../Topic/CDockSite::OnSizeParent.md)||  
|[CDockSite::PaneFromPoint](../Topic/CDockSite::PaneFromPoint.md)|Gibt einen an der Dockposition angedockten Bereich anhand des angegebenen Parameters an einem bestimmten Punkt zurück.|  
|[CDockSite::DockPaneLeftOf](../Topic/CDockSite::DockPaneLeftOf.md)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[CDockSite::FindPaneByID](../Topic/CDockSite::FindPaneByID.md)|Gibt den Bereich zurück, der anhand der angegebenen ID bestimmt wird.|  
|[CDockSite::GetPaneList](../Topic/CDockSite::GetPaneList.md)|Gibt eine Liste von Bereichen zurück, die an der Dockposition angedockt sind.|  
|[CDockSite::RectSideFromPoint](../Topic/CDockSite::RectSideFromPoint.md)||  
|[CDockSite::RemovePane](../Topic/CDockSite::RemovePane.md)||  
|[CDockSite::RemoveRow](../Topic/CDockSite::RemoveRow.md)||  
|[CDockSite::ReplacePane](../Topic/CDockSite::ReplacePane.md)||  
|[CDockSite::RepositionPanes](../Topic/CDockSite::RepositionPanes.md)||  
|[CDockSite::ResizeDockSite](../Topic/CDockSite::ResizeDockSite.md)||  
|[CDockSite::ResizeRow](../Topic/CDockSite::ResizeRow.md)||  
|[CDockSite::ShowPane](../Topic/CDockSite::ShowPane.md)|Zeigt den Bereich an.|  
|[CDockSite::ShowRow](../Topic/CDockSite::ShowRow.md)||  
|[CDockSite::SwapRows](../Topic/CDockSite::SwapRows.md)||  
  
## Hinweise  
 Das Framework erstellt `CDockSite`\-Objekte automatisch, wenn Sie [CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md) aufrufen.  Dockpositionsfenster werden am Rand des Clientbereichs des Hauptframefensters positioniert.  
  
 Sie müssen die durch die Dockposition bereitgestellten Dienste für gewöhnlich nicht aufrufen, da diese Dienste durch [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md) verarbeitet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Objekt der `CDockSite`\-Klasse erstellt wird.  
  
 [!CODE [NVC_MFC_RibbonApp#27](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#27)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## Anforderungen  
 **Header:** afxDockSite.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)