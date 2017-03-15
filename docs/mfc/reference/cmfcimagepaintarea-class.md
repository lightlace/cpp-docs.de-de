---
title: Klasse CMFCImagePaintArea | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
dev_langs:
- C++
helpviewer_keywords:
- CMFCImagePaintArea class
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c16fd9605474e57f167646ddc9bc91d235d1cba5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea-Klasse
Stellt den Bildbereich, mit denen Sie ein Bild in einem Bild-Editor-Dialogfeld ändern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CMFCImagePaintArea::GetMode](#getmode)|Ruft den Zeichnungsmodus des aktuellen ab.|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Legt das Bitmap-Bild für den Bildbereich fest.|  
|[CMFCImagePaintArea::SetColor](#setcolor)|Legt die aktuelle Zeichnung Farbe fest.|  
|[CMFCImagePaintArea::SetMode](#setmode)|Legt den aktuellen Zeichnungsmodus fest.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse kann nicht direkt aus dem Code verwendet werden.  
  
 Das Framework verwendet diese Klasse die Bildbereich in einem Bild-Editor-Dialogfeld angezeigt. Weitere Informationen über das Dialogfeld Bild-Editor finden Sie unter [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCImagePaintArea` Klasse, legen Sie die aktuelle zeichnen Farbe, legen den aktuellen Zeichnungsmodus, und legen das Bitmap-Bild für den Bildbereich.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#37;](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afximagepaintarea.h  
  
##  <a name="a-namecmfcimagepaintareaa--cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a>CMFCImagePaintArea::CMFCImagePaintArea  
 Erstellt ein `CMFCImagePaintArea`-Objekt.  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pParentDlg`|Ein Zeiger auf das Dialogfeld, das das übergeordnete Element des Grafik-Editor ist.|  
  
##  <a name="a-namegetmodea--cmfcimagepaintareagetmode"></a><a name="getmode"></a>CMFCImagePaintArea::GetMode  
 Ruft den Zeichnungsmodus des aktuellen ab.  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) Wert, der den aktuellen Zeichnungsmodus angibt.  
  
##  <a name="a-namesetbitmapa--cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a>CMFCImagePaintArea::SetBitmap  
 Legt das Bitmap-Bild für den Bildbereich fest.  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pBitmap`|Die neue Bitmap-Bild angezeigt.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pBitmap` ist `NULL`, diese Methode legt die Größe des Bereichs änderbaren Paint auf&0; (null). Andernfalls wird die Größe des Bereichs änderbaren Paint auf die Größe der bereitgestellten Bitmap.  
  
##  <a name="a-namesetcolora--cmfcimagepaintareasetcolor"></a><a name="setcolor"></a>CMFCImagePaintArea::SetColor  
 Legt die aktuelle Zeichnung Farbe fest.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `color`|Die neue Zeichnung Farbe.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine Farbe aus der Palette-Leiste von Bild-Editor auswählen oder Farbauswahl, das Framework ruft diese Methode zum Aktualisieren der aktuellen Zeichnung Farbe. Die anfängliche zeichnen Farbe ist Schwarz (ein `COLORREF` Wert 0).  
  
 Die Zeichnung Farbe wird im Dialogfeld Bild-Editor verwendet, für alle Modi, zeichnen, mit Ausnahme von `IMAGE_EDIT_MODE_COLOR`. Weitere Informationen über das Zeichnen von Modi finden Sie unter [CMFCImagePaintArea::IMAGE_EDIT_MODE-Enumeration](cmfcimagepaintarea-image-edit-mode-enumeration.md).  
  
##  <a name="a-namesetmodea--cmfcimagepaintareasetmode"></a><a name="setmode"></a>CMFCImagePaintArea::SetMode  
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

