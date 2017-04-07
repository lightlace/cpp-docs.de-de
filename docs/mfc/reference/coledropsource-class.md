---
title: Klasse COleDropSource | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- drag operations
- drop target, dragging data to
- COleDropSource class
- drag and drop, drop source
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f3d0e5b7184cf305459173065b8e1cc07e032aef
ms.lasthandoff: 02/24/2017

---
# <a name="coledropsource-class"></a>COleDropSource-Klasse
Können Daten auf ein Ablageziel gezogen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](#coledropsource)|Erstellt ein `COleDropSource`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](#givefeedback)|Wird der Cursor während eines Drag & Drop-Vorgangs.|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|Verarbeitet die Mausauswahl während eines Drag & Drop-Vorgangs.|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Überprüft, ob ziehen sollten weiterhin.|  
  
## <a name="remarks"></a>Hinweise  
 Die [COleDropTarget](../../mfc/reference/coledroptarget-class.md) Klasse behandelt den empfangenden Teil der Drag & Drop-Vorgang. Das `COleDropSource` -Objekt ist verantwortlich für bestimmen, wann ein Ziehvorgang begonnen und Senden von Feedback während des Ziehvorgangs bestimmen, wenn der Ziehvorgang beendet.  
  
 Verwenden einer `COleDropSource` -Objekt, rufen Sie einfach den Konstruktor. Dies vereinfacht den Prozess zur Bestimmung, welche Ereignisse, z. B. einen Mausklick eine Drag-Vorgang mit beginnen [Ablagequellenobjekt](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), oder [COleServerItem:: DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) Funktion. Diese Funktionen erstellt einen `COleDropSource` -Objekt für Sie. Sie können das Standardverhalten ändern möchten die `COleDropSource` überschreibbare-Funktionen. Diese Memberfunktionen werden bei Bedarf vom Framework aufgerufen werden.  
  
 Weitere Informationen zu Drag & Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Weitere Informationen finden Sie unter [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="coledropsource"></a>COleDropSource::COleDropSource  
 Erstellt ein `COleDropSource`-Objekt.  
  
```  
COleDropSource();
```  
  
##  <a name="givefeedback"></a>COleDropSource::GiveFeedback  
 Vom Framework aufgerufen wird, nach dem Aufruf von [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) oder [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>Parameter  
 `dropEffect`  
 Der Effekt, der dem Benutzer angezeigt werden soll, in der Regel, der angibt, was geschieht, wenn ein Ablegen an diesem Punkt mit den ausgewählten Daten aufgetreten ist. Dies ist normalerweise der vom letzten Aufruf zurückgegebene Wert [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) oder [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`Eine Drop würde nicht zugelassen werden.  
  
- `DROPEFFECT_COPY`Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus der abgelegten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Ein Ziehvorgangs ein Bildlauf durchgeführt wird oder im Ziel stattfindet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **DRAGDROP_S_USEDEFAULTCURSORS** Wenn das Ziehen in Bearbeitung ist **NOERROR** ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um Feedback zu den Benutzer über was geschieht, wenn ein ablegen zu diesem Zeitpunkt aufgetreten sind. Die standardmäßige Implementierung verwendet die OLE-Standardcursor. Weitere Informationen zu Drag & Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Weitere Informationen finden Sie unter [IDropSource::GiveFeedback](http://msdn.microsoft.com/library/windows/desktop/ms693723), [IDropTarget:: DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129), und [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onbegindrag"></a>COleDropSource::OnBeginDrag  
 Aufgerufen durch das Framework beim Eintreten eines Ereignisses ein Ziehvorgangs, z. B. durch Drücken der linken Maustaste beginnen kann.  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster, das die ausgewählten Daten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ziehen zulässig ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion ggf. ändern, wenn die Drag & Drop-Vorgang gestartet wird. Die standardmäßige Implementierung die Maus erfasst und in den Dragmodus bleibt, bis der Benutzer die linke oder rechte Maustaste klickt oder Treffer ESC, wobei sie die Maustaste loslässt.  
  
##  <a name="querycontinuedrag"></a>COleDropSource::QueryContinueDrag  
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
 Enthält den Status der Zusatztasten der Tastatur. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, und **MK_RBUTTON**.  
  
### <a name="return-value"></a>Rückgabewert  
 **DRAGDROP_S_CANCEL** Wenn die ESC-Taste oder die rechte Maustaste gedrückt wird oder linke Maustaste ausgelöst wird, bevor das Ziehen beginnt. **DRAGDROP_S_DROP** Wenn eine Drop-Operation ausgeführt werden soll. Andernfalls `S_OK`.  
  
### <a name="remarks"></a>Hinweise  
 Außer Kraft setzen, die diese Funktion, wenn Sie den Punkt, an dem das Ziehen ändern möchten abgebrochen wird oder eine Drop erfolgt.  
  
 Die standardmäßige Implementierung initiiert die Dropdownliste oder bricht wie folgt das ziehen. Einen Drag-Vorgang abgebrochen wird, wenn die ESC-Taste oder die rechte Maustaste gedrückt wird. Er initiiert einen Drop-Vorgang, wenn die linke Maustaste ausgelöst wird, nachdem ziehen gestartet wurde. Andernfalls gibt es `S_OK` und keine weiteren Vorgänge ausführt.  
  
 Da diese Funktion häufig aufgerufen wird, sollten sie möglichst viele optimiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




