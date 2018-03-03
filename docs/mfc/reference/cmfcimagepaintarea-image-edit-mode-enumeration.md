---
title: CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
dev_langs:
- C++
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22e3b00bed830052c2abbc988152f4a14f1267ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration
Gibt eine Zeichnungsmodus, mit denen Sie ein Bild in einem Bild-Editor (Dialogfeld) zu ändern.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="members"></a>Member  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`IMAGE_EDIT_MODE_PEN`|Verwendet, um die einzelnen Pixel gezeichnet werden soll.|  
|`IMAGE_EDIT_MODE_FILL`|Verwendet, um alle angrenzenden Bereichen zu füllen, die die Farbe an der aktuellen Cursorposition enthalten.|  
|`IMAGE_EDIT_MODE_LINE`|Verwendet, um eine Linie zu zeichnen.|  
|`IMAGE_EDIT_MODE_RECT`|Verwendet, um ein Rechteck gezeichnet werden soll.|  
|`IMAGE_EDIT_MODE_ELLIPSE`|Verwendet eine Ellipse, die gezeichnet werden soll.|  
|`IMAGE_EDIT_MODE_COLOR`|Verwendet, um die Farbe die aktuelle Farbe fest, an der aktuellen Cursorposition.|  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCImagePaintArea` und `CMFCImageEditorDialog` Klassen, die diese Enumeration verwenden, um den aktuellen Zeichnungsmodus festgelegt. Die Zeichnungsmodus und die aktuelle Farbe werden verwendet, so ändern Sie die Bildbereich in einen Bild-Editor (Dialogfeld). Weitere Informationen zu `CMFCImagePaintArea` und `CMFCImageEditorDialog`, finden Sie unter [CMFCImagePaintArea Klasse](../../mfc/reference/cmfcimagepaintarea-class.md) und [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
 Wenn Sie eine Farbe auswählen aus einem Image mithilfe der `IMAGE_EDIT_MODE_COLOR` Zeichnungsmodus, das Framework wird die aktuelle Zeichnungsmodus auf `IMAGE_EDIT_MODE_PEN`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afximagepaintarea.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCImagePaintArea-Klasse](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md)
