---
title: "CMFCImageEditorPaletteBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCImageEditorPaletteBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImageEditorPaletteBar class"
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCImageEditorPaletteBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Palettenleistefunktionalität zu einem Bildbearbeitungsdialogfeld bereit.  
  
## Syntax  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCImageEditorPaletteBar::GetRowHeight](../Topic/CMFCImageEditorPaletteBar::GetRowHeight.md)|Gibt die Höhe Symbolleisten\-Schaltflächen zurück.  \(Überschreibungen [CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md).\)|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](../Topic/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable.md)|Bestimmt, ob die Symbolleiste Schaltflächen anzeigen kann, Rahmen erweitert haben.  \(Überschreibungen [CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md).\)|  
  
### Hinweise  
 Diese Klasse ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Das Framework verwendet diese Klasse, um eine Palettenleiste in einem Bildbearbeitungsdialogfeld anzuzeigen.  Weitere Informationen zum Bildbearbeitungsdialogfeld, finden Sie unter [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## Anforderungen  
 **Header:** afximageeditordialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)