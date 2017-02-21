---
title: "CMFCColorPopupMenu Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorPopupMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorPopupMenu class"
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CMFCColorPopupMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt ein Popupmenü dar, dem Benutzer verwenden, um Farben in einem Dokument oder einer Anwendung auszuwählen.  
  
## Syntax  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](../Topic/CMFCColorPopupMenu::CMFCColorPopupMenu.md)|Erstellt ein `CMFCColorPopupMenu`\-Objekt.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCColorPopupMenu::CreateTearOffBar](../Topic/CMFCColorPopupMenu::CreateTearOffBar.md)|Erstellt eine andockbare Tearoffe Farbleiste.  \(Überschreibungen [CMFCPopupMenu::CreateTearOffBar](../Topic/CMFCPopupMenu::CreateTearOffBar.md).\)|  
|[CMFCColorPopupMenu::GetMenuBar](../Topic/CMFCColorPopupMenu::GetMenuBar.md)|Gibt [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) zurück, das innerhalb des Popupmenüs eingebettet ist.  \(Überschreibungen [CMFCPopupMenu::GetMenuBar](../Topic/CMFCPopupMenu::GetMenuBar.md).\)|  
|`CMFCColorPopupMenu::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCColorPopupMenu::SetPropList](../Topic/CMFCColorPopupMenu::SetPropList.md)|Legt das Eigenschaftraster\-steuerelement\-Objekt des eingebetteten `CMFCColorBar`\-Objekts fest.|  
  
### Datenmember  
  
|||  
|-|-|  
|Name|Description|  
|`m_bEnabledInCustomizeMode`|Ein boolescher Wert, der bestimmt, ob die Farbleiste anzeigt.|  
|`m_wndColorBar`|Das Objekt, das `CMFCColorBar` Farbauswahl bereitstellt.|  
  
### Hinweise  
 Diese Klasse erbt die Popupmenüfunktionalität der `CMFCPopupMenu`\-Klasse und verwaltet ein Objekt, das `CMFCColorBar` Farbauswahl bereitstellt.  Wenn das Symbolleistenframework im Anpassungsmodus ist und der `m_bEnabledInCustomizeMode`\-Member zu `FALSE` festgelegt ist, wird das Farbleistenobjekt nicht angezeigt.  Weitere Informationen zu Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../Topic/CMFCToolBar::IsCustomizeMode.md)  
  
 Weitere Informationen zur `CMFCColorBar`\-Komponente finden Sie unter [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## Anforderungen  
 **Header:** afxcolorpopupmenu.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)