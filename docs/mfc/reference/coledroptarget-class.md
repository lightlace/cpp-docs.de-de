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
ms.openlocfilehash: f5f101ca2c505e1b7c6b50b21af7d5aeef4ae625
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127880"
---
# <a name="coledroptarget-class"></a>COleDropTarget-Klasse

Stellt den Kommunikationsmechanismus zwischen einem Fenster und den OLE-Bibliotheken bereit.

## <a name="syntax"></a>Syntax

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[COleDropTarget:: COleDropTarget](#coledroptarget)|Erstellt ein `COleDropTarget`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[COleDropTarget:: OnDragEnter](#ondragenter)|Wird aufgerufen, wenn der Cursor zuerst das Fenster betritt.|
|[COleDropTarget:: OnDragLeave](#ondragleave)|Wird aufgerufen, wenn der Cursor aus dem Fenster gezogen wird.|
|[COleDropTarget:: OnDragOver](#ondragover)|Wird wiederholt aufgerufen, wenn der Cursor über das Fenster gezogen wird.|
|[COleDropTarget:: ondragscroll](#ondragscroll)|Wird aufgerufen, um zu bestimmen, ob der Cursor in den scrollbereich des Fensters gezogen wird.|
|[COleDropTarget:: OnDrop](#ondrop)|Wird aufgerufen, wenn Daten im Fenster abgelegt werden, Standard Handler.|
|[COleDropTarget:: ondropex](#ondropex)|Wird aufgerufen, wenn Daten im Fenster, anfänglicher Handler, abgelegt werden.|
|[COleDropTarget:: Register](#register)|Registriert das Fenster als gültiges Ablage Ziel.|
|[COleDropTarget:: Widerruf](#revoke)|Bewirkt, dass das Fenster kein gültiges Ablage Ziel mehr ist.|

## <a name="remarks"></a>Bemerkungen

Wenn Sie ein Objekt dieser Klasse erstellen, kann ein Fenster Daten über den OLE-und Drop-Mechanismus von OLE akzeptieren.

Zum Abrufen eines Fensters zum Akzeptieren von Drop-Befehlen sollten Sie zuerst ein Objekt der `COleDropTarget`-Klasse erstellen und dann die [Register](#register) -Funktion mit einem Zeiger auf das gewünschte `CWnd` Objekt als einzigen Parameter aufrufen.

Weitere Informationen zu Drag & Drop-Vorgängen mit OLE finden Sie im Artikel [OLE Drag](../../mfc/drag-and-drop-ole.md)& amp; Drop.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** Afxole. h

##  <a name="coledroptarget"></a>COleDropTarget:: COleDropTarget

Erstellt ein Objekt der Klasse `COleDropTarget`.

```
COleDropTarget();
```

### <a name="remarks"></a>Bemerkungen

Ruft [Register](#register) auf, um dieses-Objekt einem Fenster zuzuordnen.

##  <a name="ondragenter"></a>COleDropTarget:: OnDragEnter

Wird von Framework aufgerufen, wenn der Cursor zum ersten Mal in das Fenster gezogen wird.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*folgenden*<br/>
Zeigt auf das Fenster, in das der Cursor wechselt.

*pDataObject*<br/>
Verweist auf das Datenobjekt, das die Daten enthält, die gelöscht werden können.

*dwkeystate*<br/>
Enthält den Zustand der Modifizierertasten. Dies ist eine Kombination aus einer beliebigen Anzahl von folgenden: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.

*Punkt*<br/>
Enthält die aktuelle Position des Cursors in Client Koordinaten.

### <a name="return-value"></a>Rückgabewert

Der Effekt, der verursacht würde, wenn eine Ablage an der durch *Punkt*angegebenen Position versucht würde. Dabei kann es sich um eine oder mehrere der folgenden handeln:

- DROPEFFECT_NONE Drop wäre nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang ausgeführt wird.

- DROPEFFECT_MOVE ein Verschiebe Vorgang ausgeführt wird.

- DROPEFFECT_LINK eine Verknüpfung von den gelöschten Daten zu den ursprünglichen Daten erstellt werden.

- DROPEFFECT_SCROLL ein Drag & Drop-Vorgang im Ziel auftritt oder im Ziel auftritt.

### <a name="remarks"></a>Bemerkungen

Überschreiben Sie diese Funktion, um das Auftreten von Drop-Vorgängen im Fenster zuzulassen. Die Standard Implementierung ruft [CView:: OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)auf, der standardmäßig nur DROPEFFECT_NONE zurückgibt.

Weitere Informationen finden Sie unter [IDropTarget::D ragenter](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) im Windows SDK.

##  <a name="ondragleave"></a>COleDropTarget:: OnDragLeave

Wird von Framework aufgerufen, wenn der Cursor das Fenster verlässt, während ein Zieh Vorgang wirksam ist.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*folgenden*<br/>
Zeigt auf das Fenster, das der Cursor verlässt.

### <a name="remarks"></a>Bemerkungen

Überschreiben Sie diese Funktion, wenn Sie ein spezielles Verhalten wünschen, wenn der Zieh Vorgang das angegebene Fenster verlässt. Die Standard Implementierung dieser Funktion ruft [CView:: OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)auf.

Weitere Informationen finden Sie unter [IDropTarget::D ragleave](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragleave) in der Windows SDK.

##  <a name="ondragover"></a>COleDropTarget:: OnDragOver

Wird von Framework aufgerufen, wenn der Cursor über das Fenster gezogen wird.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*folgenden*<br/>
Zeigt auf das Fenster, über dem sich der Cursor befindet.

*pDataObject*<br/>
Verweist auf das Datenobjekt, das die Daten enthält, die gelöscht werden sollen.

*dwkeystate*<br/>
Enthält den Zustand der Modifizierertasten. Dies ist eine Kombination aus einer beliebigen Anzahl von folgenden: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.

*Punkt*<br/>
Enthält die aktuelle Position des Cursors in Client Koordinaten.

### <a name="return-value"></a>Rückgabewert

Der Effekt, der verursacht würde, wenn eine Ablage an der durch *Punkt*angegebenen Position versucht würde. Dabei kann es sich um eine oder mehrere der folgenden handeln:

- DROPEFFECT_NONE Drop wäre nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang ausgeführt wird.

- DROPEFFECT_MOVE ein Verschiebe Vorgang ausgeführt wird.

- DROPEFFECT_LINK eine Verknüpfung von den gelöschten Daten zu den ursprünglichen Daten erstellt werden.

- DROPEFFECT_SCROLL gibt an, dass ein Drag-Scroll-Vorgang stattfindet oder im Ziel auftritt.

### <a name="remarks"></a>Bemerkungen

Diese Funktion sollte überschrieben werden, damit Drop-Vorgänge im Fenster auftreten können. Die Standard Implementierung dieser Funktion ruft [CView:: OnDragOver](../../mfc/reference/cview-class.md#ondragover)auf, das standardmäßig DROPEFFECT_NONE zurückgibt. Da diese Funktion während eines Drag & Drop-Vorgangs häufig aufgerufen wird, sollte Sie so weit wie möglich optimiert werden.

Weitere Informationen finden Sie unter [IDropTarget::D ragover](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover) in der Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

##  <a name="ondragscroll"></a>COleDropTarget:: ondragscroll

Wird vom Framework aufgerufen, bevor [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) aufgerufen wird, um zu bestimmen, ob der *Punkt* im scrollbereich ist.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*folgenden*<br/>
Zeigt auf das Fenster, über dem sich der Cursor zurzeit befindet.

*dwkeystate*<br/>
Enthält den Zustand der Modifizierertasten. Dies ist eine Kombination aus einer beliebigen Anzahl von folgenden: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.

*Punkt*<br/>
Enthält die Position des Cursors relativ zum Bildschirm in Pixel.

### <a name="return-value"></a>Rückgabewert

Der Effekt, der verursacht würde, wenn eine Ablage an der durch *Punkt*angegebenen Position versucht würde. Dabei kann es sich um eine oder mehrere der folgenden handeln:

- DROPEFFECT_NONE Drop wäre nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang ausgeführt wird.

- DROPEFFECT_MOVE ein Verschiebe Vorgang ausgeführt wird.

- DROPEFFECT_LINK eine Verknüpfung von den gelöschten Daten zu den ursprünglichen Daten erstellt werden.

- DROPEFFECT_SCROLL gibt an, dass ein Drag-Scroll-Vorgang stattfindet oder im Ziel auftritt.

### <a name="remarks"></a>Bemerkungen

Überschreiben Sie diese Funktion, wenn Sie ein spezielles Verhalten für dieses Ereignis bereitstellen möchten. Mit der Standard Implementierung dieser Funktion wird [CView:: ondragscroll](../../mfc/reference/cview-class.md#ondragscroll)aufgerufen, die DROPEFFECT_NONE zurückgibt und im Fenster einen Bildlauf durchführt, wenn der Cursor in den Standardbild Laufbereich innerhalb des Fensters gezogen wird.

##  <a name="ondrop"></a>COleDropTarget:: OnDrop

Wird von Framework aufgerufen, wenn ein Ablage Vorgang erfolgen soll.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*folgenden*<br/>
Zeigt auf das Fenster, über dem sich der Cursor zurzeit befindet.

*pDataObject*<br/>
Verweist auf das Datenobjekt, das die Daten enthält, die gelöscht werden sollen.

*dropffect*<br/>
Der Effekt, den der Benutzer für den Drop-Vorgang gewählt hat. Dabei kann es sich um eine oder mehrere der folgenden handeln:

- DROPEFFECT_COPY ein Kopiervorgang ausgeführt wird.

- DROPEFFECT_MOVE ein Verschiebe Vorgang ausgeführt wird.

- DROPEFFECT_LINK eine Verknüpfung von den gelöschten Daten zu den ursprünglichen Daten erstellt werden.

*Punkt*<br/>
Enthält die Position des Cursors relativ zum Bildschirm in Pixel.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Löschvorgang erfolgreich ist. andernfalls 0.

### <a name="remarks"></a>Bemerkungen

Das Framework ruft zuerst [ondropex](#ondropex)auf. Wenn die `OnDropEx`-Funktion den Löschvorgang nicht behandelt, ruft das Framework diese Member-Funktion auf, `OnDrop`. In der Regel überschreibt die Anwendung [ondropex](../../mfc/reference/cview-class.md#ondropex) in der Ansichts Klasse, um die Rechte Drag & amp; Drop der Mauszeiger zu verarbeiten. In der Regel wird die Ansichts Klasse [OnDrop](../../mfc/reference/cview-class.md#ondrop) verwendet, um einfaches Drag & Drop zu verarbeiten.

Die Standard Implementierung von `COleDropTarget::OnDrop` ruft [CView:: OnDrop](../../mfc/reference/cview-class.md#ondrop)auf, das standardmäßig einfach false zurückgibt.

Weitere Informationen finden Sie unter [IDropTarget::D ROP](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) in der Windows SDK.

##  <a name="ondropex"></a>COleDropTarget:: ondropex

Wird von Framework aufgerufen, wenn ein Ablage Vorgang erfolgen soll.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parameter

*folgenden*<br/>
Zeigt auf das Fenster, über dem sich der Cursor zurzeit befindet.

*pDataObject*<br/>
Verweist auf das Datenobjekt, das die Daten enthält, die gelöscht werden sollen.

*dropDefault*<br/>
Der Effekt, den der Benutzer für den Standard Ablage Vorgang basierend auf dem aktuellen Schlüssel Zustand ausgewählt hat. Sie kann DROPEFFECT_NONE werden. Drop Effects werden im Abschnitt "Hinweise" erläutert.

*droplist*<br/>
Eine Liste der Ablage Effekte, die von der Drop-Quelle unterstützt werden. Drop Effect-Werte können mithilfe des bitweisen or ( **&#124;** )-Vorgangs kombiniert werden. Drop Effects werden im Abschnitt "Hinweise" erläutert.

*Punkt*<br/>
Enthält die Position des Cursors relativ zum Bildschirm in Pixel.

### <a name="return-value"></a>Rückgabewert

Der Ablage Effekt, der aus dem Drop-Versuch an der durch *Punkt*angegebenen Position resultiert. Drop Effects werden im Abschnitt "Hinweise" erläutert.

### <a name="remarks"></a>Bemerkungen

Das Framework ruft diese Funktion zuerst auf. Wenn das Drop nicht behandelt wird, ruft das Framework dann [OnDrop](#ondrop)auf. In der Regel überschreiben Sie [ondropex](../../mfc/reference/cview-class.md#ondropex) in der Ansichts Klasse, um die Rechte Drag & Drop-Taste zu unterstützen. In der Regel wird die Ansichts Klasse [OnDrop](../../mfc/reference/cview-class.md#ondrop) verwendet, um die Groß-/Kleinschreibung für das einfache Drag & Drop zu verarbeiten.

Die Standard Implementierung von `COleDropTarget::OnDropEx` die [CView:: ondropex](../../mfc/reference/cview-class.md#ondropex)aufruft. Standardmäßig gibt [CView:: ondropex](../../mfc/reference/cview-class.md#ondropex) einfach einen Dummy-Wert zurück, um anzugeben, dass die [OnDrop](#ondrop) -Member-Funktion aufgerufen werden soll.

Drop Effects beschreibt die Aktion, die einem Drop-Vorgang zugeordnet ist. Weitere Informationen finden Sie in der folgenden Dropdown Liste:

- DROPEFFECT_NONE Drop wäre nicht zulässig.

- DROPEFFECT_COPY ein Kopiervorgang ausgeführt wird.

- DROPEFFECT_MOVE ein Verschiebe Vorgang ausgeführt wird.

- DROPEFFECT_LINK eine Verknüpfung von den gelöschten Daten zu den ursprünglichen Daten erstellt werden.

- DROPEFFECT_SCROLL gibt an, dass ein Drag-Scroll-Vorgang stattfindet oder im Ziel auftritt.

Weitere Informationen finden Sie unter [IDropTarget::D ROP](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) in der Windows SDK.

##  <a name="register"></a>COleDropTarget:: Register

Diese Funktion wird aufgerufen, um das Fenster mit den OLE-DLLs als gültiges Ablage Ziel zu registrieren.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*folgenden*<br/>
Verweist auf das Fenster, das als Ablage Ziel registriert werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Registrierung erfolgreich ist. andernfalls 0.

### <a name="remarks"></a>Bemerkungen

Diese Funktion muss für Drop-Vorgänge aufgerufen werden, um akzeptiert zu werden.

Weitere Informationen finden Sie unter [RegisterDragDrop](/windows/win32/api/ole2/nf-ole2-registerdragdrop) im Windows SDK.

##  <a name="revoke"></a>COleDropTarget:: Widerruf

Diese Funktion wird aufgerufen, bevor ein Fenster zerstört wird, das als Ablage Ziel mithilfe eines Aufrufens registriert wurde [, um es](#register) aus der Liste der Ablage Ziele zu entfernen.

```
virtual void Revoke();
```

### <a name="remarks"></a>Bemerkungen

Diese Funktion wird automatisch vom [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) -Handler für das registrierte Fenster aufgerufen. Daher ist es in der Regel nicht notwendig, diese Funktion explizit aufzurufen.

Weitere Informationen finden Sie unter [revokedragdrop](/windows/win32/api/ole2/nf-ole2-revokedragdrop) in der Windows SDK.

## <a name="see-also"></a>Weitere Informationen

[MFC-Beispiel Hierarchien](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDropSource-Klasse](../../mfc/reference/coledropsource-class.md)
