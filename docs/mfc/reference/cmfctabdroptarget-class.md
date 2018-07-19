---
title: CMFCTabDropTarget-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2991135d7cbb7e2e9df66e871b5d047e69b93d16
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852967"
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget-Klasse
Stellt den Kommunikationsmechanismus zwischen einem Registerkarten-Steuerelement und die OLE-Bibliotheken bereit.  
  
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
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|Vom Framework aufgerufen, wenn der Benutzer ein Objekt in einer Registerkartenfenster zieht. (Überschreibt [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|Wird von Framework aufgerufen, wenn der Benutzer ein Objekt außerhalb des Fensters Registerkarte zieht, den Fokus besitzt. (Überschreibt [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|Wird von Framework aufgerufen, wenn der Benutzer ein Objekt auf der Registerkarte "-Fenster zieht, den Fokus besitzt. (Überschreibt [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt, die am Ende des Ziehvorgangs. (Überschreibt [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|  
|[CMFCTabDropTarget::Register](#register)|Registriert das-Steuerelement als eins, das das Ziel eines OLE-Drag & Drop-Vorgangs verwendet werden kann.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse bietet Drag & Drop-Unterstützung, die `CMFCBaseTabCtrl` Klasse. Wenn Ihre Anwendung initialisiert wird die OLE-Bibliotheken mithilfe der [AfxOleInit](ole-initialization.md#afxoleinit) Funktion `CMFCBaseTabCtrl` Objekte registrieren sich selbst für Drag & Drop-Vorgänge.  
  
 Die `CMFCTabDropTarget` Klasse erweitert die Basisklasse, indem Sie die Registerkarte, unter dem Cursor befindet, tritt ein Ziehvorgang Active, machen. Weitere Informationen zu Drag & Drop-Vorgängen finden Sie unter [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
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
  
##  <a name="ondragenter"></a>  CMFCTabDropTarget::OnDragEnter  
 Vom Framework aufgerufen, wenn der Benutzer ein Objekt in einer Registerkartenfenster zieht.  
  
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
|[in] *aufnehmen*|Nicht verwendet.|  
|[in] *pDataObject*|Ein Zeiger auf das Objekt, das der Benutzer zieht.|  
|[in] *DwKeyState*|Enthält den Status der Modifizierertasten. Eine Kombination aus einer beliebigen Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.|  
|[in] *zeigen*|Die Position des Cursors in Clientkoordinaten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkungen, die sich ergibt, wenn das ablegen, an dem vom angegebenen Speicherort geschieht *zeigen*. Sie können eine oder mehrere der folgenden sein:  
  
- DROPEFFECT_NONE  
  
- DROPEFFECT_COPY  
  
- DROPEFFECT_MOVE  
  
- DROPEFFECT_LINK  
  
- DROPEFFECT_SCROLL  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt DROPEFFECT_NONE zurück, wenn das Framework für die Symbolleiste befindet sich nicht im Anpassungsmodus oder das Datenformat der Zwischenablage nicht verfügbar ist. Andernfalls wird das Ergebnis des Aufrufs `CMFCBaseTabCtrl::OnDragEnter` mit den bereitgestellten Parametern.  
  
 Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu den Standardformaten der Zwischenablage Daten, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="ondragleave"></a>  CMFCTabDropTarget::OnDragLeave  
 Wird von Framework aufgerufen, wenn der Benutzer ein Objekt außerhalb des Fensters Registerkarte zieht, den Fokus besitzt.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] *aufnehmen*|Nicht verwendet.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die `CMFCBaseTabCtrl::OnDragLeave` Methode, um den Ziehvorgang entsteht durchzuführen.  
  
##  <a name="ondragover"></a>  CMFCTabDropTarget::OnDragOver  
 Wird von Framework aufgerufen, wenn der Benutzer ein Objekt auf der Registerkarte "-Fenster zieht, den Fokus besitzt.  
  
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
|[in] *aufnehmen*|Nicht verwendet.|  
|[in] *pDataObject*|Ein Zeiger auf das Objekt, das der Benutzer zieht.|  
|[in] *DwKeyState*|Enthält den Status der Modifizierertasten. Eine Kombination aus einer beliebigen Anzahl von Folgendes: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON.|  
|[in] *zeigen*|Die Position des Mauszeigers in Clientkoordinaten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Auswirkungen, die sich ergibt, wenn das ablegen, an dem vom angegebenen Speicherort geschieht *zeigen*. Sie können eine oder mehrere der folgenden sein:  
  
- DROPEFFECT_NONE  
  
- DROPEFFECT_COPY  
  
- DROPEFFECT_MOVE  
  
- DROPEFFECT_LINK  
  
- DROPEFFECT_SCROLL  
  
### <a name="remarks"></a>Hinweise  
 Auf diese Weise wird die Registerkarte, die unter dem Cursor befindet, wenn ein Ziehvorgang active auftritt. DROPEFFECT_NONE gibt, wenn das Framework für die Symbolleiste befindet sich nicht im Anpassungsmodus oder das Datenformat der Zwischenablage nicht verfügbar ist. Andernfalls wird das Ergebnis des Aufrufs `CMFCBaseTabCtrl::OnDragOver` mit den bereitgestellten Parametern.  
  
 Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu den Standardformaten der Zwischenablage Daten, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="ondropex"></a>  CMFCTabDropTarget::OnDropEx  
 Vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt, die am Ende des Ziehvorgangs.  
  
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
|[in] *aufnehmen*|Nicht verwendet.|  
|[in] *pDataObject*|Ein Zeiger auf das Objekt, das der Benutzer zieht.|  
|[in] *-DropEffect-*|Der Standard-Drop-Vorgang.|  
|[in] *Dropdownliste*|Nicht verwendet.|  
|[in] *zeigen*|Die Position des Mauszeigers in Clientkoordinaten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der resultierende Drop-Effekt. Sie können eine oder mehrere der folgenden sein:  
  
- DROPEFFECT_NONE  
  
- DROPEFFECT_COPY  
  
- DROPEFFECT_MOVE  
  
- DROPEFFECT_LINK  
  
- DROPEFFECT_SCROLL  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft `CMFCBaseTabCtrl::OnDrop` Wenn das Framework für die Symbolleiste im Anpassungsmodus und Zwischenablage-Datenformats zur Verfügung steht. Wenn der Aufruf von `CMFCBaseTabCtrl::OnDrop` gibt ein Wert ungleich NULL, diese Methode den Standardwert des Ablageeffekts gemäß gibt *-DropEffect-*. Andernfalls gibt diese Methode DROPEFFECT_NONE zurück. Weitere Informationen zu & Drop-Effekte, finden Sie unter [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).  
  
 Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Weitere Informationen zu den Standardformaten der Zwischenablage Daten, finden Sie unter [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="register"></a>  CMFCTabDropTarget::Register  
 Registriert das-Steuerelement als eins, das das Ziel eines OLE-Drag & Drop-Vorgangs verwendet werden kann.  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] *pOwner*|Das Registerkarten-Steuerelement als Ablageziel zu registrieren.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn die Registrierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) zur Registrierung des Steuerelements für Drag & Drop-Vorgänge.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md)



