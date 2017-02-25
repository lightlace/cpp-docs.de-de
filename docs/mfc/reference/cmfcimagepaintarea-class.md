---
title: "CMFCImagePaintArea Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCImagePaintArea"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImagePaintArea class"
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMFCImagePaintArea Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt den Bildbereich bereit, den Sie verwenden, um ein Bild in einem Bildbearbeitungsdialogfeld zu ändern.  
  
## Syntax  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCImagePaintArea::CMFCImagePaintArea](../Topic/CMFCImagePaintArea::CMFCImagePaintArea.md)|Erstellt ein `CMFCImagePaintArea`\-Objekt.|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCImagePaintArea::GetMode](../Topic/CMFCImagePaintArea::GetMode.md)|Ruft den aktuellen Zeichnungsmodus ab.|  
|[CMFCImagePaintArea::SetBitmap](../Topic/CMFCImagePaintArea::SetBitmap.md)|Legt das Bitmapbild für den Bildbereich fest.|  
|[CMFCImagePaintArea::SetColor](../Topic/CMFCImagePaintArea::SetColor.md)|Legt die aktuelle Zeichenfarbe fest.|  
|[CMFCImagePaintArea::SetMode](../Topic/CMFCImagePaintArea::SetMode.md)|Legt den aktuellen Zeichnungsmodus fest.|  
  
### Hinweise  
 Diese Klasse ist nicht für die direkte Verwendung im Code vorgesehen.  
  
 Das Framework verwendet diese Klasse, um den Bildbereich in einem Bildbearbeitungsdialogfeld anzuzeigen.  Weitere Informationen zum Bildbearbeitungsdialogfeld, finden Sie unter [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt der Klasse `CMFCImagePaintArea` erstellt, dann die aktuellen Zeichenfarbe fest, legen Sie den aktuellen Zeichnungsmodus fest und legt das Bitmapbild für den Bildbereich fest.  
  
 [!CODE [NVC_MFC_RibbonApp#37](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#37)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## Anforderungen  
 **Header:** afximagepaintarea.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)