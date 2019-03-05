---
title: IViewObjectExImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
ms.openlocfilehash: 4ed7a7e4a6070ba52c54c4dace687111cf7d33d8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301934"
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt standardimplementierungen der [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2), und [IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex) Schnittstellen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE IViewObjectExImpl
   : public IViewObjectEx
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IViewObjectExImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IViewObjectExImpl::Draw](#draw)|Zeichnet eine Darstellung des Steuerelements auf einen Gerätekontext.|
|[IViewObjectExImpl::Freeze](#freeze)|Friert die gezeichnete Darstellung eines Steuerelements, sodass sich diese nicht bis zum Ändern einer `Unfreeze`. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IViewObjectExImpl::GetAdvise](#getadvise)|Ruft eine vorhandene Advise-Senke-Verbindung auf das Steuerelement ab, sofern vorhanden.|
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Gibt die logische Palette, die vom Steuerelement verwendet wird, für das Zeichnen zurück. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IViewObjectExImpl::GetExtent](#getextent)|Ruft die Größe des Steuerelements in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) ab, aus der Steuerelement-Klassendatenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Stellt Größenhinweise vom Container für das Objekt verwenden, wie der Benutzer die Größe ändert.|
|[IViewObjectExImpl::GetRect](#getrect)|Gibt ein Rechteck, das einen angeforderten Zeichenaspekt beschreibt. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Gibt Informationen über die Durchlässigkeit des Objekts und Zeichenaspekte unterstützt werden.|
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Überprüft, ob der angegebene Punkt befindet sich in das angegebene Rechteck und gibt eine [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) Wert `pHitResult`.|
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Überprüft, ob das Rechteck des Steuerelements anzeigen überschneidet sich mit einem beliebigen Zeitpunkt im angegebenen Speicherort Rechteck und einen Wert HITRESULT in gibt `pHitResult`.|
|[IViewObjectExImpl::SetAdvise](#setadvise)|Legt fest, um eine Verbindung zwischen dem Steuerelement und einer Advise-Senke, damit die Senke über Änderungen in der Ansicht des Steuerelements benachrichtigt werden kann.|
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Hebt die Fixierung der gezeichneten Darstellung des Steuerelements. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Die [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2), und [IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex) Schnittstellen aktivieren ein Steuerelements, sich direkt anzuzeigen und zu erstellen und verwalten eine Advise-Senke zu benachrichtigen, die Container mit Änderungen in der Steuerelementanzeige. Die `IViewObjectEx` Schnittstelle bietet Unterstützung für erweiterten Steuerelements Features wie z. B. flimmerfreie zeichnen, viereckig noch transparent Steuerelemente und Treffertests (z. B., wie weit ein Mausklick sein muss auf dem Steuerelement berücksichtigt werden). Klasse `IViewObjectExImpl` stellt eine Standardimplementierung dieser Schnittstellen bereit, und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="draw"></a>  IViewObjectExImpl::Draw

Zeichnet eine Darstellung des Steuerelements auf einen Gerätekontext.

```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```

### <a name="remarks"></a>Hinweise

Diese Methode ruft `CComControl::OnDrawAdvanced` die ruft der Steuerelementklasse `OnDraw` Methode. Ein `OnDraw` Methode wird automatisch der Steuerelement-Klasse hinzugefügt, wenn Sie das Steuerelement mit dem ATL-Steuerelement-Assistenten erstellen. Des Assistenten standardmäßig `OnDraw` zeichnet ein Rechteck mit der Bezeichnung "ATL 3.0".

Finden Sie unter [IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw) in das Windows SDK.

##  <a name="freeze"></a>  IViewObjectExImpl::Freeze

Friert die gezeichnete Darstellung eines Steuerelements, sodass sich diese nicht bis zum Ändern einer `Unfreeze`. Die ATL-Implementierung gibt E_NOTIMPL zurück.

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IViewObject::Freeze](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-freeze) in das Windows SDK.

##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise

Ruft eine vorhandene Advise-Senke-Verbindung auf das Steuerelement ab, sofern vorhanden.

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>Hinweise

Die Advise-Senke befindet sich in der Steuerelement-Klassendatenmember [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).

Finden Sie unter [IViewObject::GetAdvise](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-getadvise) in das Windows SDK.

##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet

Gibt die logische Palette, die vom Steuerelement verwendet wird, für das Zeichnen zurück. Die ATL-Implementierung gibt E_NOTIMPL zurück.

```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IViewObject::GetColorSet](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-getcolorset) in das Windows SDK.

##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent

Ruft die Größe des Steuerelements in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) ab, aus der Steuerelement-Klassendatenmember [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IViewObject2::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-iviewobject2-getextent) in das Windows SDK.

##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent

Stellt Größenhinweise vom Container für das Objekt verwenden, wie der Benutzer die Größe ändert.

```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```

### <a name="remarks"></a>Hinweise

Wenn `dwAspect` DVASPECT_CONTENT ist und *pExtentInfo -> DwExtentMode* DVEXTENT_CONTENT ist, legt * `psizel` in der Steuerelementklasse-Datenmember [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). Andernfalls wird ein fehlerhaftes HRESULT zurückgegeben.

Finden Sie unter [IViewObjectEx::GetNaturalExtent](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) in das Windows SDK.

##  <a name="getrect"></a>  IViewObjectExImpl::GetRect

Gibt ein Rechteck, das einen angeforderten Zeichenaspekt beschreibt. Die ATL-Implementierung gibt E_NOTIMPL zurück.

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IViewObjectEx::GetRect](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getrect) in das Windows SDK.

##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus

Gibt Informationen über die Durchlässigkeit des Objekts und Zeichenaspekte unterstützt werden.

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>Hinweise

Standardmäßig legt ATL `pdwStatus` um anzugeben, dass das Steuerelement VIEWSTATUS_OPAQUE unterstützt (mögliche Werte sind in der [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) Enumeration).

Finden Sie unter [IViewObjectEx::GetViewStatus](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) in das Windows SDK.

##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint

Überprüft, ob der angegebene Punkt befindet sich in das angegebene Rechteck und gibt eine [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) Wert `pHitResult`.

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Hinweise

Der Wert kann entweder HITRESULT_HIT oder HITRESULT_OUTSIDE sein.

Wenn `dwAspect` gleich [DVASPECT_CONTENT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), die Methode gibt S_OK zurück. Andernfalls gibt die Methode E_FAIL zurück.

Finden Sie unter [IViewObjectEx::QueryHitPoint](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) in das Windows SDK.

##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect

Überprüft, ob das Rechteck des Steuerelements anzeigen, überschneidet sich mit einem beliebigen Zeitpunkt im angegebenen Speicherort Rechteck, und gibt eine [HITRESULT](/windows/desktop/api/ocidl/ne-ocidl-taghitresult) Wert `pHitResult`.

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Hinweise

Der Wert kann entweder HITRESULT_HIT oder HITRESULT_OUTSIDE sein.

Wenn `dwAspect` gleich [DVASPECT_CONTENT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), die Methode gibt S_OK zurück. Andernfalls gibt die Methode E_FAIL zurück.

Finden Sie unter [IViewObjectEx::QueryHitRect](/windows/desktop/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) in das Windows SDK.

##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise

Legt fest, um eine Verbindung zwischen dem Steuerelement und einer Advise-Senke, damit die Senke über Änderungen in der Ansicht des Steuerelements benachrichtigt werden kann.

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>Hinweise

Der Zeiger auf die [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) -Schnittstelle der Advise-Senke befindet sich in der Steuerelement-Klassendatenmember [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).

Finden Sie unter [IViewObject::SetAdvise](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-setadvise) in das Windows SDK.

##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze

Hebt die Fixierung der gezeichneten Darstellung des Steuerelements. Die ATL-Implementierung gibt E_NOTIMPL zurück.

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IViewObject::Unfreeze](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-unfreeze) in das Windows SDK.

##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle

Implementieren Sie diese Methode, um das Handle, das diesem Objekt zugeordneten zu schließen.

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>Parameter

*hHandle*<br/>
Das Handle geschlossen werden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Das Handle, das an diese Methode übergeben wurde bereits zugeordnet. dieses Objekt durch einen Aufruf von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Beispiel

Der folgende Code zeigt eine einfache Implementierung der `IWorkerThreadClient::CloseHandle`.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

##  <a name="execute"></a>  IWorkerThreadClient::Execute

Implementieren Sie diese Methode, um Code auszuführen, wenn das diesem Objekt zugeordnete Handle signalisiert wird.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parameter

*dwParam*<br/>
Der Benutzerparameter.

*hObject*<br/>
Das Handle, das signalisiert wurde.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Das Handle und die DWORD/Zeiger an diese Methode übergeben wurden zuvor mit diesem Objekt durch einen Aufruf von verknüpften [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Beispiel

Der folgende Code zeigt eine einfache Implementierung der `IWorkerThreadClient::Execute`.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX-Steuerelemente Schnittstellen](/windows/desktop/com/activex-controls-interfaces)<br/>
[Tutorial](../../atl/active-template-library-atl-tutorial.md)<br/>
[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
