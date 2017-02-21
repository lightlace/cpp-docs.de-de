---
title: "CMFCOutlookBarTabCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCOutlookBarTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBarTabCtrl class"
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCOutlookBarTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Tab\-Steuerelement, das die visuelle Darstellung **Navigationsbereich** in Microsoft Outlook verfügt.  
  
## Syntax  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Standardkonstruktor.|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md)|Fügt ein Windows\-Steuerelement als neue Registerkarte in der Outlook\-Leiste hinzu.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Aufgerufen vom Framework, um die Dimensionen des Eingabefelds zu bestimmen, das angezeigt wird, wenn ein Benutzer eine Registerkarte umbenannt wird.  \(Überschreibungen `CMFCBaseTabCtrl::CalcRectEdit`.\)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons.md)|Gerufen vom Framework während der Größenanpassungsvorgänge auf, um zu bestimmen, wenn weniger als Outlook\-Leisteregisterkartenseitenschaltflächen angezeigt werden können, gerade sichtbar.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowMorePageButtons.md)|Gerufen vom Framework während der Größenanpassungsvorgänge auf, um zu bestimmen, wenn mehr als Outlook\-Leisteregisterkartenseitenschaltflächen angezeigt werden können, gerade sichtbar.|  
|[CMFCOutlookBarTabCtrl::Create](../Topic/CMFCOutlookBarTabCtrl::Create.md)|Erstellt das Outlook\-Leistetab\-steuerelement.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](../Topic/CMFCOutlookBarTabCtrl::EnableAnimation.md)|Gibt an, ob die Animation, die während des Schalters zwischen aktiven Registerkarten auftritt, aktiviert ist.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](../Topic/CMFCOutlookBarTabCtrl::EnableInPlaceEdit.md)|Gibt an, ob ein Benutzer die Beschriftungen auf den Registerkartenschaltflächen der Outlook\-Leiste ändern kann.  \(Überschreibungen [CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md).\)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](../Topic/CMFCOutlookBarTabCtrl::EnableScrollButtons.md)|Aufgerufen durch das Framework, um Schaltflächen zu aktivieren, die den Benutzer zum Bildlauf durch Schaltflächen auf dem Outlook\-Leistebereich ermöglichen.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Identifiziert den Bereich, der einen angegebenen Punkt enthält.  \(Überschreibungen [CMFCBaseTabCtrl::FindTargetWnd](../Topic/CMFCBaseTabCtrl::FindTargetWnd.md).\)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](../Topic/CMFCOutlookBarTabCtrl::GetBorderSize.md)|Gibt die Rahmengröße des Outlook\-Tab\-Steuerelements zurück.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Ruft die Größe und die Position des Registerkartenbereichs des Tab\-Steuerelements ab.  \(Überschreibungen [CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md).\)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::GetVisiblePageButtons.md)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](../Topic/CMFCOutlookBarTabCtrl::IsAnimation.md)|Bestimmt, ob die Animation, die während des Schalters zwischen aktiven Registerkarten auftritt, aktiviert ist.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](../Topic/CMFCOutlookBarTabCtrl::IsMode2003.md)|Bestimmt, ob das Outlook\-Leistetab\-steuerelement in einem Modus ist, der Microsoft Outlook 2003 emuliert.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Bestimmt, ob ein Punkt innerhalb des Registerkartenbereichs ist.  \(Überschreibungen [CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md).\)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Bestimmt, ob eine Registerkarte abnehmbar ist.  \(Überschreibungen [CMFCBaseTabCtrl::IsTabDetachable](../Topic/CMFCBaseTabCtrl::IsTabDetachable.md).\)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Aufgerufen vom Framework, wenn eine Registerkarte eingefügt oder entfernt wird.  \(Überschreibungen `CMFCBaseTabCtrl::OnChangeTabs`.\)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons.md)|Aufgerufen vom Framework, um die Anzahl der Registerkartenseitenschaltflächen zu verringern, die sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowMorePageButtons.md)|Aufgerufen vom Framework, um die Anzahl der Registerkartenseitenschaltflächen zu erhöhen, die sichtbar sind.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](../Topic/CMFCOutlookBarTabCtrl::OnShowOptions.md)|Zeigt das Dialogfeld an. **Navigationsbereichsoptionen**|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Berechnet das interne Layout des Tab\-Steuerelements neu.  \(Überschreibungen [CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md).\)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md)|Legt die aktive Registerkarte fest.  \(Überschreibungen [CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md).\)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](../Topic/CMFCOutlookBarTabCtrl::SetBorderSize.md)|Legt die Rahmengröße des Outlook\-Tab\-Steuerelements fest.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](../Topic/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign.md)|Legt die Ausrichtung der Beschriftung auf den Registerkartenschaltflächen der Outlook\-Leiste fest.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md)|Legt die Bitmap fest, die die Symbole enthält, die an der Unterkante der Outlook\-Leiste in Outlook 2003\-Modus angezeigt werden \(siehe [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)\).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::SetVisiblePageButtons.md)||  
  
## Hinweise  
 Um Outlook erstellen halten Sie die andockbare Unterstützung verfügt, verwenden `CMFCOutlookBar` ein Objekt um das Outlook\-Leistetab\-steuerelement zu hosten ab.  Weitere Informationen finden Sie unter [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMFCOutlookBarTabCtrl`\-Objekt initialisiert und verschiedene Methoden in `CMFCOutlookBarTabCtrl` zu verwenden Sie.  Im Beispiel wird gezeigt, wie die direkte Bearbeitung der Beschriftung auf den Registerkartenseitenschaltflächen der Outlook\-Leiste, aktivieren die Animation, aktivieren Bildlaufhandles aktiviert, die dem Benutzer ermöglichen, durch Schaltflächen auf dem Outlook\-Leistebereich liegen, die Rahmengröße des Outlook\-Tab\-Steuerelements festlegen und die Ausrichtung der Beschriftung auf den Registerkartenschaltflächen der Outlook\-Leiste festlegen.  Dieser Codeausschnitt ist Teil [Outlook\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_OutlookDemo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_OutlookDemo#1)]  
[!CODE [NVC_MFC_OutlookDemo#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_OutlookDemo#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## Anforderungen  
 **Header:** afxoutlookbartabctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)