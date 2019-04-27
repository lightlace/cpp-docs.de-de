---
title: COleDropTarget-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
helpviewer_keywords:
- COleDropTarget [MFC], COleDropTarget
- COleDropTarget [MFC], OnDragEnter
- COleDropTarget [MFC], OnDragLeave
- COleDropTarget [MFC], OnDragOver
- COleDropTarget [MFC], OnDragScroll
- COleDropTarget [MFC], OnDrop
- COleDropTarget [MFC], OnDropEx
- COleDropTarget [MFC], Register
- COleDropTarget [MFC], Revoke
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
ms.openlocfilehash: 9a1633ed48c763b986f3421c33589a05f8bba126
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224793"
---
# <a name="coledroptarget-class"></a>COleDropTarget-Klasse

Stellt den Kommunikationsmechanismus zwischen einem Fenster und den OLE-Bibliotheken bereit.

## <a name="syntax"></a>Syntax

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDropTarget::COleDropTarget](#coledroptarget)|Erstellt ein `COleDropTarget`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDropTarget::OnDragEnter](#ondragenter)|Wird aufgerufen, wenn der Cursor zuerst das Fenster betritt.|
|[COleDropTarget::OnDragLeave](#ondragleave)|Wird aufgerufen, wenn der Cursor aus dem Fenster gezogen wird.|
|[COleDropTarget::OnDragOver](#ondragover)|Wiederholt aufgerufen, wenn der Cursor über dem Fenster gezogen wird.|
|[COleDropTarget::OnDragScroll](#ondragscroll)|Wird aufgerufen, um festzustellen, ob der Cursor in der Region Scrollen Sie im Fenster gezogen wird.|
|[COleDropTarget::OnDrop](#ondrop)|Wird aufgerufen, wenn Daten in das Fenster an und Standard-Handler gelöscht werden.|
|[COleDropTarget::OnDropEx](#ondropex)|Wird aufgerufen, wenn Daten in das Fenster und der erste Handler gelöscht werden.|
|[COleDropTarget::Register](#register)|Wird das Fenster als ein gültiges Ablageziel registriert.|
|[COleDropTarget::Revoke](#revoke)|Bewirkt, dass das Fenster nicht mehr, wird ein gültiges Ablageziel.|

## <a name="remarks"></a>Hinweise

Erstellen ein Objekt dieser Klasse können ein Fenster, um Daten über den OLE-Drag & Drop-Mechanismus zu bestätigen.

Um ein Fenster zum Akzeptieren von Drop-Befehle zu erhalten, sollten Sie zuerst ein Objekt vom Erstellen der `COleDropTarget` Klasse, und rufen Sie dann die [registrieren](#register) Funktion mit einem Zeiger auf die gewünschte `CWnd` Objekt als einzigen Parameter.

Weitere Informationen zu Drag & Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="coledroptarget"></a>  COleDropTarget::COleDropTarget

Erstellt ein Objekt der Klasse `COleDropTarget`.

```
COleDropTarget();
```

### <a name="remarks"></a>Hinweise

Rufen Sie [registrieren](#register) , ein Fenster dieses Objekt zugeordnet werden soll.

##  <a name="ondragenter"></a>  COleDropTarget::OnDragEnter

Wird vom Framework aufgerufen, wenn der Cursor zuerst in das Fenster gezogen wird.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster den Cursor wird eingeben.

*pDataObject*<br/>
Verweist auf das Datenobjekt, das mit den Daten, die gelöscht werden können.

*dwKeyState*<br/>
Enthält den Status der Modifizierertasten. Dies ist eine Kombination von eine beliebige Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, and MK_RBUTTON.

*point*<br/>
Enthält die aktuelle Position des Cursors in Clientkoordinaten.

### <a name="return-value"></a>Rückgabewert

Die Auswirkungen, die sich ergeben würde, wenn eine Drop an die vom angegebenen Speicherort durchgeführt wurden *zeigen*. Sie können eine oder mehrere der folgenden sein:

- DROPEFFECT_NONE ein Drop würde nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang würde ausgeführt werden.

- DROPEFFECT_MOVE ein Verschiebevorgang würde ausgeführt werden.

- DROPEFFECT_LINK ein Link von der abgelegten Daten auf die ursprünglichen Daten würden hergestellt werden.

- DROPEFFECT_SCROLL ein Bildlauf Ziehvorgang durchgeführt wird oder im Ziel stattfindet.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um die Drop-Vorgänge in der das Fenster auftreten können. Die Standardimplementierung ruft [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), einfach DROPEFFECT_NONE standardmäßig zurückgegeben.

Weitere Informationen finden Sie unter [IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) im Windows SDK.

##  <a name="ondragleave"></a>  COleDropTarget::OnDragLeave

Wird vom Framework aufgerufen, wenn der Cursor im Fenster verlässt, während ein Ziehvorgang ausgeführt wird.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster den Cursor verlässt.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn bei der der Ziehvorgang des angegebenen Fensters verlässt besonderes Verhalten soll. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).

Weitere Informationen finden Sie unter [IDropTarget::DragLeave](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragleave) im Windows SDK.

##  <a name="ondragover"></a>  COleDropTarget::OnDragOver

Wird vom Framework aufgerufen, wenn der Cursor über das Fenster gezogen wird.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster, dem der Cursor über befindet.

*pDataObject*<br/>
Verweist auf das Datenobjekt, das den Daten, die gelöscht werden sollen.

*dwKeyState*<br/>
Enthält den Status der Modifizierertasten. Dies ist eine Kombination von eine beliebige Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, and MK_RBUTTON.

*point*<br/>
Enthält die aktuelle Position des Cursors in Clientkoordinaten.

### <a name="return-value"></a>Rückgabewert

Die Auswirkungen, die sich ergeben würde, wenn eine Drop an die vom angegebenen Speicherort durchgeführt wurden *zeigen*. Sie können eine oder mehrere der folgenden sein:

- DROPEFFECT_NONE ein Drop würde nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang würde ausgeführt werden.

- DROPEFFECT_MOVE ein Verschiebevorgang würde ausgeführt werden.

- DROPEFFECT_LINK ein Link von der abgelegten Daten auf die ursprünglichen Daten würden hergestellt werden.

- DROPEFFECT_SCROLL gibt an, die ein Ziehvorgang für den Bildlauf durchgeführt wird oder im Ziel stattfindet.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte überschrieben werden, um Drop-Vorgänge in der das Fenster auftreten zu ermöglichen. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), DROPEFFECT_NONE standardmäßig zurückgegeben. Da diese Funktion häufig während eines Drag & Drop-Vorgangs aufgerufen wird, sollten sie so weit wie möglich optimiert werden.

Weitere Informationen finden Sie unter [IDropTarget:: DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

##  <a name="ondragscroll"></a>  COleDropTarget::OnDragScroll

Wird aufgerufen, durch das Framework vor dem Aufruf [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) um zu bestimmen, ob *zeigen* im Bildlaufbereich ist.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster der Cursor befindet sich derzeit über.

*dwKeyState*<br/>
Enthält den Status der Modifizierertasten. Dies ist eine Kombination von eine beliebige Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, and MK_RBUTTON.

*point*<br/>
Enthält den Speicherort des Cursors in Pixel relativ zum Bildschirm.

### <a name="return-value"></a>Rückgabewert

Die Auswirkungen, die sich ergeben würde, wenn eine Drop an die vom angegebenen Speicherort durchgeführt wurden *zeigen*. Sie können eine oder mehrere der folgenden sein:

- DROPEFFECT_NONE ein Drop würde nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang würde ausgeführt werden.

- DROPEFFECT_MOVE ein Verschiebevorgang würde ausgeführt werden.

- DROPEFFECT_LINK ein Link von der abgelegten Daten auf die ursprünglichen Daten würden hergestellt werden.

- DROPEFFECT_SCROLL gibt an, die ein Ziehvorgang für den Bildlauf durchgeführt wird oder im Ziel stattfindet.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Sie für dieses Ereignis besonderes Verhalten bereitstellen möchten. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), die DROPEFFECT_NONE zurückgibt und das Fenster einen Bildlauf durchführt, wenn der Cursor in die Standard-Bildlaufbereich in den Rand des Fensters gezogen wird.

##  <a name="ondrop"></a>  COleDropTarget::OnDrop

Vom Framework aufgerufen, wenn ein Drop-Vorgang ausgeführt wird.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster der Cursor befindet sich derzeit über.

*pDataObject*<br/>
Verweist auf das Datenobjekt, das den Daten, die gelöscht werden sollen.

*dropEffect*<br/>
Der Effekt, den der Benutzer für den Löschvorgang ausgewählt haben. Sie können eine oder mehrere der folgenden sein:

- DROPEFFECT_COPY ein Kopiervorgang würde ausgeführt werden.

- DROPEFFECT_MOVE ein Verschiebevorgang würde ausgeführt werden.

- DROPEFFECT_LINK ein Link von der abgelegten Daten auf die ursprünglichen Daten würden hergestellt werden.

*point*<br/>
Enthält den Speicherort des Cursors in Pixel relativ zum Bildschirm.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Dropdownliste erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Das Framework ruft zunächst [OnDropEx](#ondropex). Wenn die `OnDropEx` Funktion der Ablegevorgang nicht behandelt, die das Framework ruft dann diese Memberfunktion `OnDrop`. Die Anwendung in der Regel überschreibt [OnDropEx](../../mfc/reference/cview-class.md#ondropex) in der Ansichtsklasse, Behandeln der rechten Maustaste Drag & drop. In der Regel der Ansichtsklasse [OnDrop](../../mfc/reference/cview-class.md#ondrop) wird verwendet, um einfache Drag & Drop zu behandeln.

Die standardmäßige Implementierung des `COleDropTarget::OnDrop` Aufrufe [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), die einfach "false" zurückgibt, wird standardmäßig.

Weitere Informationen finden Sie unter [IDropTarget:: Drop](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-drop) im Windows SDK.

##  <a name="ondropex"></a>  COleDropTarget::OnDropEx

Vom Framework aufgerufen, wenn ein Drop-Vorgang ausgeführt wird.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster der Cursor befindet sich derzeit über.

*pDataObject*<br/>
Verweist auf das Datenobjekt, das den Daten, die gelöscht werden sollen.

*dropDefault*<br/>
Die Auswirkungen, die der Benutzer für den Standard-Drop-Vorgang basierend auf dem aktuellen Schlüssel Status auswählen. Es kann DROPEFFECT_NONE sein. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.

*dropList*<br/>
Eine Liste mit der Drop-Effekten, die die Quelle unterstützt. Drop-Effekt-Werte können kombiniert werden, mit dem bitweisen OR (**&#124;**) Vorgang. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.

*point*<br/>
Enthält den Speicherort des Cursors in Pixel relativ zum Bildschirm.

### <a name="return-value"></a>Rückgabewert

Die Drop-Effekt, die bei der Löschversuch an die vom angegebenen Speicherort *zeigen*. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.

### <a name="remarks"></a>Hinweise

Das Framework ruft zuerst diese Funktion. Wenn der Ablegevorgang nicht handhaben kann, ruft das Framework dann [OnDrop](#ondrop). Überschreiben Sie in der Regel [OnDropEx](../../mfc/reference/cview-class.md#ondropex) in der Ansichtsklasse zur Unterstützung der rechten Maustaste Drag & drop. In der Regel der Ansichtsklasse [OnDrop](../../mfc/reference/cview-class.md#ondrop) wird verwendet, um den Fall der Unterstützung für einfache Drag & Drop zu behandeln.

Die standardmäßige Implementierung des `COleDropTarget::OnDropEx` Aufrufe [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). In der Standardeinstellung [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) einfach gibt den Dummywert an, dass die [OnDrop](#ondrop) Memberfunktion aufgerufen werden soll.

& Drop-Effekte wird beschrieben, die ein Drop-Vorgang zugeordnete Aktion. Finden Sie in der folgenden Liste der Drop-Effekten:

- DROPEFFECT_NONE ein Drop würde nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang würde ausgeführt werden.

- DROPEFFECT_MOVE ein Verschiebevorgang würde ausgeführt werden.

- DROPEFFECT_LINK ein Link von der abgelegten Daten auf die ursprünglichen Daten würden hergestellt werden.

- DROPEFFECT_SCROLL gibt an, die ein Ziehvorgang für den Bildlauf durchgeführt wird oder im Ziel stattfindet.

Weitere Informationen finden Sie unter [IDropTarget:: Drop](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-drop) im Windows SDK.

##  <a name="register"></a>  COleDropTarget::Register

Rufen Sie diese Funktion aus, um das Fenster für OLE-DLL als ein gültiges Ablageziel zu registrieren.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
Verweist auf das Fenster, das als Dropziel registriert werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Registrierung erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion muss aufgerufen werden, für die Drop-Vorgänge, um akzeptiert zu werden.

Weitere Informationen finden Sie unter [RegisterDragDrop](/windows/desktop/api/ole2/nf-ole2-registerdragdrop) im Windows SDK.

##  <a name="revoke"></a>  COleDropTarget::Revoke

Mit dieser Funktion wird vor dem Zerstören von einem beliebigen Fenster, das als Drop-Ziel durch einen Aufruf von registriert wurde [registrieren](#register) es aus der Liste der Ziele zu entfernen.

```
virtual void Revoke();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird automatisch aufgerufen, von der [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) Handler für das Fenster, das registriert wurde, daher ist es in der Regel nicht notwendig, diese Funktion explizit aufrufen,.

Weitere Informationen finden Sie unter [RevokeDragDrop](/windows/desktop/api/ole2/nf-ole2-revokedragdrop) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDropSource-Klasse](../../mfc/reference/coledropsource-class.md)
