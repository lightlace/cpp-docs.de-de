---
title: CDocObjectServerItem-Klasse
ms.date: 03/27/2019
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnDoVerb
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnDoVerb
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
ms.openlocfilehash: 4d44791415626f1a94500b9c3885581d67e8fe42
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506820"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem-Klasse

Implementiert OLE-Serververben speziell für DocObject-Server.

## <a name="syntax"></a>Syntax

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Erstellt ein `CDocObjectServerItem`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDocObjectServerItem::GetDocument](#getdocument)|Ruft einen Zeiger auf das Dokument ab, das das Element enthält.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDocObjectServerItem::OnDoVerb](#ondoverb)|Wird aufgerufen, um ein Verb auszuführen.|
|[CDocObjectServerItem::OnHide](#onhide)|Löst eine Ausnahme aus, wenn das Framework versucht, ein DocObject-Element auszublenden.|
|[CDocObjectServerItem::OnShow](#onshow)|Wird von Framework aufgerufen, um das DocObject-Element direkt zu aktivieren. Wenn das Element kein DocObject ist, ruft [COleServerItem:: onShow](../../mfc/reference/coleserveritem-class.md#onshow)auf.|

## <a name="remarks"></a>Hinweise

`CDocObjectServerItem`definiert über schreibbare Member-Funktionen: [OnHide](#onhide), [ondoverb](#ondoverb)und [onShow](#onshow).

Um zu `CDocObjectServerItem`verwenden, stellen Sie sicher, dass die [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) `COleServerDoc`-Überschreibung in der `CDocObjectServerItem` von abgeleiteten Klasse ein neues-Objekt zurückgibt. Wenn Sie Funktionen in Ihrem Element ändern müssen, können Sie eine neue Instanz Ihrer eigenen `CDocObjectServerItem`, von abgeleiteten Klasse erstellen.

Weitere Informationen zu docobjects finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in der *MFC-Referenz*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>Anforderungen

**Header:** afxdocob. h

##  <a name="cdocobjectserveritem"></a>CDocObjectServerItem:: CDocObjectServerItem

Erstellt ein `CDocObjectServerItem`-Objekt.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>Parameter

*pServerDoc*<br/>
Ein Zeiger auf das Dokument, das das neue DocObject-Element enthalten soll.

*bAutoDelete*<br/>
Gibt an, ob das Objekt gelöscht werden kann, wenn ein Link zu dem Objekt freigegeben wird. Legen Sie das-Argument auf false `CDocObjectServerItem` fest, wenn das-Objekt ein integraler Bestandteil der Daten Ihres Dokuments ist. Legen Sie diese Einstellung auf true fest, wenn das Objekt eine sekundäre Struktur ist, die verwendet wird, um einen Bereich in den Daten des Dokuments zu identifizieren, die vom Framework gelöscht werden können.

##  <a name="getdocument"></a>CDocObjectServerItem:: GetDocument

Ruft einen Zeiger auf das Dokument ab, das das Element enthält.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Dokument, das das Element enthält. NULL, wenn das Element nicht Teil eines Dokuments ist.

### <a name="remarks"></a>Hinweise

Dies ermöglicht den Zugriff auf das Server Dokument, das Sie als Argument an den [CDocObjectServerItem](#cdocobjectserveritem) -Konstruktor übergeben haben.

##  <a name="ondoverb"></a>CDocObjectServerItem:: ondoverb

Wird von Framework aufgerufen, um das angegebene Verb auszuführen.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Gibt das auszuführende Verb an. Mögliche Werte finden Sie unter [IOleObject::D overb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) in der Windows SDK.

### <a name="remarks"></a>Hinweise

Die Standard Implementierung ruft die [onShow](#onshow) -Member-Funktion auf, wenn das Element ein DocObject-Element ist und OLEIVERB_INPLACEACTIVATE oder OLEIVERB_SHOW angegeben wird. Wenn das Element kein DocObject ist oder ein anderes Verb angegeben ist, ruft die Standard Implementierung [COleServerItem:: ondoverb](../../mfc/reference/coleserveritem-class.md#ondoverb)auf.

##  <a name="onhide"></a>CDocObjectServerItem:: onHide

Wird vom Framework aufgerufen, um das Element auszublenden.

```
virtual void OnHide();
```

### <a name="remarks"></a>Hinweise

Die Standard Implementierung löst eine Ausnahme aus, wenn das Element ein DocObject ist. Ein aktives DocObject-Element kann nicht ausgeblendet werden, da es die gesamte Ansicht annimmt. Sie müssen das DocObject-Element deaktivieren, damit es verschwindet. Wenn das Element kein DocObject ist, ruft die Standard Implementierung [COleServerItem:: onHide](../../mfc/reference/coleserveritem-class.md#onhide)auf.

##  <a name="onshow"></a>CDocObjectServerItem:: onShow

Wird von Framework aufgerufen, um die Serveranwendung anzuweisen, das DocObject-Element direkt zu aktivieren.

```
virtual void OnShow();
```

### <a name="remarks"></a>Hinweise

Wenn das Element kein DocObject ist, ruft die Standard Implementierung [COleServerItem:: onShow](../../mfc/reference/coleserveritem-class.md#onopen)auf. Überschreiben Sie diese Funktion, wenn Sie beim Öffnen eines DocObject-Elements eine besondere Verarbeitung durchführen möchten.

## <a name="see-also"></a>Siehe auch

[COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServer-Klasse](../../mfc/reference/cdocobjectserver-class.md)<br/>
[COleDocObjectItem-Klasse](../../mfc/reference/coledocobjectitem-class.md)
