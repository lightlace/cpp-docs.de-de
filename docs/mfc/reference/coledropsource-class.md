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
ms.openlocfilehash: 3a1e27ca6c1019eb8716194b3b7711238d015d6d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504002"
---
# <a name="coledropsource-class"></a>COleDropSource-Klasse

Ermöglicht, dass Daten auf ein Ablage Ziel gezogen werden.

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
|[COleDropSource::GiveFeedback](#givefeedback)|Ändert den Cursor während eines Drag & Drop-Vorgangs.|
|[COleDropSource::OnBeginDrag](#onbegindrag)|Behandelt die Maus Aufzeichnung während eines Drag & Drop-Vorgangs.|
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Prüft, ob das ziehen fortgesetzt werden soll.|

## <a name="remarks"></a>Hinweise

Die [COleDropTarget](../../mfc/reference/coledroptarget-class.md) -Klasse verarbeitet den empfangenden Teil des Drag & Drop-Vorgangs. Das `COleDropSource` -Objekt ist dafür verantwortlich, zu bestimmen, wann ein Zieh Vorgang beginnt, während der Zieh Vorgang Feedback bereitstellt und zu bestimmen, wann der Zieh Vorgang beendet wird.

Um ein `COleDropSource` -Objekt zu verwenden, nennen Sie einfach den-Konstruktor. Dadurch wird der Prozess zum Bestimmen der Ereignisse, z. b. mit einem Mausklick, mit der Verwendung von [COleDataSource::D odragdrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::D odragdrop](../../mfc/reference/coleclientitem-class.md#dodragdrop)oder [COleServerItem::D odragdrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) -Funktion vereinfacht. Mit diesen Funktionen wird ein `COleDropSource` -Objekt für Sie erstellt. Möglicherweise möchten Sie das Standardverhalten `COleDropSource` der über schreibbaren Funktionen ändern. Diese Member-Funktionen werden zu den entsprechenden Zeitpunkten des Frameworks aufgerufen.

Weitere Informationen zu Drag & Drop-Vorgängen mit OLE finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).

Weitere Informationen finden Sie unter [IDropSource](/windows/win32/api/oleidl/nn-oleidl-idropsource) in der Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>Anforderungen

**Header:** Afxole. h

##  <a name="coledropsource"></a>COleDropSource:: COleDropSource

Erstellt ein `COleDropSource`-Objekt.

```
COleDropSource();
```

##  <a name="givefeedback"></a>COleDropSource:: GiveFeedback

Wird vom Framework aufgerufen, nachdem [COleDropTarget:: OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) oder [COleDropTarget::D ragenter](../../mfc/reference/coledroptarget-class.md#ondragenter)aufgerufen wurde.

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>Parameter

*dropEffect*<br/>
Die Auswirkung, die dem Benutzer angezeigt werden soll, und gibt in der Regel an, was passiert, wenn an diesem Punkt mit den ausgewählten Daten ein Löschvorgang stattgefunden hat. In der Regel ist dies der Wert, der durch den letzten Aufruf von [CView:: OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) oder [CView:: OnDragOver](../../mfc/reference/cview-class.md#ondragover)zurückgegeben wird. Dabei kann es sich um eine oder mehrere der folgenden handeln:

- DROPEFFECT_NONE ein Drop wäre nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang wird ausgeführt.

- DROPEFFECT_MOVE ein Verschiebungs Vorgang wird ausgeführt.

- DROPEFFECT_LINK es wird ein Link zwischen den gelöschten Daten und den ursprünglichen Daten erstellt.

- DROPEFFECT_SCROLL ein Drag-Scroll-Vorgang ist im Begriff, oder er tritt im Ziel auf.

### <a name="return-value"></a>Rückgabewert

Gibt DRAGDROP_S_USEDEFAULTCURSORS zurück, wenn der Zieh Vorgang ausgeführt wird, andernfalls noError.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um dem Benutzer Feedback darüber zu geben, was passiert, wenn zu diesem Zeitpunkt ein Löschvorgang aufgetreten ist. Die Standard Implementierung verwendet die OLE-standardcursorn. Weitere Informationen zu Drag & Drop-Vorgängen mit OLE finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).

Weitere Informationen finden Sie unter [IDropSource:: GiveFeedback](/windows/win32/api/oleidl/nf-oleidl-idropsource-givefeedback), [IDropTarget::D ragover](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover)und [IDropTarget::D ragenter](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) im Windows SDK.

##  <a name="onbegindrag"></a>COleDropSource:: OnBeginDrag

Wird von Framework aufgerufen, wenn ein Ereignis auftritt, das einen Zieh Vorgang, z. b. das Drücken der linken Maustaste, einleiten könnte.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster, das die ausgewählten Daten enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das ziehen zulässig ist, andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Sie die Art und Weise ändern möchten, wie der Zieh Vorgang gestartet wird. Die Standard Implementierung erfasst die Maus und verbleibt im Zieh Modus, bis der Benutzer auf die linke oder die Rechte Maustaste klickt oder auf ESC trifft. zu diesem Zeitpunkt wird die Maus losgelassen.

##  <a name="querycontinuedrag"></a>COleDropSource:: QueryContinueDrag

Nachdem der Zieh Vorgang begonnen hat, wird diese Funktion vom Framework wiederholt aufgerufen, bis der Zieh Vorgang entweder abgebrochen oder abgeschlossen wird.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>Parameter

*bEscapePressed*<br/>
Gibt an, `COleDropSource::QueryContinueDrag`ob die ESC-Taste seit dem letzten-aufgerufene aufgerufen wurde.

*dwKeyState*<br/>
Enthält den Zustand der Modifizierertasten auf der Tastatur. Dies ist eine Kombination aus einer beliebigen Anzahl von folgenden: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.

### <a name="return-value"></a>Rückgabewert

DRAGDROP_S_CANCEL wenn die ESC-Taste oder die Rechte Schaltfläche gedrückt wird, wird die Schaltfläche nach links vor dem ziehen ausgelöst. DRAGDROP_S_DROP, wenn ein Ablage Vorgang erfolgen soll. Andernfalls S_OK.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Sie den Punkt ändern möchten, an dem der Zieh Vorgang abgebrochen wird oder ein Ablage Vorgang auftritt.

Die Standard Implementierung initiiert den Löschvorgang oder bricht den Zieh Vorgang wie folgt ab. Ein Drag-Vorgang wird abgebrochen, wenn die ESC-Taste oder die Rechte Maustaste gedrückt wird. Er initiiert einen Drop-Vorgang, wenn die linke Maustaste nach dem Start des Zieh Vorgangs ausgelöst wird. Andernfalls wird S_OK zurückgegeben, und es werden keine weiteren Vorgänge durchführt.

Da diese Funktion häufig aufgerufen wird, sollte Sie so weit wie möglich optimiert werden.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel Hierarchien](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
