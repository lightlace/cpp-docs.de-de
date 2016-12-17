---
title: "CMFCRibbonMiniToolBar Class"
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
  - "CMFCRibbonMiniToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonMiniToolBar class"
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
caps.latest.revision: 24
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonMiniToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine kontextbezogene Popup\-Symbolleiste.  
  
## Syntax  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Standardkonstruktor|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Wird vom Framework verwendet wird, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](../Topic/CMFCRibbonMiniToolBar::IsContextMenuMode.md)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](../Topic/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar.md)|\(Überschreibt `CMFCPopupMenu::IsRibbonMiniToolBar`.\)|  
|[CMFCRibbonMiniToolBar::SetCommands](../Topic/CMFCRibbonMiniToolBar::SetCommands.md)|Legt die Liste der auf der Symbolleiste anzuzeigenden Befehle fest.|  
|[CMFCRibbonMiniToolBar::Show](../Topic/CMFCRibbonMiniToolBar::Show.md)|Zeigt die Minisymbolleiste an den angegebenen Bildschirmkoordinaten an.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](../Topic/CMFCRibbonMiniToolBar::ShowWithContextMenu.md)|Zeigt die Minisymbolleiste zusammen mit einem Kontextmenü an.|  
  
## Hinweise  
 Die Minisymbolleiste wird meist angezeigt, nachdem ein Benutzer ein Objekt in einem Dokument ausgewählt hat.  Nachdem der Benutzer einen Textblock in einem Textverarbeitungsprogramm auswählt, zeigt die Anwendung z. B. eine Minisymbolleiste mit Textformatierungsbefehlen an.  
  
 Die Minisymbolleiste wird transparent, wenn der Mauszeiger sich außerhalb des gültigen Bereichs der Minisymbolleiste befindet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## Anforderungen  
 **Header:** afxRibbonMiniToolBar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)