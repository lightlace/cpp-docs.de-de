---
title: CMFCImagePaintArea Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
dev_langs: C++
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f4af09ad1da91e3d59f82736ae9b240812069eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea-Klasse
Stellt den Bildbereich, mit denen Sie ein Bild in einem Bild-Editor (Dialogfeld) ändern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Erstellt ein `CMFCImagePaintArea`-Objekt.|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCImagePaintArea::GetMode](#getmode)|Ruft den aktuellen Zeichnungsmodus ab.|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Legt das Bitmap-Bild zum Bereich "Bild" fest.|  
|[CMFCImagePaintArea::SetColor](#setcolor)|Legt die aktuelle zeichnen Farbe fest.|  
|[CMFCImagePaintArea::SetMode](#setmode)|Legt den aktuellen Zeichnungsmodus fest.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse kann nicht direkt aus Ihrem Code verwendet werden.  
  
 Das Framework verwendet diese Klasse die Bildbereich in einem Bild-Editor (Dialogfeld) angezeigt. Weitere Informationen zu den Bild-Editor (Dialogfeld), finden Sie unter [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCImagePaintArea` Klasse, legen Sie die aktuelle zeichnen Farbe an, den aktuellen Zeichnungsmodus festgelegt, und legen Sie das Bitmap-Bild zum Bereich "Bild".  
  
 [!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afximagepaintarea.h  
  
##  <a name="cmfcimagepaintarea"></a>CMFCImagePaintArea::CMFCImagePaintArea  
 Erstellt ein `CMFCImagePaintArea`-Objekt.  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pParentDlg`|Ein Zeiger auf das Dialogfeld, das das übergeordnete Element des Grafik-Editor ist.|  
  
##  <a name="getmode"></a>CMFCImagePaintArea::GetMode  
 Ruft den aktuellen Zeichnungsmodus ab.  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) Wert, der den aktuellen Zeichnungsmodus angibt.  
  
##  <a name="setbitmap"></a>CMFCImagePaintArea::SetBitmap  
 Legt das Bitmap-Bild zum Bereich "Bild" fest.  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pBitmap`|Die neue Bitmap-Bild angezeigt.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pBitmap` ist `NULL`, diese Methode legt die Größe des Bereichs änderbaren Paint auf 0 (null). Andernfalls wird die Größe des Bereichs änderbaren Paint auf die Größe des bereitgestellten Bitmapbilds.  
  
##  <a name="setcolor"></a>CMFCImagePaintArea::SetColor  
 Legt die aktuelle zeichnen Farbe fest.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `color`|Die neue zeichnen Farbe.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie wählen eine Farbe aus der Bild-Editor Palette Leiste oder Farbauswahl, das Framework ruft diese Methode zum Aktualisieren der aktuellen zeichnen Farbe. Ist "Schwarz der Zeichnung Ausgangsfarbe" (ein `COLORREF` Wert 0).  
  
 Die Zeichnung Farbe wird durch die Bild-Editor (Dialogfeld) verwendet, für alle Modi, Zeichnen mit Ausnahme von `IMAGE_EDIT_MODE_COLOR`. Weitere Informationen zu Modi zu zeichnen, finden Sie unter [CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration](cmfcimagepaintarea-image-edit-mode-enumeration.md).  
  
##  <a name="setmode"></a>CMFCImagePaintArea::SetMode  
 Legt den aktuellen Zeichnungsmodus fest.  
  
```  
void SetMode(IMAGE_EDIT_MODE mode);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `mode`|Ein [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) Wert, der den aktuellen Zeichnungsmodus angibt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md)
