---
title: "CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IMAGE_EDIT_MODE Enumeration"
  - "CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration"
  - "CMFCImagePaintArea.IMAGE_EDIT_MODE Enumeration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IMAGE_EDIT_MODE-Enumerationsmethode"
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Zeichnungsmodus an, den Sie verwenden, um ein Bild in einem Bildbearbeitungsdialogfeld zu ändern.  
  
## Syntax  
  
```  
enum IMAGE_EDIT_MODE  
{  
   IMAGE_EDIT_MODE_PEN = 0,  
   IMAGE_EDIT_MODE_FILL,  
   IMAGE_EDIT_MODE_LINE,  
   IMAGE_EDIT_MODE_RECT,  
   IMAGE_EDIT_MODE_ELLIPSE,  
   IMAGE_EDIT_MODE_COLOR  
};  
```  
  
## Member  
  
|||  
|-|-|  
|Name|**Beschreibung**|  
|`IMAGE_EDIT_MODE_PEN`|Wird verwendet, um einzelne Pixel zu zeichnen.|  
|`IMAGE_EDIT_MODE_FILL`|Wird verwendet, um alle benachbarten Bereiche füllen, die die Farbe an der aktuellen Cursorposition enthalten.|  
|`IMAGE_EDIT_MODE_LINE`|Wird verwendet, um eine Linie zu zeichnen.|  
|`IMAGE_EDIT_MODE_RECT`|Wird verwendet, um ein Rechteck zu zeichnen.|  
|`IMAGE_EDIT_MODE_ELLIPSE`|Wird verwendet, um eine Ellipse zu zeichnen.|  
|`IMAGE_EDIT_MODE_COLOR`|Wird verwendet, um die aktuelle Farbe auf die Farbe an der aktuellen Cursorposition festzulegen.|  
  
### Hinweise  
 Die `CMFCImagePaintArea` und `CMFCImageEditorDialog`\-Klassen verwenden diese Enumeration, um den aktuellen Zeichnungsmodus festzulegen.  Der Zeichnungsmodus und die aktuelle Farbe werden verwendet, um den Platz hat in einem Bildbearbeitungsdialogfeld zu ändern.  Weitere Informationen zu den Aktionen `CMFCImagePaintArea` und `CMFCImageEditorDialog` finden Sie unter [CMFCImagePaintArea Class](../../mfc/reference/cmfcimagepaintarea-class.md) und [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
 Wenn Sie eine Farbe aus einem Bild auswählen, indem Sie `IMAGE_EDIT_MODE_COLOR`, gefolgt Modus wird, legt das Framework den aktuellen Zeichnungsmodus auf `IMAGE_EDIT_MODE_PEN` fest.  
  
## Anforderungen  
 **Header:** afximagepaintarea.h  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCImagePaintArea Class](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)