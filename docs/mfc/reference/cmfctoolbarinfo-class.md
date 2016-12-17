---
title: "CMFCToolBarInfo Class"
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
  - "CMFCToolBarInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarInfo class"
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Enthält die Ressourcen\-IDs von Symbolleistenimages in unterschiedlichen Zuständen.  `CMFCToolBarInfo` ist eine Hilfsklasse, die als Parameter der [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)\-Methode verwendet wird.  
  
## Syntax  
  
```  
class CMFCToolBarInfo  
```  
  
## Mitglieder  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarInfo::m\_uiColdResID](../Topic/CMFCToolBarInfo::m_uiColdResID.md)|Ressourcen\-ID der Symbolleistenbitmaps, die reguläre \(kalte\) Symbolleistenimages enthält.|  
|[CMFCToolBarInfo::m\_uiDisabledResID](../Topic/CMFCToolBarInfo::m_uiDisabledResID.md)|Ressourcen\-ID der Symbolleistenbitmaps, die deaktivierte Symbolleistenimages enthält.|  
|[CMFCToolBarInfo::m\_uiHotResID](../Topic/CMFCToolBarInfo::m_uiHotResID.md)|Ressourcen\-ID der Symbolleistenbitmaps, die ausgewählte \(heiße\) Symbolleistenimages enthält.|  
|[CMFCToolBarInfo::m\_uiLargeColdResID](../Topic/CMFCToolBarInfo::m_uiLargeColdResID.md)|Ressourcen\-ID der Symbolleistenbitmaps, die die großen, regulären Symbolleistenimages enthält.|  
|[CMFCToolBarInfo::m\_uiLargeDisabledResID](../Topic/CMFCToolBarInfo::m_uiLargeDisabledResID.md)|Ressourcen\-ID der Symbolleistenbitmaps, die die großen, deaktivierten Symbolleistenimages enthält.|  
|[CMFCToolBarInfo::m\_uiLargeHotResID](../Topic/CMFCToolBarInfo::m_uiLargeHotResID.md)|Ressourcen\-ID der Symbolleistenbitmaps, die die großen enthält, ausgewählten Symbolleistenimages.|  
|[CMFCToolBarInfo::m\_uiMenuDisabledResID](../Topic/CMFCToolBarInfo::m_uiMenuDisabledResID.md)|Ressourcen\-ID der Symbolleistenbitmaps, die deaktivierte Menüimages enthält.|  
|[CMFCToolBarInfo::m\_uiMenuResID](../Topic/CMFCToolBarInfo::m_uiMenuResID.md)|Ressourcen\-ID der Symbolleistenbitmaps, die Menüimages enthält.|  
  
## Hinweise  
 Eine vollständige Symbolleistenbitmap besteht aus kleinen Symbolleistenimages \(Schaltflächen\) einer festen Größe.  Jedes Ressourcen\-ID, das in einem `CMFCToolBarInfo`\-Objekt gespeichert wird, ist eine Bitmap, die einen vollständigen Satz Symbolleistenimages in einem einzelnen Zustand enthält \(beispielsweise, ausgewählte, deaktivierte, große oder Menüimages\).  
  
## Vererbungshierarchie  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## Anforderungen  
 **Header:** afxtoolbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)