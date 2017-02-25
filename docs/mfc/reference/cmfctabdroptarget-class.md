---
title: "CMFCTabDropTarget Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabDropTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabDropTarget class"
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCTabDropTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt den Kommunikationsmechanismus zwischen einem Tab\-Steuerelement und den OLE\-Bibliotheken bereit.  
  
## Syntax  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|Standardkonstruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCTabDropTarget::OnDragEnter](../Topic/CMFCTabDropTarget::OnDragEnter.md)|Aufgerufen vom Framework, wenn der Benutzer ein Objekt in ein Registerkartenfenster zieht.  \(Überschreibungen [COleDropTarget::OnDragEnter](../Topic/COleDropTarget::OnDragEnter.md).\)|  
|[CMFCTabDropTarget::OnDragLeave](../Topic/CMFCTabDropTarget::OnDragLeave.md)|Aufgerufen vom Framework, wenn der Benutzer ein Objekt außerhalb des Registerkartenfensters zieht, das den Fokus besitzt.  \(Überschreibungen [COleDropTarget::OnDragLeave](../Topic/COleDropTarget::OnDragLeave.md).\)|  
|[CMFCTabDropTarget::OnDragOver](../Topic/CMFCTabDropTarget::OnDragOver.md)|Aufgerufen vom Framework, wenn der Benutzer ein Objekt auf das Registerkartenfenster zieht, das den Fokus besitzt.  \(Überschreibungen [COleDropTarget::OnDragOver](../Topic/COleDropTarget::OnDragOver.md).\)|  
|[CMFCTabDropTarget::OnDropEx](../Topic/CMFCTabDropTarget::OnDropEx.md)|Aufgerufen vom Framework, wenn der Benutzer die Maustaste am Ende eines Ziehvorgangs freigibt.  \(Überschreibungen [COleDropTarget::OnDropEx](../Topic/COleDropTarget::OnDropEx.md).\)|  
|[CMFCTabDropTarget::Register](../Topic/CMFCTabDropTarget::Register.md)|Registriert das Steuerelement als eines, das das Ziel eines Drag & Drop\-Vorgangs sein kann.|  
  
### Hinweise  
 Diese Klasse stellt Drag & Drop\-Unterstützung der `CMFCBaseTabCtrl`\-Klasse.  Wenn die Anwendung die OLE\-Bibliotheken initialisiert, indem sie die Funktion verwendet, [AfxOleInit](../Topic/AfxOleInit.md) registrieren sich `CMFCBaseTabCtrl`\-Objekte für Drag & Drop\-Vorgänge.  
  
 Die `CMFCTabDropTarget`\-Klasse erweitert die Basisklasse, indem sie die Registerkarte macht, die unter dem Cursor befindet, wenn ein Ziehvorgang aktiv auftritt.  Weitere Informationen über Drag & Drop\-Vorgänge, finden Sie unter [Drag & Drop \(OLE\)](../../mfc/drag-and-drop-ole.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMFCTabDropTarget`\-Objekt erstellt und dessen `Register`\-Methode verwendet.  
  
 [!CODE [NVC_MFC_RibbonApp#39](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#39)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## Anforderungen  
 **Header:** afxbasetabctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Drag & Drop \(OLE\)](../../mfc/drag-and-drop-ole.md)