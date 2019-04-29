---
title: COleDropSource-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
ms.openlocfilehash: a2773333ea1dd89f73e7bdf3c5dc2f36945e0810
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391100"
---
# <a name="coledropsource-class"></a>COleDropSource-Klasse

Können Daten an ein Ablageziel gezogen werden.

## <a name="syntax"></a>Syntax

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDropSource::COleDropSource](#coledropsource)|Erstellt ein `COleDropSource`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDropSource::GiveFeedback](#givefeedback)|Ändert sich der Cursor während eines Drag & Drop-Vorgangs.|
|[COleDropSource::OnBeginDrag](#onbegindrag)|Behandelt die Erfassung von Mauseingaben während eines Drag & Drop-Vorgangs an.|
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Überprüft, ob Sie ziehen, sollten weiterhin.|

## <a name="remarks"></a>Hinweise

Die [COleDropTarget](../../mfc/reference/coledroptarget-class.md) Klasse behandelt den empfangenden Teil der Drag & Drop-Vorgang. Die `COleDropSource` -Objekt ist verantwortlich für das bestimmen, wann ein Ziehvorgang begonnen und Bereitstellen von Feedback während des Ziehvorgangs bestimmen, wann der Ziehvorgang endet.

Verwenden einer `COleDropSource` Objekt, rufen Sie einfach den Konstruktor. Dies vereinfacht den Prozess der Bestimmung, welche Ereignisse, z. B. ein Mausklick, beginnen mit einem Drag & [oledatasource:: DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), oder [ COleServerItem:: DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) Funktion. Diese Funktionen erstellt einen `COleDropSource` -Objekt für Sie. Möglicherweise möchten Sie das Standardverhalten des Ändern der `COleDropSource` überschreibbare-Funktionen. Diese Memberfunktionen werden vom Framework jeweils richtigen Zeitpunkt aufgerufen werden.

Weitere Informationen zu Drag & Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).

Weitere Informationen finden Sie unter [IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource) im Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="coledropsource"></a>  COleDropSource::COleDropSource

Erstellt ein `COleDropSource`-Objekt.

```
COleDropSource();
```

##  <a name="givefeedback"></a>  COleDropSource::GiveFeedback

Vom Framework aufgerufen, nach dem Aufruf [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) oder [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>Parameter

*dropEffect*<br/>
Die Auswirkungen, die Sie dem Benutzer anzeigen möchten, in der Regel, der angibt, was geschieht, wenn ein Ablegen an diesem Punkt mit den ausgewählten Daten aufgetreten ist. Dies ist normalerweise der Rückgabewert vom letzten Aufruf von [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) oder [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Sie können eine oder mehrere der folgenden sein:

- DROPEFFECT_NONE ein Drop würde nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang würde ausgeführt werden.

- DROPEFFECT_MOVE ein Verschiebevorgang würde ausgeführt werden.

- DROPEFFECT_LINK ein Link von der abgelegten Daten auf die ursprünglichen Daten würden hergestellt werden.

- DROPEFFECT_SCROLL ein Bildlauf Ziehvorgang durchgeführt wird oder im Ziel stattfindet.

### <a name="return-value"></a>Rückgabewert

Gibt zurück, DRAGDROP_S_USEDEFAULTCURSORS Wenn Ziehen wird durchgeführt. "noError" ZURÜCKGEGEBEN, wenn er nicht ist.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um Feedback an den Benutzer zu, was passieren würde, wenn ein ablegen zu diesem Zeitpunkt aufgetreten sind. Die Standardimplementierung verwendet die OLE-Standardcursor an. Weitere Informationen zu Drag & Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).

Weitere Informationen finden Sie unter [IDropSource::GiveFeedback](/windows/desktop/api/oleidl/nf-oleidl-idropsource-givefeedback), [IDropTarget:: DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover), und [IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) im Windows SDK.

##  <a name="onbegindrag"></a>  COleDropSource::OnBeginDrag

Wird aufgerufen, durch das Framework beim Auftreten eines Ereignisses, das einen Ziehvorgang auswirken, z. B. die linke Maustaste drückt einleiten kann.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster, das die ausgewählten Daten enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn ziehen zulässig ist, andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Sie möchten die Möglichkeit zu ändern, die der ziehen Prozess gestartet wurde. Die standardmäßige Implementierung die Maus erfasst und in den Dragmodus bleibt, bis der Benutzer klickt auf die linke oder rechte Maustaste gedrückt oder ESC trifft, woraufhin sie die Maustaste loslässt.

##  <a name="querycontinuedrag"></a>  COleDropSource::QueryContinueDrag

Nach dem Ziehen gestartet wurde, ist diese Funktion oft vom Framework aufgerufen, bis der Ziehvorgang abgebrochen oder abgeschlossen wird.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>Parameter

*bEscapePressed*<br/>
Gibt an, ob die ESC-Taste seit dem letzten Aufruf von gedrückt wurde `COleDropSource::QueryContinueDrag`.

*dwKeyState*<br/>
Enthält den Status der Zusatztasten der Tastatur. Dies ist eine Kombination von eine beliebige Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, and MK_RBUTTON.

### <a name="return-value"></a>Rückgabewert

DRAGDROP_S_CANCEL, wenn die ESC-Taste oder die Rechte Taste gedrückt wird, oder links die Schaltfläche wird ausgelöst, vor dem Ziehen gestartet wird. DRAGDROP_S_DROP, wenn ein Ablagevorgang erfolgen soll. Andernfalls S_OK.

### <a name="remarks"></a>Hinweise

Außer Kraft setzen, die diese Funktion ggf. so ändern Sie den Punkt, an dem der Ziehvorgang abgebrochen wird oder eine Drop auftritt.

Die Standardimplementierung initiiert die Dropdownliste oder bricht Sie wie folgt für den Ziehvorgang ab. Sie Bricht einen Ziehvorgang aus, wenn die ESC-Taste oder die rechte Maustaste gedrückt wird. Er initiiert einen Drop-Vorgang, wenn die linke Maustaste gedrückt ausgelöst wird, nachdem Sie ziehen gestartet wurde. Andernfalls gibt S_OK zurück, und führt keine weiteren Vorgänge.

Da diese Funktion häufig aufgerufen wird, sollten sie so weit wie möglich optimiert werden.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
