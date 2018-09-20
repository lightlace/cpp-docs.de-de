---
title: CMFCImagePaintArea-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4de97b23f0dc41220eac03f084fed37b2d9af671
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382842"
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea-Klasse

Die Bildbereich, mit denen Sie so ändern Sie ein Bild in einem Bild-Editor-Dialogfeld zur Verfügung.

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
|[CMFCImagePaintArea::GetMode](#getmode)|Ruft den Zeichnungsmodus des aktuellen ab.|
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Legt das Bitmap-Bild für den Bildbereich fest.|
|[CMFCImagePaintArea::SetColor](#setcolor)|Legt die aktuelle zeichnen Farbe fest.|
|[CMFCImagePaintArea::SetMode](#setmode)|Legt den aktuellen Zeichnungsmodus fest.|

### <a name="remarks"></a>Hinweise

Diese Klasse ist nicht vorgesehen, direkt aus Ihrem Code verwendet werden.

Das Framework verwendet diese Klasse, die im Bild in einem Bild-Editor-Dialogfeld angezeigt werden kann. Weitere Informationen zu diesem Bild-Editor-Dialogfeld finden Sie unter [CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCImagePaintArea` Klasse, legen Sie die aktuelle, zeichnen die Farbe, den aktuellen Zeichnungsmodus festgelegt, und legen Sie das Bitmap-Bild zum Bereich "Bild".

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afximagepaintarea.h

##  <a name="cmfcimagepaintarea"></a>  CMFCImagePaintArea::CMFCImagePaintArea

Erstellt ein `CMFCImagePaintArea`-Objekt.

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pParentDlg*|[in] Ein Zeiger auf das Dialogfeld, das das übergeordnete Element des Grafik-Editor.|

##  <a name="getmode"></a>  CMFCImagePaintArea::GetMode

Ruft den Zeichnungsmodus des aktuellen ab.

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) Wert, der den Zeichnungsmodus des aktuellen angibt.

##  <a name="setbitmap"></a>  CMFCImagePaintArea::SetBitmap

Legt das Bitmap-Bild für den Bildbereich fest.

```
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pBitmap*|[in] Die neue Bitmap-Bild angezeigt.|

### <a name="remarks"></a>Hinweise

Wenn *pBitmap* NULL ist, diese Methode legt die Größe des änderbar Paint Bereichs auf 0 (null). Andernfalls wird die Größe des änderbar Paint Bereichs auf die Größe des bereitgestellten Bitmapbilds.

##  <a name="setcolor"></a>  CMFCImagePaintArea::SetColor

Legt die aktuelle zeichnen Farbe fest.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*Farbe*|[in] Die neue Zeichnung Farbe.|

### <a name="remarks"></a>Hinweise

Wenn Sie eine Farbe aus der Palette-Leiste von Bild-Editor auswählen oder Farbauswahl angezeigt, das Framework ruft diese Methode, um die aktuelle zeichnen Farbe zu aktualisieren. Die Ausgangsfarbe zeichnen ist Schwarz (COLORREF Wert 0).

Die Farbe Zeichnen wird von der Bild-Editor-Dialogfeld für alle Zeichnen mit Ausnahme von IMAGE_EDIT_MODE_COLOR verwendet. Weitere Informationen zu den Modi zu zeichnen, finden Sie unter [cmfcimagepaintarea:: Image_edit_mode-Enumeration](cmfcimagepaintarea-image-edit-mode-enumeration.md).

##  <a name="setmode"></a>  CMFCImagePaintArea::SetMode

Legt den aktuellen Zeichnungsmodus fest.

```
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*mode*|[in] Ein [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) Wert, der den Zeichnungsmodus des aktuellen angibt.|

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog-Klasse](../../mfc/reference/cmfcimageeditordialog-class.md)
