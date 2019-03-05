---
title: CDocItem-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
ms.openlocfilehash: 6c1c1da14d732b6aff6ae07f86ae7b9c1b690b84
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291313"
---
# <a name="cdocitem-class"></a>CDocItem-Klasse

Die Basisklasse für Dokumentelemente, die Komponenten der Daten eines Dokuments sind.

## <a name="syntax"></a>Syntax

```
class CDocItem : public CCmdTarget
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDocItem::GetDocument](#getdocument)|Gibt zurück, das Dokument, das das Element enthält.|
|[CDocItem::IsBlank](#isblank)|Bestimmt, ob das Element alle Informationen enthält.|

## <a name="remarks"></a>Hinweise

`CDocItem` Objekte werden verwendet, um OLE-Elemente in Client- und Dokumente darzustellen.

Weitere Informationen finden Sie im Artikel [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="getdocument"></a>  CDocItem::GetDocument

Rufen Sie diese Funktion, um das Dokument zu erhalten, das das Element enthält.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Dokument, das das Element enthält; NULL, wenn das Element nicht Teil eines Dokuments ist.

### <a name="remarks"></a>Hinweise

Diese Funktion wird in den abgeleiteten Klassen überschrieben [COleClientItem](../../mfc/reference/coleclientitem-class.md) und [COleServerItem](../../mfc/reference/coleserveritem-class.md), Rückgabe eines Zeigers auf eine [COleDocument](../../mfc/reference/coledocument-class.md), [ COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), oder ein [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) Objekt.

##  <a name="isblank"></a>  CDocItem::IsBlank

Vom Framework aufgerufen, wenn Standardserialisierung auftritt.

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Element keine Informationen enthält; andernfalls 0.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `CDocItem` Objekte sind nicht leer. [COleClientItem](../../mfc/reference/coleclientitem-class.md) Objekte sind manchmal leer, da sie direkt vom abgeleitet sind `CDocItem`. Allerdings [COleServerItem](../../mfc/reference/coleserveritem-class.md) Objekte sind immer leer. In der Standardeinstellung werden OLE-Anwendungen, die mit `COleClientItem` Objekte, die keine x- oder y Block werden serialisiert. Dies erfolgt durch "true" zurückgeben, von einer Überschreibung von `IsBlank` Wenn das Element aufweist, keine x- oder y Block.

Überschreiben Sie diese Funktion, wenn Sie andere Aktionen während der Serialisierung implementieren möchten.

## <a name="see-also"></a>Siehe auch

[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDocument-Klasse](../../mfc/reference/coledocument-class.md)<br/>
[COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)<br/>
[COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)
