---
title: 'Cmfcimagepaintarea:: Image_edit_mode-Enumeration | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
dev_langs:
- C++
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b87b0c8c179e2982c450d244c50ea89dad2a596a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848605"
---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration
Gibt eine Zeichnungsmodus, mit denen Sie ein Bild in einem Bild-Editor-Dialogfeld ändern.  
  
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
|IMAGE_EDIT_MODE_PEN|Verwendet, um die einzelnen Pixel gezeichnet werden soll.|  
|IMAGE_EDIT_MODE_FILL|Verwendet, um alle benachbarte Bereiche zu füllen, die die Farbe in der aktuellen Cursorposition enthalten.|  
|IMAGE_EDIT_MODE_LINE|Verwendet, um eine Linie zu zeichnen.|  
|IMAGE_EDIT_MODE_RECT|Verwendet, um ein Rechteck zu zeichnen.|  
|IMAGE_EDIT_MODE_ELLIPSE|Verwendet, um eine Ellipse zu zeichnen.|  
|IMAGE_EDIT_MODE_COLOR|Verwendet, um die aktuelle Farbe auf die Farbe an der aktuellen Cursorposition festgelegt.|  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCImagePaintArea` und `CMFCImageEditorDialog` Klassen, die diese Enumeration verwenden, um den aktuellen Zeichnungsmodus festgelegt. Den Zeichnungsmodus des und die aktuelle Farbe werden verwendet, so ändern Sie die Bildbereich in einem Bild-Editor-Dialogfeld. Weitere Informationen zu `CMFCImagePaintArea` und `CMFCImageEditorDialog`, finden Sie unter [CMFCImagePaintArea-Klasse](../../mfc/reference/cmfcimagepaintarea-class.md) und [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
 Wenn Sie eine Farbe aus einem Image mit den Zeichnungsmodus IMAGE_EDIT_MODE_COLOR auswählen, wird das Framework den aktuellen Zeichnungsmodus auf IMAGE_EDIT_MODE_PEN an.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afximagepaintarea.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCImagePaintArea-Klasse](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md)
