---
title: "CMFCDropDownFrame Class"
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
  - "CMFCDropDownFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownFrame class"
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownFrame Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Dropdown\-Rahmenfensterfunktionalität zu den Dropdown\-Symbolleisten und zu den Dropdown\-Symbolleistenschaltflächen bereit.  
  
## Syntax  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|Standardkonstruktor.|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCDropDownFrame::Create](../Topic/CMFCDropDownFrame::Create.md)|Erstellt ein `CMFCDropDownFrame`\-Objekt.|  
|`CMFCDropDownFrame::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCDropDownFrame::GetParentMenuBar](../Topic/CMFCDropDownFrame::GetParentMenuBar.md)|Ruft die Elemente Menüleiste der Dropdown\-Frame ab.|  
|[CMFCDropDownFrame::GetParentPopupMenu](../Topic/CMFCDropDownFrame::GetParentPopupMenu.md)|Ruft das Popupmenü Elemente der Dropdown\-Frame ab.|  
|`CMFCDropDownFrame::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCDropDownFrame::RecalcLayout](../Topic/CMFCDropDownFrame::RecalcLayout.md)|Ordnet die Dropdown\-Frame neu.|  
|[CMFCDropDownFrame::SetAutoDestroy](../Topic/CMFCDropDownFrame::SetAutoDestroy.md)|Legt fest, ob das untergeordnete Dropdown\-Symbolleistenfenster automatisch zerstört wird.|  
  
### Hinweise  
 Diese Klasse ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Das Framework verwendet diese Klasse, um Frameverhalten zu den `CMFCDropDownToolbar` und `CMFCDropDownToolbarButton`\-Klassen bereitzustellen.  Weitere Informationen zu diesen Klassen finden Sie unter [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) und [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Zeiger auf einen `CMFCDropDownFrame`\-Objekt aus einer Klasse `CFrameWnd` abgerufen und wie das untergeordnete automatisch zerstört werden Dropdown\-festlegt Symbolleistenfenster.  
  
 [!CODE [NVC_MFC_RibbonApp#36](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#36)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## Anforderungen  
 **Header:** afxdropdowntoolbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)