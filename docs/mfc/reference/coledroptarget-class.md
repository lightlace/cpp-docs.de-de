---
title: COleDropTarget Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb52739977b641cd5d52f018efcd30a51ecf1e32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373132"
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
|[COleDropTarget::OnDragEnter](#ondragenter)|Wird aufgerufen, wenn der Cursor zuerst das Fenster wechselt.|  
|[COleDropTarget::OnDragLeave](#ondragleave)|Wird aufgerufen, wenn der Cursor aus dem Fenster gezogen wird.|  
|[COleDropTarget::OnDragOver](#ondragover)|Wiederholt aufgerufen, wenn der Cursor über dem Fenster gezogen wird.|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|Wird aufgerufen, um festzustellen, ob der Cursor in das Scroll-Bereich des Fensters gezogen wird.|  
|[COleDropTarget::OnDrop](#ondrop)|Wird aufgerufen, wenn Daten in das Fenster und Standardhandler gelöscht werden.|  
|[COleDropTarget::OnDropEx](#ondropex)|Wird aufgerufen, wenn Daten in das Fenster und der erste Ereignishandler gelöscht werden.|  
|[COleDropTarget::Register](#register)|Registerfenster als ein gültiges Ablageziel.|  
|[COleDropTarget::Revoke](#revoke)|Bewirkt, dass das Fenster, um ein gültiges Ablageziel wird eingestellt.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen ein Objekt dieser Klasse können ein Fenster in den Daten über den OLE-Drag & Drop-Mechanismus zu akzeptieren.  
  
 Um ein Fenster zum Annehmen von Drop-Befehlen zu erhalten, sollten Sie zunächst ein Objekt des Erstellen der `COleDropTarget` Klasse, und rufen Sie anschließend die [registrieren](#register) Funktion mit einem Zeiger auf die gewünschte `CWnd` Objekt als einzigem Parameter.  
  
 Weitere Informationen zu Drag-and-Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
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
 Rufen Sie [registrieren](#register) dieses Objekt ein Fenster zugeordnet.  
  
##  <a name="ondragenter"></a>  COleDropTarget::OnDragEnter  
 Vom Framework aufgerufen, wenn der Cursor in das Fenster zuerst gezogen wird.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster den Cursor wird in Betrieb.  
  
 `pDataObject`  
 Verweist auf das Datenobjekt, das mit den Daten, die gelöscht werden können.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Enthält die aktuelle Position des Cursors in Clientkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkungen, die auftreten würden, wenn ein solches löschen, an der vom angegebenen Position versucht wurden `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE` Ein solches löschen, ist nicht zulässig.  
  
- `DROPEFFECT_COPY` Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE` Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK` Eine Verknüpfung aus dem gelöschten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL` Ein Ziehvorgangs ein Bildlauf durchgeführt wird oder im Ziel auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um Drop-Vorgänge im Fenster auftreten können. Die Standardimplementierung ruft [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), welche gibt einfach `DROPEFFECT_NONE` standardmäßig.  
  
 Weitere Informationen finden Sie unter [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) im Windows SDK.  
  
##  <a name="ondragleave"></a>  COleDropTarget::OnDragLeave  
 Vom Framework aufgerufen, wenn der Cursor im Fenster verlässt, während ein Ziehvorgang ausgeführt wird.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster den Cursor verlässt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn besonderes Verhalten soll, wenn des Ziehvorgangs des angegebenen Fensters verlässt. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).  
  
 Weitere Informationen finden Sie unter [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) im Windows SDK.  
  
##  <a name="ondragover"></a>  COleDropTarget::OnDragOver  
 Wird vom Framework aufgerufen, wenn der Cursor über dem Fenster gezogen wird.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster, dem der Cursor über befindet.  
  
 `pDataObject`  
 Verweist auf das Datenobjekt, das die Daten, die gelöscht werden sollen.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Enthält die aktuelle Position des Cursors in Clientkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkungen, die auftreten würden, wenn ein solches löschen, an der vom angegebenen Position versucht wurden `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE` Ein solches löschen, ist nicht zulässig.  
  
- `DROPEFFECT_COPY` Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE` Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK` Eine Verknüpfung aus dem gelöschten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL` Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird, oder im Ziel auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte überschrieben werden, damit Drop-Vorgänge im Fenster auftreten können. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), welche gibt `DROPEFFECT_NONE` standardmäßig. Da diese Funktion häufig während eines Drag & Drop-Vorgangs aufgerufen wird, sollten sie so weit wie möglich optimiert.  
  
 Weitere Informationen finden Sie unter [IDropTarget:: DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="ondragscroll"></a>  COleDropTarget::OnDragScroll  
 Wird aufgerufen, durch das Framework vor dem Aufruf [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) um zu bestimmen, ob `point` befindet sich im Bildlaufbereich.  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster den Cursor ist derzeit über.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Enthält die Position des Cursors in Pixel relativ zu dem Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkungen, die auftreten würden, wenn ein solches löschen, an der vom angegebenen Position versucht wurden `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE` Ein solches löschen, ist nicht zulässig.  
  
- `DROPEFFECT_COPY` Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE` Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK` Eine Verknüpfung aus dem gelöschten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL` Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird, oder im Ziel auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie spezielle Verhaltensweisen für dieses Ereignis bereitstellen möchten. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), welche gibt `DROPEFFECT_NONE` und verschiebt das Fenster, wenn der Cursor in der Standardeinstellung Bildlaufbereich den Rand des Fensters gezogen wird.  
  
##  <a name="ondrop"></a>  COleDropTarget::OnDrop  
 Durch das Framework aufgerufen, wenn eine Drop-Vorgangs auftreten.  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster den Cursor ist derzeit über.  
  
 `pDataObject`  
 Verweist auf das Datenobjekt, das die Daten, die gelöscht werden sollen.  
  
 `dropEffect`  
 Die Auswirkungen, die der Benutzer für den Löschvorgang ausgewählt haben. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_COPY` Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE` Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK` Eine Verknüpfung aus dem gelöschten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
 `point`  
 Enthält die Position des Cursors in Pixel relativ zu dem Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie der Löschvorgang erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft zunächst [OnDropEx](#ondropex). Wenn die `OnDropEx` Funktion behandelt nicht das Dropdownmenü, das Framework ruft dann diese Memberfunktion `OnDrop`. Die Anwendung in der Regel überschreibt [OnDropEx](../../mfc/reference/cview-class.md#ondropex) in Ansichtsklasse Rechte Maustaste behandeln Drag & drop. In der Regel die Ansichtsklasse [OnDrop](../../mfc/reference/cview-class.md#ondrop) wird verwendet, um einfache Drag & Drop zu behandeln.  
  
 Die standardmäßige Implementierung des `COleDropTarget::OnDrop` Aufrufe [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), welche gibt einfach **"false"** standardmäßig.  
  
 Weitere Informationen finden Sie unter [IDropTarget:: Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) im Windows SDK.  
  
##  <a name="ondropex"></a>  COleDropTarget::OnDropEx  
 Durch das Framework aufgerufen, wenn eine Drop-Vorgangs auftreten.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster den Cursor ist derzeit über.  
  
 `pDataObject`  
 Verweist auf das Datenobjekt, das die Daten, die gelöscht werden sollen.  
  
 `dropDefault`  
 Die Auswirkungen, die für die Standard-Drop-Vorgang basierend auf den aktuellen Status der Benutzer ausgewählt haben. Es kann sein `DROPEFFECT_NONE`. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.  
  
 `dropList`  
 Eine Liste der Drop-Effekte, die die Drop-Quelle unterstützt. Drop-Effekt-Werte können mit dem bitweisen OR kombiniert werden ( **&#124;**) Vorgang. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.  
  
 `point`  
 Enthält die Position des Cursors in Pixel relativ zu dem Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Drop-Effekt, die aus der Drop-Versuch, an der vom angegebenen Position resultieren `point`. Drop-Effekte werden im Abschnitt "Hinweise" erläutert.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft zuerst diese Funktion. Wenn sie den Löschvorgang nicht verarbeiten kann, ruft das Framework dann [OnDrop](#ondrop). Setzen Sie in der Regel [OnDropEx](../../mfc/reference/cview-class.md#ondropex) in Ansichtsklasse zur Unterstützung der rechten Maustaste ziehen und ablegen. In der Regel die Ansichtsklasse [OnDrop](../../mfc/reference/cview-class.md#ondrop) wird verwendet, um die Groß-/Kleinschreibung Unterstützung für einfache Drag & Drop zu behandeln.  
  
 Die standardmäßige Implementierung des `COleDropTarget::OnDropEx` Aufrufe [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). Standardmäßig [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) gibt einfach einen Dummywert an, dass die [OnDrop](#ondrop) Memberfunktion aufgerufen werden.  
  
 Drop-Effekte beschreiben die Aktion ein Drop-Vorgang zugeordnet ist. Die folgende Liste von Drop-Effekte finden Sie in:  
  
- `DROPEFFECT_NONE` Ein solches löschen, ist nicht zulässig.  
  
- `DROPEFFECT_COPY` Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE` Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK` Eine Verknüpfung aus dem gelöschten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL` Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird, oder im Ziel auftritt.  
  
 Weitere Informationen finden Sie unter [IDropTarget:: Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) im Windows SDK.  
  
##  <a name="register"></a>  COleDropTarget::Register  
 Rufen Sie diese Funktion, um das Fenster für die OLE-DLLs als ein gültiges Ablageziel zu registrieren.  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster, das als Ablageziel registriert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Registrierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion muss für Drop-Vorgänge zu akzeptierende aufgerufen werden.  
  
 Weitere Informationen finden Sie unter [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) im Windows SDK.  
  
##  <a name="revoke"></a>  COleDropTarget::Revoke  
 Mit dieser Funktion wird vor der Zerstörung ein Fenster, das als Ablageziel durch einen Aufruf von registriert wurde [registrieren](#register) um sie aus der Liste der Ablageziele zu entfernen.  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird automatisch aufgerufen, aus der [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) Handler für das Fenster, das registriert wurde, daher ist es in der Regel nicht notwendig, diese Funktion explizit aufrufen,.  
  
 Weitere Informationen finden Sie unter [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDropSource-Klasse](../../mfc/reference/coledropsource-class.md)
