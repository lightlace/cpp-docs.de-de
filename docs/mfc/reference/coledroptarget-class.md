---
title: COleDropTarget Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropTarget
dev_langs:
- C++
helpviewer_keywords:
- COleDropTarget class
- drag and drop, drop target
- drop commands, accepting
- drop commands
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0e9429d531d6af86bc571b1f871fbcd4a8fe2532
ms.lasthandoff: 02/24/2017

---
# <a name="coledroptarget-class"></a>COleDropTarget-Klasse
Stellt den Kommunikationsmechanismus zwischen einem Fenster und den OLE-Bibliotheken bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](#coledroptarget)|Erstellt ein `COleDropTarget`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](#ondragenter)|Wird aufgerufen, wenn der Cursor zuerst das Fenster betritt.|  
|[COleDropTarget::OnDragLeave](#ondragleave)|Wird aufgerufen, wenn der Cursor über das Fenster gezogen wird.|  
|[COleDropTarget::OnDragOver](#ondragover)|Wiederholt aufgerufen, wenn der Cursor über dem Fenster gezogen wird.|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|Wird aufgerufen, um festzustellen, ob der Cursor in der Bildlaufbereich des Fensters gezogen wird.|  
|[COleDropTarget::OnDrop](#ondrop)|Wird aufgerufen, wenn Daten im Fenster Standardhandler gelöscht werden.|  
|[COleDropTarget::OnDropEx](#ondropex)|Wird aufgerufen, wenn Daten im Fenster ersten Ereignishandler gelöscht werden.|  
|[COleDropTarget::Register](#register)|Wird das Fenster als ein gültiges Ablageziel registriert.|  
|[COleDropTarget::Revoke](#revoke)|Bewirkt, dass das Fenster wird ein gültiges Ablageziel beendet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen ein Objekt dieser Klasse können ein Fenster für die Aufnahme von Daten über den OLE-Drag & Drop-Mechanismus.  
  
 Um ein Fenster zum Annehmen von Drop-Befehlen zu erhalten, erstellen Sie zunächst ein Objekt der `COleDropTarget` Klasse, und rufen Sie dann die [registrieren](#register) Funktion mit einem Zeiger auf die gewünschte `CWnd` Objekt als einzigen Parameter.  
  
 Weitere Informationen zu Drag & Drop-Vorgängen mithilfe von OLE, finden Sie im Artikel [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="a-namecoledroptargeta--coledroptargetcoledroptarget"></a><a name="coledroptarget"></a>COleDropTarget::COleDropTarget  
 Erstellt ein Objekt der Klasse `COleDropTarget`.  
  
```  
COleDropTarget();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [registrieren](#register) ein Fenster dieses Objekt zugeordnet.  
  
##  <a name="a-nameondragentera--coledroptargetondragenter"></a><a name="ondragenter"></a>COleDropTarget::OnDragEnter  
 Wird vom Framework aufgerufen, wenn der Cursor zuerst in das Fenster gezogen wird.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster des Cursors ist eingeben.  
  
 `pDataObject`  
 Verweist auf das Datenobjekt mit den Daten, die gelöscht werden können.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Enthält die aktuelle Position des Cursors in Clientkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkung, die entstehen, wenn ein Ablegen am angegebenen Speicherort versuchten `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`Eine Drop würde nicht zugelassen werden.  
  
- `DROPEFFECT_COPY`Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus der abgelegten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Ein Ziehvorgangs ein Bildlauf durchgeführt wird oder im Ziel stattfindet.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Drop-Vorgänge im Fenster auftreten können. Die standardmäßige Implementierung ruft [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), welche gibt einfach die `DROPEFFECT_NONE` standardmäßig.  
  
 Weitere Informationen finden Sie unter [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameondragleavea--coledroptargetondragleave"></a><a name="ondragleave"></a>COleDropTarget::OnDragLeave  
 Vom Framework aufgerufen, wenn der Cursor über das Fenster verlässt, während ein Drag & Drop-Vorgangs ausgeführt wird.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster den Cursor werden beibehalten.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn besonderes Verhalten, sollen Wenn der Ziehvorgang das angegebene Fenster verlässt. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).  
  
 Weitere Informationen finden Sie unter [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameondragovera--coledroptargetondragover"></a><a name="ondragover"></a>COleDropTarget::OnDragOver  
 Wird vom Framework aufgerufen, wenn der Cursor über das Fenster gezogen wird.  
  
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
 Verweist auf das Objekt mit den Daten gelöscht werden.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Enthält die aktuelle Position des Cursors in Clientkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkung, die entstehen, wenn ein Ablegen am angegebenen Speicherort versuchten `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`Eine Drop würde nicht zugelassen werden.  
  
- `DROPEFFECT_COPY`Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus der abgelegten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird oder im Ziel stattfindet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte überschrieben werden, damit Drop-Vorgänge im Fenster auftreten können. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), welche gibt `DROPEFFECT_NONE` standardmäßig. Da diese Funktion häufig während eines Drag & Drop-Vorgangs aufgerufen wird, sollten sie möglichst viele optimiert werden.  
  
 Weitere Informationen finden Sie unter [IDropTarget:: DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&21;](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="a-nameondragscrolla--coledroptargetondragscroll"></a><a name="ondragscroll"></a>COleDropTarget::OnDragScroll  
 Vor dem Aufruf aufgerufen [OnDragEnter](#ondragenter) oder [OnDragOver](#ondragover) um zu bestimmen, ob `point` im Bildlaufbereich ist.  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster der Cursor derzeit befindet.  
  
 `dwKeyState`  
 Enthält den Status der Zusatztasten. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, und **MK_RBUTTON**.  
  
 `point`  
 Enthält den Speicherort des Cursors in Pixel relativ zum Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkung, die entstehen, wenn ein Ablegen am angegebenen Speicherort versuchten `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`Eine Drop würde nicht zugelassen werden.  
  
- `DROPEFFECT_COPY`Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus der abgelegten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird oder im Ziel stattfindet.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie für dieses Ereignis ein besonderes Verhalten bereitstellen möchten. Ruft die standardmäßige Implementierung dieser Funktion [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), welche gibt `DROPEFFECT_NONE` und führt einen Bildlauf im Fenster, wenn der Cursor in der Standardeinstellung Bildlaufbereich den Rand des Fensters gezogen wird.  
  
##  <a name="a-nameondropa--coledroptargetondrop"></a><a name="ondrop"></a>COleDropTarget::OnDrop  
 Wird vom Framework aufgerufen, wenn eine Drop-Operation ausgeführt werden soll.  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster der Cursor derzeit befindet.  
  
 `pDataObject`  
 Verweist auf das Objekt mit den Daten gelöscht werden.  
  
 `dropEffect`  
 Der Effekt, den der Benutzer für den Löschvorgang ausgewählt haben. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_COPY`Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus der abgelegten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
 `point`  
 Enthält den Speicherort des Cursors in Pixel relativ zum Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Dropdownliste erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft zuerst [OnDropEx](#ondropex). Wenn die `OnDropEx` Funktion behandelt nicht die Dropdownliste, die das Framework ruft dann diese Memberfunktion `OnDrop`. Die Anwendung in der Regel überschreibt [OnDropEx](../../mfc/reference/cview-class.md#ondropex) in der Ansichtsklasse, behandeln Rechte Maustaste Drag & drop. In der Regel die Ansichtsklasse [OnDrop](../../mfc/reference/cview-class.md#ondrop) zum einfachen Drag & Drop zu behandeln.  
  
 Die standardmäßige Implementierung des `COleDropTarget::OnDrop` Aufrufe [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), welche gibt einfach **FALSE** standardmäßig.  
  
 Weitere Informationen finden Sie unter [IDropTarget:: Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameondropexa--coledroptargetondropex"></a><a name="ondropex"></a>COleDropTarget::OnDropEx  
 Wird vom Framework aufgerufen, wenn eine Drop-Operation ausgeführt werden soll.  
  
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
 Verweist auf das Fenster der Cursor derzeit befindet.  
  
 `pDataObject`  
 Verweist auf das Objekt mit den Daten gelöscht werden.  
  
 `dropDefault`  
 Der Effekt, den für die Standard-Drop-Vorgang basierend auf den aktuellen Status der Benutzer ausgewählt hat. Es kann sein `DROPEFFECT_NONE`. Drop-Effekte werden im Abschnitt Hinweise erläutert.  
  
 `dropList`  
 Eine Liste der Drop-Effekte, die die Quelle unterstützt. Drop Effektwerte können kombiniert werden, mit dem bitweisen OR ( **|**) Vorgang. Drop-Effekte werden im Abschnitt Hinweise erläutert.  
  
 `point`  
 Enthält den Speicherort des Cursors in Pixel relativ zum Bildschirm.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Drop-Effekt, die aus der Löschversuch am angegebenen Speicherort resultieren `point`. Drop-Effekte werden im Abschnitt Hinweise erläutert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zuerst aufgerufen. Wenn sie den Löschvorgang nicht behandelt wird, ruft das Framework dann [OnDrop](#ondrop). In der Regel überschreiben [OnDropEx](../../mfc/reference/cview-class.md#ondropex) in der Ansichtsklasse zur Unterstützung der rechten Maustaste Drag & drop. In der Regel die Ansichtsklasse [OnDrop](../../mfc/reference/cview-class.md#ondrop) wird verwendet, um die Behandlung der Unterstützung für einfache Drag & Drop.  
  
 Die standardmäßige Implementierung des `COleDropTarget::OnDropEx` Aufrufe [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). In der Standardeinstellung [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) gibt einfach einen dummy-Wert an, dass die [OnDrop](#ondrop) -Memberfunktion aufgerufen werden.  
  
 Drop-Effekte beschrieben, die ein Drop-Vorgang zugeordnete Aktion. Die folgende Liste der Drop-Effekte angezeigt:  
  
- `DROPEFFECT_NONE`Eine Drop würde nicht zugelassen werden.  
  
- `DROPEFFECT_COPY`Ein Kopiervorgang würde ausgeführt werden.  
  
- `DROPEFFECT_MOVE`Ein Verschiebevorgang würde ausgeführt werden.  
  
- `DROPEFFECT_LINK`Eine Verknüpfung aus der abgelegten Daten auf die ursprünglichen Daten würde hergestellt werden.  
  
- `DROPEFFECT_SCROLL`Gibt an, dass ein Ziehvorgangs ein Bildlauf durchgeführt wird oder im Ziel stattfindet.  
  
 Weitere Informationen finden Sie unter [IDropTarget:: Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameregistera--coledroptargetregister"></a><a name="register"></a>COleDropTarget::Register  
 Rufen Sie diese Funktion, um das Fenster mit der OLE-DLLs als ein gültiges Ablageziel zu registrieren.  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf das Fenster, das als Dropziel registriert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Registrierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion muss für Drop-Vorgänge zu akzeptierende aufgerufen werden.  
  
 Weitere Informationen finden Sie unter [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namerevokea--coledroptargetrevoke"></a><a name="revoke"></a>COleDropTarget::Revoke  
 Rufen Sie diese Funktion vor der Zerstörung von einem beliebigen Fenster, das als Ablageziel durch einen Aufruf von registriert wurde [registrieren](#register) um sie aus der Liste der Dropziele zu entfernen.  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird automatisch aufgerufen, von der [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) Handler für das Fenster, das registriert wurde, daher ist es normalerweise nicht erforderlich, diese Funktion explizit aufzurufen,.  
  
 Weitere Informationen finden Sie unter [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDropSource-Klasse](../../mfc/reference/coledropsource-class.md)

