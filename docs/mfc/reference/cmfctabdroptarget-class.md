---
title: Klasse CMFCTabDropTarget | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget class
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
caps.latest.revision: 22
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
ms.openlocfilehash: 31f9950df5974fe1561d601d4e9c26b3e8a96a62
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget-Klasse
Stellt den Kommunikationsmechanismus zwischen einem Registerkarten-Steuerelement und die OLE-Bibliotheken bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt in einem Registerkartenfenster zieht. (Überschreibt [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt außerhalb des Fensters Registerkarte zieht, den Fokus besitzt. (Überschreibt [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt auf der Registerkartenfenster zieht, den Fokus besitzt. (Überschreibt [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|Wird vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt, die am Ende eines Ziehvorgangs ein. (Überschreibt [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|  
|[CMFCTabDropTarget::Register](#register)|Registriert das Steuerelement als eines, das das Ziel einer OLE-Drag & Drop-Operation sein kann.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse stellt die Drag & Drop-Unterstützung für die `CMFCBaseTabCtrl` Klasse. Wenn Ihre Anwendung initialisiert wird die OLE-Bibliotheken mithilfe der [AfxOleInit](ole-initialization.md#afxoleinit) Funktion `CMFCBaseTabCtrl` Objekte registrieren sich für Drag & Drop-Vorgänge.  
  
 Die `CMFCTabDropTarget` Klasse erweitert die Basisklasse, indem Sie die Registerkarte, die unter dem Cursor befindet, tritt ein Ziehvorgang active machen. Weitere Informationen über Drag & Drop-Vorgänge finden Sie unter [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCTabDropTarget`-Objekts und die Verwendung der `Register`-Methode.  
  
 [!code-cpp[NVC_MFC_RibbonApp Nr.&39;](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbasetabctrl.h  
  
##  <a name="a-nameondragentera--cmfctabdroptargetondragenter"></a><a name="ondragenter"></a>CMFCTabDropTarget::OnDragEnter  
 Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt in einem Registerkartenfenster zieht.  
  
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
|[in] `dwKeyState`|Enthält den Status der Zusatztasten. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, und `MK_RBUTTON`.|  
|[in] `point`|Die Position des Cursors in Clientkoordinaten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkung, die sich ergibt, tritt die Dropdownliste am angegebenen Speicherort `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `DROPEFFECT_NONE` ist das Framework Symbolleiste nicht im Anpassungsmodus oder das Datenformat der Zwischenablage nicht verfügbar ist. Andernfalls wird das Ergebnis des Aufrufs zurückgegeben `CMFCBaseTabCtrl::OnDragEnter` mit den bereitgestellten Parametern.  
  
 Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu zwischenablagedatenformate, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="a-nameondragleavea--cmfctabdroptargetondragleave"></a><a name="ondragleave"></a>CMFCTabDropTarget::OnDragLeave  
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
 Diese Methode ruft die `CMFCBaseTabCtrl::OnDragLeave` Methode, um den Ziehvorgang durchzuführen.  
  
##  <a name="a-nameondragovera--cmfctabdroptargetondragover"></a><a name="ondragover"></a>CMFCTabDropTarget::OnDragOver  
 Wird vom Framework aufgerufen, wenn der Benutzer ein Objekt auf der Registerkartenfenster zieht, den Fokus besitzt.  
  
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
|[in] `dwKeyState`|Enthält den Status der Zusatztasten. Dies ist eine Kombination aus einer beliebigen Anzahl von Folgendes: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, und `MK_RBUTTON`.|  
|[in] `point`|Die Position des Mauszeigers in Clientkoordinaten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkung, die sich ergibt, tritt die Dropdownliste am angegebenen Speicherort `point`. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Hinweise  
 Auf diese Weise ist die Registerkarte, die unter dem Cursor befindet, tritt ein Ziehvorgang aktiv. Es gibt `DROPEFFECT_NONE` , wenn die Symbolleiste-Framework nicht im Anpassungsmodus ist oder das Datenformat der Zwischenablage nicht verfügbar ist. Andernfalls wird das Ergebnis des Aufrufs zurückgegeben `CMFCBaseTabCtrl::OnDragOver` mit den bereitgestellten Parametern.  
  
 Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu zwischenablagedatenformate, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="a-nameondropexa--cmfctabdroptargetondropex"></a><a name="ondropex"></a>CMFCTabDropTarget::OnDropEx  
 Wird vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt, die am Ende eines Ziehvorgangs ein.  
  
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
 Der resultierende Drop-Effekt. Es kann eine oder mehrere der folgenden sein:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft `CMFCBaseTabCtrl::OnDrop` Wenn Symbolleiste Rahmen im Anpassungsmodus und Zwischenablage-Datenformats verfügbar ist. Wenn der Aufruf von `CMFCBaseTabCtrl::OnDrop` gibt ein Wert ungleich NULL, diese Methode die Standard-Drop-Effekt angegebenen gibt `dropEffect`. Diese Methode andernfalls `DROPEFFECT_NONE`. Weitere Informationen über die Drop-Effekte finden Sie unter [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).  
  
 Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu zwischenablagedatenformate, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="a-nameregistera--cmfctabdroptargetregister"></a><a name="register"></a>CMFCTabDropTarget::Register  
 Registriert das Steuerelement als eines, das das Ziel einer OLE-Drag & Drop-Operation sein kann.  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pOwner`|Das Registerkarten-Steuerelement als Dropziel registriert werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Registrierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) zur Registrierung des Steuerelements für Drag & Drop-Vorgänge.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md)




