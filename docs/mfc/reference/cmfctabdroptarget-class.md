---
title: CMFCTabDropTarget Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff17f7312f5e04b6ae900e792523155705a3b4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget-Klasse
Stellt den Kommunikationsmechanismus zwischen einem Registerkarten-Steuerelement und den OLE-Bibliotheken bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|Vom Framework aufgerufen, wenn der Benutzer ein Objekt in einem Registerkartenfenster zieht. (Überschreibt [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt außerhalb des Fensters Registerkarte zieht, den Fokus besitzt. (Überschreibt [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt in der "Verwaltung" zieht, den Fokus besitzt. (Überschreibt [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt, die am Ende eines Ziehvorgangs ein. (Überschreibt [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|  
|[CMFCTabDropTarget::Register](#register)|Registriert das Steuerelement als ein Feld, das das Ziel eines OLE-Drag & Drop-Vorgangs verwendet werden kann.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse bietet Drag-and-Drop-Support, um die `CMFCBaseTabCtrl` Klasse. Wenn Ihre Anwendung mithilfe die OLE-Bibliotheken initialisiert die [AfxOleInit](ole-initialization.md#afxoleinit) Funktion `CMFCBaseTabCtrl` Objekte, registrieren Sie sich für Drag & Drop-Vorgänge.  
  
 Die `CMFCTabDropTarget` Klasse erweitert die Basisklasse, indem Sie die Registerkarte, unter dem Cursor befindet, tritt ein Ziehvorgang aktiv, machen. Weitere Informationen über Drag & Drop-Vorgänge finden Sie unter [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCTabDropTarget`-Objekts und die Verwendung der `Register`-Methode.  
  
 [!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbasetabctrl.h  
  
##  <a name="ondragenter"></a>CMFCTabDropTarget::OnDragEnter  
 Vom Framework aufgerufen, wenn der Benutzer ein Objekt in einem Registerkartenfenster zieht.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pWnd`|Nicht verwendet.|  
|[in] `pDataObject`|Ein Zeiger auf das Objekt, das der Benutzer zieht.|  
|[in] `dwKeyState`|Enthält den Status der Zusatztasten. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, und `MK_RBUTTON`.|  
|[in] `point`|Die Position des Cursors in Clientkoordinaten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkungen, die sich ergibt, erfolgt die Dropdownliste am vom angegebenen Speicherort `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `DROPEFFECT_NONE` , wenn die Symbolleiste-Framework nicht im Anpassungsmodus ist oder das Datenformat der Zwischenablage nicht verfügbar ist. Andernfalls wird das Ergebnis des Aufrufs zurückgegeben `CMFCBaseTabCtrl::OnDragEnter` mit den angegebenen Parametern.  
  
 Weitere Informationen zu Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu zwischenablagedatenformate, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="ondragleave"></a>CMFCTabDropTarget::OnDragLeave  
 Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt außerhalb des Fensters Registerkarte zieht, den Fokus besitzt.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pWnd`|Nicht verwendet.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die `CMFCBaseTabCtrl::OnDragLeave` Methode zum Ausführen des Ziehvorgangs.  
  
##  <a name="ondragover"></a>CMFCTabDropTarget::OnDragOver  
 Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt in der "Verwaltung" zieht, den Fokus besitzt.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pWnd`|Nicht verwendet.|  
|[in] `pDataObject`|Ein Zeiger auf das Objekt, das der Benutzer zieht.|  
|[in] `dwKeyState`|Enthält den Status der Zusatztasten. Dies ist eine Kombination einer beliebigen Anzahl von Folgendes: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, und `MK_RBUTTON`.|  
|[in] `point`|Die Position des Mauszeigers in Clientkoordinaten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkungen, die sich ergibt, erfolgt die Dropdownliste am vom angegebenen Speicherort `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Hinweise  
 Bei dieser Methode ist die Registerkarte, die unter dem Cursor befindet, tritt ein Ziehvorgang aktiv. Es gibt `DROPEFFECT_NONE` , wenn die Symbolleiste-Framework nicht im Anpassungsmodus ist oder das Datenformat der Zwischenablage nicht verfügbar ist. Andernfalls wird das Ergebnis des Aufrufs zurückgegeben `CMFCBaseTabCtrl::OnDragOver` mit den angegebenen Parametern.  
  
 Weitere Informationen zu Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu zwischenablagedatenformate, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="ondropex"></a>CMFCTabDropTarget::OnDropEx  
 Vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt, die am Ende eines Ziehvorgangs ein.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pWnd`|Nicht verwendet.|  
|[in] `pDataObject`|Ein Zeiger auf das Objekt, das der Benutzer zieht.|  
|[in] `dropEffect`|Der Standard-Drop-Vorgang.|  
|[in] `dropList`|Nicht verwendet.|  
|[in] `point`|Die Position des Mauszeigers in Clientkoordinaten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die resultierende Drop-Effekt. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft `CMFCBaseTabCtrl::OnDrop` Wenn die Symbolleiste-Framework im Anpassungsmodus ist und das Datenformat der Zwischenablage verfügbar ist. Wenn der Aufruf von `CMFCBaseTabCtrl::OnDrop` gibt ein Wert ungleich NULL, diese Methode die Standard-Drop-Effekt gemäß gibt `dropEffect`. Diese Methode hingegen gibt `DROPEFFECT_NONE`. Weitere Informationen über die Drop-Effekte finden Sie unter [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).  
  
 Weitere Informationen zu Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu zwischenablagedatenformate, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="register"></a>CMFCTabDropTarget::Register  
 Registriert das Steuerelement als ein Feld, das das Ziel eines OLE-Drag & Drop-Vorgangs verwendet werden kann.  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pOwner`|Das Registerkarten-Steuerelement als Ablageziel registriert werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Registrierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) zum Registrieren des Steuerelements für Drag & Drop-Vorgänge.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md)



