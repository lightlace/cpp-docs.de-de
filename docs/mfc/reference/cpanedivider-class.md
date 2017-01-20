---
title: "CPaneDivider Class"
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
  - "CPaneDivider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDivider class"
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
caps.latest.revision: 25
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneDivider Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Die Klasse `CPaneDivider` unterteilt zwei Bereiche unterteilt, zwei Gruppen oder Bereiche trennt eine Gruppe Bereiche im Clientbereich des Hauptrahmenfensters.  
  
## Syntax  
  
```  
class CPaneDivider : public CBasePane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPaneDivider::CPaneDivider](../Topic/CPaneDivider::CPaneDivider.md)||  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPaneDivider::AddPaneContainer](../Topic/CPaneDivider::AddPaneContainer.md)||  
|[CPaneDivider::AddPane](../Topic/CPaneDivider::AddPane.md)||  
|[CPaneDivider::AddRecentPane](../Topic/CPaneDivider::AddRecentPane.md)||  
|[CPaneDivider::CalcExpectedDockedRect](../Topic/CPaneDivider::CalcExpectedDockedRect.md)||  
|[CPaneDivider::CalcFixedLayout](../Topic/CPaneDivider::CalcFixedLayout.md)|\(Überschreibungen [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CPaneDivider::CheckVisibility](../Topic/CPaneDivider::CheckVisibility.md)||  
|[CPaneDivider::CreateEx](../Topic/CPaneDivider::CreateEx.md)|\(Überschreibungen [CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md).\)|  
|[CPaneDivider::DoesAllowDynInsertBefore](../Topic/CPaneDivider::DoesAllowDynInsertBefore.md)|\(Überschreibungen [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CPaneDivider::DoesContainFloatingPane](../Topic/CPaneDivider::DoesContainFloatingPane.md)||  
|[CPaneDivider::FindPaneContainer](../Topic/CPaneDivider::FindPaneContainer.md)||  
|[CPaneDivider::FindTabbedPane](../Topic/CPaneDivider::FindTabbedPane.md)||  
|[CPaneDivider::GetDefaultWidth](../Topic/CPaneDivider::GetDefaultWidth.md)||  
|[CPaneDivider::GetFirstPane](../Topic/CPaneDivider::GetFirstPane.md)||  
|[CPaneDivider::GetPaneDividerStyle](../Topic/CPaneDivider::GetPaneDividerStyle.md)||  
|[CPaneDivider::GetRootContainerRect](../Topic/CPaneDivider::GetRootContainerRect.md)||  
|[CPaneDivider::GetWidth](../Topic/CPaneDivider::GetWidth.md)||  
|[CPaneDivider::Init](../Topic/CPaneDivider::Init.md)||  
|[CPaneDivider::InsertPane](../Topic/CPaneDivider::InsertPane.md)||  
|[CPaneDivider::IsAutoHideMode](../Topic/CPaneDivider::IsAutoHideMode.md)|\(Überschreibungen [CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md).\)|  
|[CPaneDivider::IsDefault](../Topic/CPaneDivider::IsDefault.md)||  
|[CPaneDivider::IsHorizontal](../Topic/CPaneDivider::IsHorizontal.md)|\(Überschreibungen [CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md).\)|  
|[CPaneDivider::Move](../Topic/CPaneDivider::Move.md)||  
|[CPaneDivider::NotifyAboutRelease](../Topic/CPaneDivider::NotifyAboutRelease.md)||  
|[CPaneDivider::OnShowPane](../Topic/CPaneDivider::OnShowPane.md)||  
|[CPaneDivider::ReleaseEmptyPaneContainers](../Topic/CPaneDivider::ReleaseEmptyPaneContainers.md)||  
|[CPaneDivider::RemovePane](../Topic/CPaneDivider::RemovePane.md)||  
|[CPaneDivider::ReplacePane](../Topic/CPaneDivider::ReplacePane.md)||  
|[CPaneDivider::RepositionPanes](../Topic/CPaneDivider::RepositionPanes.md)||  
|[CPaneDivider::Serialize](../Topic/CPaneDivider::Serialize.md)|\(Überschreibungen `CBasePane::Serialize`.\)|  
|[CPaneDivider::SetAutoHideMode](../Topic/CPaneDivider::SetAutoHideMode.md)||  
|[CPaneDivider::SetPaneContainerManager](../Topic/CPaneDivider::SetPaneContainerManager.md)||  
|[CPaneDivider::ShowWindow](../Topic/CPaneDivider::ShowWindow.md)||  
|[CPaneDivider::StoreRecentDockSiteInfo](../Topic/CPaneDivider::StoreRecentDockSiteInfo.md)||  
|[CPaneDivider::StoreRecentTabRelatedInfo](../Topic/CPaneDivider::StoreRecentTabRelatedInfo.md)||  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPaneDivider::GetPanes](../Topic/CPaneDivider::GetPanes.md)|Gibt die Liste von Bereichen zurück, die in [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md) befinden.  Diese Methode sollte nur für Standard Bereichsteiler aufgerufen werden.|  
|[CPaneDivider::GetPaneDividers](../Topic/CPaneDivider::GetPaneDividers.md)|Gibt die Liste der Bereichsteilern zurück, die in [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md) befinden.  Diese Methode sollte nur für Standard Bereichsteiler aufgerufen werden.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPaneDivider::m\_nDefaultWidth](../Topic/CPaneDivider::m_nDefaultWidth.md)|Gibt die Standardbreite in Pixel aller Bereichsteiler in der Anwendung.|  
|[CPaneDivider::m\_pSliderRTC](../Topic/CPaneDivider::m_pSliderRTC.md)|Hält einen Zeiger auf Ablaufklasseninformationen über `CPaneDivider` von abgeleitetes Objekt an.|  
  
## Hinweise  
 Das Framework erstellt `CPaneDivider`\-Objekte automatisch, wenn ein Bereich angedockt ist.  
  
 Es gibt zwei Typen Bereichsteiler:  
  
-   ein \- Bereichsteiler wird erstellt, wenn eine Gruppe Bereiche zu einer Seite des Hauptrahmenfensters angedockt ist.  Der Standardwert Bereichsteiler enthält einen Zeiger auf [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md) an und leitet die meisten Vorgänge in der Gruppe von Bereichen \(wie Größe eines Bereichs oder Andocken eines anderen Bereich oder Containers\) in Containermanager um.  Jeder andockbare Bereich verwaltet einen Zeiger auf den Standardwert Bereichsteiler.  
  
-   Ein regulärer Bereichsteiler unterteilt nur zwei Bereiche in einem Container.  Weitere Informationen finden Sie unter [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CPaneDivider`\-Objekt von einem `CWorkspaceBar`\-Objekt abrufen.  Dieser Codeausschnitt ist Teil [MDI stellt Demobeispiel mit den](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_MDITabsDemo#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MDITabsDemo#5)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)  
  
## Anforderungen  
 **Header:** afxPaneDivider.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md)   
 [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md)   
 [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)