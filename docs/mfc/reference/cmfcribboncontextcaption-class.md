---
title: CMFCRibbonContextCaption-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
ms.openlocfilehash: 26cc509db55bc95688123a7c6e673dcfc87c975b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262401"
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption-Klasse

Implementiert eine farbige Beschriftung, die über einer Menübandkategorie oder einer Kontextkategorie angezeigt wird.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCRibbonContextCaption::GetColor](#getcolor)|Gibt die Farbe der Beschriftung zurück.|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|

## <a name="remarks"></a>Hinweise

Diese Klasse kann nicht direkt instanziiert werden. Die [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) Klasse verwendet diese Klasse intern, um menübandkategorien Farbe hinzuzufügen.

Zum Festlegen der Farbe für menübandkategorien rufen [CMFCRibbonCategory:: Settabcolor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor). Zum Festlegen der Farbe für kontextkategorien rufen [CMFCRibbonBar:: Addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRibbonBar.h

##  <a name="getcolor"></a>  CMFCRibbonContextCaption::GetColor

Gibt die Hintergrundfarbe der Beschriftung zurück.

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Der zurückgegebene Wert kann es sich um eine der folgenden Enumerationswerte sein:

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>Hinweise

Die Farbe der Beschriftung kann festgelegt werden, durch den Aufruf [CMFCRibbonCategory:: Settabcolor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) oder [CMFCRibbonBar:: Addcontextcategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).

##  <a name="getrighttabx"></a>  CMFCRibbonContextCaption::GetRightTabX

Ruft die Position des rechten Rands des die Kategorie des Menüband-Registerkarte ab.

```
int GetRightTabX() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt den rechten X-Wert des umschließenden Rechtecks des der `CMFCRibbonCategory` Registerkarte des Menübands des Objekts oder den Wert 1, wenn die Registerkarte abgeschnitten wird.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonCategory-Klasse](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)
