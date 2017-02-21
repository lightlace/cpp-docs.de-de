---
title: "CMFCTabToolTipInfo Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabToolTipInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabToolTipInfo struct"
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCTabToolTipInfo Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Struktur enthält Informationen über die MDI\-Registerkarte, der der Benutzer auf zeigt.  
  
## Syntax  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## Mitglieder  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m\_nTabIndex](../Topic/CMFCTabToolTipInfo::m_nTabIndex.md)|Gibt den Index des Tab\-Steuerelements an.|  
|[CMFCTabToolTipInfo::m\_pTabWnd](../Topic/CMFCTabToolTipInfo::m_pTabWnd.md)|Ein Zeiger auf das Tab\-Steuerelement.|  
|[CMFCTabToolTipInfo::m\_strText](../Topic/CMFCTabToolTipInfo::m_strText.md)|Der QuickInfo\-Text.|  
  
## Hinweise  
 Ein Zeiger auf eine `CMFCTabToolTipInfo`\-Struktur wird als Parameter der `AFX_WM_ON_GET_TAB_TOOLTIP` Meldung übergeben.  Diese Meldung wird generiert, wenn MDI\-Registerkarten und die Benutzerbewegungen des mauszeigers zu einem Tab\-Steuerelement aktiviert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie `CMFCTabToolTipInfo` in [MDITabsDemo\-Beispiel: MDI im Registerkartenformat](../../top/visual-cpp-samples.md) verwendet wird.  
  
 [!CODE [NVC_MFC_MDITabsDemo#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MDITabsDemo#2)]  
  
## Vererbungshierarchie  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## Anforderungen  
 **Header:** afxbasetabctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx::EnableMDITabs](../Topic/CMDIFrameWndEx::EnableMDITabs.md)   
 [CMDITabInfo::m\_bTabCustomTooltips](../Topic/CMDITabInfo::m_bTabCustomTooltips.md)