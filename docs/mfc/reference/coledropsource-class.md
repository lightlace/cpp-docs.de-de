---
title: COleDropSource Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
dev_langs:
- C++
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e510811fcaac81aa54699250ef37f48ffe1f40e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="coledropsource-class"></a>COleDropSource-Klasse
Können Daten auf ein Ablageziel gezogen werden.  
  
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
|[COleDropSource::GiveFeedback](#givefeedback)|Ändert sich der Cursor während eines Drag & Drop-Vorgangs ein.|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|Verarbeitet die Mausauswahl während eines Drag & Drop-Vorgangs.|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Überprüft, ob ziehen sollten weiterhin.|  
  
## <a name="remarks"></a>Hinweise  
 Die [COleDropTarget](../../mfc/reference/coledroptarget-class.md) Klasse behandelt den empfangenden Teil des Drag & Drop-Vorgangs. Die `COleDropSource` -Objekt ist verantwortlich für das ermitteln, wenn ein Ziehvorgang begonnen und Bereitstellen von Feedback während des Ziehvorgangs bestimmen, wann der Ziehvorgang endet.  
  
 Verwenden einer `COleDropSource` Objekt, rufen Sie einfach den Konstruktor. Dies vereinfacht den Prozess der Beurteilung, welche Ereignisse, z. B. ein Mausklick Starten einer Drag-Vorgang mit [Oledatasource](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), oder [ COleServerItem:: DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) Funktion. Diese Funktionen erstellt einen `COleDropSource` Objekt für Sie. Möglicherweise möchten Sie das Standardverhalten ändern die `COleDropSource` überschreibbare-Funktionen. Diese Memberfunktionen werden vom Framework zu den entsprechenden Zeitpunkten aufgerufen.  
  
 Weitere Informationen zu Drag-and-Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Weitere Informationen finden Sie unter [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) im Windows SDK.  
  
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
 Vom Framework aufgerufen wird, nach dem Aufruf [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) oder [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `dropEffect`  
 Den Effekt, der dem Benutzer angezeigt werden sollen, in der Regel, der angibt, was passiert, wenn ein solches Löschen an diesem Punkt mit den ausgewählten Daten aufgetreten ist. Dies ist in der Regel vom letzten Aufruf zurückgegebene Wert [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) oder [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE` Ein solches löschen, ist nicht zulässig.  
  
- `DROPEFFECT_COPY` Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE` Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK` Eine Verknüpfung aus dem gelöschten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL` Ein Ziehvorgangs ein Bildlauf durchgeführt wird oder im Ziel auftritt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **DRAGDROP_S_USEDEFAULTCURSORS** Wenn ziehen ausgeführt wird, wird **NOERROR** wird jedoch nicht.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Bereitstellen von Feedback für den Benutzer zu, was passieren würde, wenn ein solches Löschen zu diesem Zeitpunkt aufgetreten ist. Die Standardimplementierung verwendet die OLE-Standardcursor an. Weitere Informationen zu Drag-and-Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Weitere Informationen finden Sie unter [IDropSource::GiveFeedback](http://msdn.microsoft.com/library/windows/desktop/ms693723), [IDropTarget:: DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129), und [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) im Windows SDK.  
  
##  <a name="onbegindrag"></a>  COleDropSource::OnBeginDrag  
 Wird aufgerufen, durch das Framework beim Eintreten eines Ereignisses ein Ziehvorgangs, z. B. die linke Maustaste drückt beginnen konnte.  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster, das die ausgewählten Daten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ziehen zulässig ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion ggf. ändern, wenn das Ziehen Prozess gestartet wird. Die standardmäßige Implementierung erfasst die Maus und bleibt im Ziehmodus, bis der Benutzer klickt auf die linke oder rechte Maustaste gedrückt oder Treffer ESC, woraufhin sie die Maustaste loslässt.  
  
##  <a name="querycontinuedrag"></a>  COleDropSource::QueryContinueDrag  
 Nach dem Ziehen begonnen hat, wird diese Funktion vom Framework wiederholt aufgerufen, bis der Ziehvorgang abgebrochen oder beendet wird.  
  
```  
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed, 
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>Parameter  
 *bEscapePressed*  
 Gibt an, ob die ESC-Taste seit dem letzten Aufruf von gedrückt wurde `COleDropSource::QueryContinueDrag`.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten der Tastatur. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, und **MK_RBUTTON**.  
  
### <a name="return-value"></a>Rückgabewert  
 **DRAGDROP_S_CANCEL** Wenn die ESC-Taste oder die rechte Maustaste gedrückt wird, oder die linke Maustaste vor dem Ziehen beginnt ausgelöst. **DRAGDROP_S_DROP** , wenn ein Drop-Vorgang ausgeführt werden soll. Andernfalls `S_OK`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben, die diese Funktion, wenn Sie die Stelle, an welche Ziehen ändern möchten abgebrochen wird oder einen Löschvorgang erfolgt.  
  
 Die standardmäßige Implementierung initiiert die Dropdownliste oder bricht ab der Ziehvorgang wie folgt. Ziehen Sie-Vorgang abgebrochen wird, wenn die ESC-Taste oder die rechte Maustaste gedrückt wird. Initialisiert einen Drop-Vorgang, wenn die linke Maustaste gedrückt ausgelöst wird, nachdem Sie ziehen gestartet wurde. Andernfalls wird zurückgegeben `S_OK` und keine weiteren Vorgänge ausführt.  
  
 Da diese Funktion häufig aufgerufen wird, sollten sie so weit wie möglich optimiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



