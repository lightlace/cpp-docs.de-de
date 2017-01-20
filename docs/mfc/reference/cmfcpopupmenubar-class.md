---
title: "CMFCPopupMenuBar-Klasse"
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
  - "CMFCPopupMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPopupMenuBar-Klasse"
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPopupMenuBar-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Menüleiste eingebettet in ein Popupmenü.  
  
## Syntax  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](../Topic/CMFCPopupMenuBar::AdjustSizeImmediate.md)|Berechnet sofort das Layout eines Bereichs neu.  \(Überschreibungen [CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md).\)|  
|[CMFCPopupMenuBar::BuildOrigItems](../Topic/CMFCPopupMenuBar::BuildOrigItems.md)|Lädt Popupmenüelemente aus einer angegebenen Menüressource.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](../Topic/CMFCPopupMenuBar::CloseDelayedSubMenu.md)|Schließt eine verzögerte Popupmenüschaltfläche.|  
|[CMFCPopupMenuBar::ExportToMenu](../Topic/CMFCPopupMenuBar::ExportToMenu.md)|Erstellt ein Menü mit den Popupmenüschaltflächen.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](../Topic/CMFCPopupMenuBar::FindDestintationToolBar.md)|Sucht die Symbolleiste, in der ein bestimmter Punkt liegt.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](../Topic/CMFCPopupMenuBar::GetCurrentMenuImageSize.md)|Gibt die Größe von Menüschaltflächenimages an.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](../Topic/CMFCPopupMenuBar::GetDefaultMenuId.md)|Gibt den Bezeichner des standardmäßigen Menüelements zurück.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](../Topic/CMFCPopupMenuBar::GetLastCommandIndex.md)|Ruft den Index des zuletzt aufgerufenen Menübefehls ab.|  
|[CMFCPopupMenuBar::GetOffset](../Topic/CMFCPopupMenuBar::GetOffset.md)|Ruft den Zeilenoffset der Popupmenüleiste ab.|  
|[CMFCPopupMenuBar::ImportFromMenu](../Topic/CMFCPopupMenuBar::ImportFromMenu.md)|Importiert Popupmenüschaltflächen aus einem angegebenen Menü.|  
|[CMFCPopupMenuBar::IsDropDownListMode](../Topic/CMFCPopupMenuBar::IsDropDownListMode.md)|Gibt an, ob die Popupmenüleiste im Dropdownlistenmodus ist.|  
|[CMFCPopupMenuBar::IsPaletteMode](../Topic/CMFCPopupMenuBar::IsPaletteMode.md)|Gibt an, ob die Popupmenüleiste im Palettenmodus ist.|  
|[CMFCPopupMenuBar::IsRibbonPanel](../Topic/CMFCPopupMenuBar::IsRibbonPanel.md)|Gibt an, ob dies ein Favoritenmenübandbereich `FALSE` \(standardmäßig\) ist.|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](../Topic/CMFCPopupMenuBar::IsRibbonPanelInRegularMode.md)|Gibt an, ob dies ein Favoritenmenübandbereich im normalen Modus `FALSE` \(standardmäßig\) ist.|  
|[CMFCPopupMenuBar::LoadFromHash](../Topic/CMFCPopupMenuBar::LoadFromHash.md)|Lädt ein archiviertes Menü.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](../Topic/CMFCPopupMenuBar::RestoreDelayedSubMenu.md)|Stellt eine verzögerte Menüschaltfläche zum Schließen der Popupmenüleiste wieder her.|  
|[CMFCPopupMenuBar::SetButtonStyle](../Topic/CMFCPopupMenuBar::SetButtonStyle.md)|Legt das Format der Symbolleisten\-Schaltfläche am angegebenen Index fest.  \(Überschreibungen [CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md).\)|  
|[CMFCPopupMenuBar::SetOffset](../Topic/CMFCPopupMenuBar::SetOffset.md)|Legt den Zeilenoffset der Popupmenüleiste fest.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](../Topic/CMFCPopupMenuBar::StartPopupMenuTimer.md)|Stellt den Zeitgeber für eine angegebene verzögerte Popupmenüschaltfläche an.|  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCPopupMenuBar::m\_bDisableSideBarInXPMode](../Topic/CMFCPopupMenuBar::m_bDisableSideBarInXPMode.md)|Gibt an, ob die graue Randleiste angezeigt wird, wenn die Anwendung eine Windows XP\-Darstellung verfügt.|  
  
## Hinweise  
 `CMFCPopupMenuBar` wird gleichzeitig wie [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) erstellt und es eingebettet.  `CMFCPopupMenuBar` umfasst den gesamten Clientbereich des `CMFCPopupMenu`\-Objekts.  Es unterstützt Tastatur\- und Mauseingaben.  Es wird auch diese Eingabe zu `CMFCPopupMenu` und im Rahmenfenster der obersten Ebene mit.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMFCPopupMenuBar`\-Objekt von einem `CMFCPopupMenu`\-Objekt initialisiert.  Dieser Codeausschnitt ist Teil [Clientbeispiel Videofunktionen](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DrawClient#7](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#7)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## Anforderungen  
 **Header:** afxpopupmenubar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)