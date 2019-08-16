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
ms.openlocfilehash: 3aead41f317d175eac9dcb094aa2070d82dc6185
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495502"
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt Standard Implementierungen der Schnittstellen [IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)und [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE IViewObjectExImpl
   : public IViewObjectEx
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IViewObjectExImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IViewObjectExImpl::Draw](#draw)|Zeichnet eine Darstellung des-Steuer Elements auf einen Gerätekontext.|
|[IViewObjectExImpl:: Freeze](#freeze)|Friert die gezeichnete Darstellung eines-Steuer Elements, sodass es bis `Unfreeze`zum nicht geändert wird. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IViewObjectExImpl::GetAdvise](#getadvise)|Ruft eine vorhandene beratungssenke-Verbindung auf dem Steuerelement ab, sofern vorhanden.|
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Gibt die logische Palette zurück, die vom Steuerelement für die Zeichnung verwendet wird. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IViewObjectExImpl::GetExtent](#getextent)|Ruft die Anzeige Größe des Steuer Elements in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) aus dem Steuerelement-Klassendatenmember [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)ab.|
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Stellt Größen Hinweise aus dem Container für das Objekt bereit, das verwendet werden soll, wenn der Benutzer die Größe ändert.|
|[IViewObjectExImpl::GetRect](#getrect)|Gibt ein Rechteck zurück, das einen angeforderten Zeichnungs Aspekt beschreibt. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Gibt Informationen über die Durchlässigkeit des Objekts zurück und welche Zeichnungs Aspekte unterstützt werden.|
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Überprüft, ob der angegebene Punkt im angegebenen Rechteck ist, und gibt in `pHitResult`einen [HitResult](/windows/win32/api/ocidl/ne-ocidl-hitresult) -Wert zurück.|
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Überprüft, ob das Anzeige Rechteck des Steuer Elements einen beliebigen Punkt im angegebenen Positions Rechteck überlappt und einen HitResult `pHitResult`-Wert in zurückgibt.|
|[IViewObjectExImpl::SetAdvise](#setadvise)|Richtet eine Verbindung zwischen dem-Steuerelement und einer Benachrichtigungs Senke ein, damit die Senke über Änderungen in der Ansicht des Steuer Elements benachrichtigt werden kann.|
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Entfriert die gezeichnete Darstellung des-Steuer Elements. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Mit den Schnittstellen [IViewObject](/windows/win32/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/win32/api/oleidl/nn-oleidl-iviewobject2)und [IViewObjectEx](/windows/win32/api/ocidl/nn-ocidl-iviewobjectex) kann ein Steuerelement sich direkt anzeigen lassen und eine Benachrichtigungs Senke erstellen und verwalten, um den Container über Änderungen in der Steuerelement Anzeige zu benachrichtigen. Die `IViewObjectEx` -Schnittstelle bietet Unterstützung für erweiterte Steuerelement Features, wie z. b. flimmerfreies zeichnen, nicht rechteckige und transparente Steuerelemente und Treffer Tests (z. b., wie nahe ein Mausklick im Steuerelement berücksichtigt werden muss). Die `IViewObjectExImpl` -Klasse stellt eine Standard Implementierung dieser Schnittstellen `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IViewObjectEx`

`IViewObjectExImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="draw"></a>IViewObjectExImpl::D RAW

Zeichnet eine Darstellung des-Steuer Elements auf einen Gerätekontext.

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

Diese Methode ruft `CComControl::OnDrawAdvanced` auf, die wiederum die- `OnDraw` Methode der Steuerelement Klasse aufruft. Wenn `OnDraw` Sie das Steuerelement mit dem ATL-Steuerelement-Assistenten erstellen, wird der Steuerelement Klasse automatisch eine-Methode hinzugefügt. Der Standard `OnDraw` des Assistenten zeichnet ein Rechteck mit der Bezeichnung "ATL 3,0".

Weitere Informationen finden Sie unter [IViewObject::D RAW](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw) in der Windows SDK.

##  <a name="freeze"></a>IViewObjectExImpl:: Freeze

Friert die gezeichnete Darstellung eines-Steuer Elements, sodass es bis `Unfreeze`zum nicht geändert wird. Die ATL-Implementierung gibt E_NOTIMPL zurück.

```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IViewObject:: Freeze](/windows/win32/api/oleidl/nf-oleidl-iviewobject-freeze) in der Windows SDK.

##  <a name="getadvise"></a>IViewObjectExImpl:: getrat

Ruft eine vorhandene beratungssenke-Verbindung auf dem Steuerelement ab, sofern vorhanden.

```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```

### <a name="remarks"></a>Hinweise

Die Beratungs Senke wird im Steuerelement-Klassendatenmember [CComControlBase:: m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)gespeichert.

Weitere Informationen finden Sie unter [IViewObject:: getrat](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getadvise) im Windows SDK.

##  <a name="getcolorset"></a>IViewObjectExImpl:: GetColorSet

Gibt die logische Palette zurück, die vom Steuerelement für die Zeichnung verwendet wird. Die ATL-Implementierung gibt E_NOTIMPL zurück.

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

Siehe [IViewObject:: GetColorSet](/windows/win32/api/oleidl/nf-oleidl-iviewobject-getcolorset) in der Windows SDK.

##  <a name="getextent"></a>IViewObjectExImpl:: GetExtent

Ruft die Anzeige Größe des Steuer Elements in HIMETRIC-Einheiten (0,01 Millimeter pro Einheit) aus dem Steuerelement-Klassendatenmember [CComControlBase:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)ab.

```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IViewObject2:: GetExtent](/windows/win32/api/oleidl/nf-oleidl-iviewobject2-getextent) in der Windows SDK.

##  <a name="getnaturalextent"></a>IViewObjectExImpl:: getnaturalextent

Stellt Größen Hinweise aus dem Container für das Objekt bereit, das verwendet werden soll, wenn der Benutzer die Größe ändert.

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

Wenn `dwAspect` DVASPECT_CONTENT und *pextentinfo-> dwextentmode* auf DVEXTENT_CONTENT festgelegt ist, `psizel` wird * auf den Datenmember der Steuerelement Klasse [CComControlBase:: m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)festgelegt. Andernfalls wird ein HRESULT-Fehler zurückgegeben.

Weitere Informationen finden Sie unter [IViewObjectEx:: getnaturalextent](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getnaturalextent) in der Windows SDK.

##  <a name="getrect"></a>IViewObjectExImpl:: GetRect

Gibt ein Rechteck zurück, das einen angeforderten Zeichnungs Aspekt beschreibt. Die ATL-Implementierung gibt E_NOTIMPL zurück.

```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IViewObjectEx:: GetRect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getrect) .

##  <a name="getviewstatus"></a>IViewObjectExImpl:: getviewstatus

Gibt Informationen über die Durchlässigkeit des Objekts zurück und welche Zeichnungs Aspekte unterstützt werden.

```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```

### <a name="remarks"></a>Hinweise

Standardmäßig wird ATL fest `pdwStatus` gelegt, um anzugeben, dass das Steuerelement VIEWSTATUS_OPAQUE unterstützt (mögliche Werte sind in der [VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus) -Enumeration).

Weitere Informationen finden Sie unter [IViewObjectEx:: getviewstatus](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-getviewstatus) im Windows SDK.

##  <a name="queryhitpoint"></a>IViewObjectExImpl:: queryhitpoint

Überprüft, ob der angegebene Punkt im angegebenen Rechteck ist, und gibt in `pHitResult`einen [HitResult](/windows/win32/api/ocidl/ne-ocidl-hitresult) -Wert zurück.

```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Hinweise

Der Wert kann entweder "HITRESULT_HIT" oder "HITRESULT_OUTSIDE" lauten.

Wenn `dwAspect` [DVASPECT_CONTENT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)ist, gibt die Methode S_OK zurück. Andernfalls gibt die Methode E_FAIL zurück.

Weitere Informationen finden Sie im Windows SDK unter [IViewObjectEx:: queryhitpoint](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitpoint) .

##  <a name="queryhitrect"></a>IViewObjectExImpl:: queryhitrect

Überprüft, ob das Anzeige Rechteck des Steuer Elements einen beliebigen Punkt im angegebenen Positions Rechteck überlappt und einen [HitResult](/windows/win32/api/ocidl/ne-ocidl-hitresult) -Wert in `pHitResult`zurückgibt.

```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```

### <a name="remarks"></a>Hinweise

Der Wert kann entweder "HITRESULT_HIT" oder "HITRESULT_OUTSIDE" lauten.

Wenn `dwAspect` [DVASPECT_CONTENT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)ist, gibt die Methode S_OK zurück. Andernfalls gibt die Methode E_FAIL zurück.

Weitere Informationen finden Sie unter [IViewObjectEx:: queryhitrect](/windows/win32/api/ocidl/nf-ocidl-iviewobjectex-queryhitrect) in der Windows SDK.

##  <a name="setadvise"></a>IViewObjectExImpl:: setrat

Richtet eine Verbindung zwischen dem-Steuerelement und einer Benachrichtigungs Senke ein, damit die Senke über Änderungen in der Ansicht des Steuer Elements benachrichtigt werden kann.

```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```

### <a name="remarks"></a>Hinweise

Der Zeiger auf die [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) -Schnittstelle in der "Hinweis"-Senke wird im Steuerelement-Klassendatenmember " [CComControlBase:: m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink)" gespeichert.

Weitere Informationen finden Sie unter [IViewObject:: setrat](/windows/win32/api/oleidl/nf-oleidl-iviewobject-setadvise) im Windows SDK.

##  <a name="unfreeze"></a>IViewObjectExImpl:: unfreeze

Entfriert die gezeichnete Darstellung des-Steuer Elements. Die ATL-Implementierung gibt E_NOTIMPL zurück.

```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IViewObject:: unfreeze](/windows/win32/api/oleidl/nf-oleidl-iviewobject-unfreeze) in der Windows SDK.

##  <a name="closehandle"></a>Iworkerthreadclient:: CloseHandle

Implementieren Sie diese Methode, um das Handle zu schließen, das diesem Objekt zugeordnet ist.

```
HRESULT CloseHandle(HANDLE hHandle);
```

### <a name="parameters"></a>Parameter

*hHandle*<br/>
Das Handle, das geschlossen werden soll.

### <a name="return-value"></a>Rückgabewert

Rückgabe von "S_OK" bei Erfolg oder Fehler "HRESULT" bei einem Fehler.

### <a name="remarks"></a>Hinweise

Das an diese Methode über gegebene Handle wurde diesem-Objekt zuvor durch einen [CWorkerThread:: addhandle](../../atl/reference/cworkerthread-class.md#addhandle)-Befehl zugeordnet.

### <a name="example"></a>Beispiel

Der folgende Code zeigt eine einfache Implementierung von `IWorkerThreadClient::CloseHandle`.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]

##  <a name="execute"></a>Iworkerthreadclient:: Execute

Implementieren Sie diese Methode, um Code auszuführen, wenn das Handle, das diesem Objekt zugeordnet ist, signalisiert wird.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parameter

*dwParam*<br/>
Der Benutzerparameter.

*hobject*<br/>
Das Handle, das signalisiert wurde.

### <a name="return-value"></a>Rückgabewert

Rückgabe von "S_OK" bei Erfolg oder Fehler "HRESULT" bei einem Fehler.

### <a name="remarks"></a>Hinweise

Das Handle und der DWORD/Zeiger, die an diese Methode übergeben wurden, wurden diesem-Objekt zuvor durch einen [CWorkerThread:: addhandle](../../atl/reference/cworkerthread-class.md#addhandle)-Befehl zugeordnet.

### <a name="example"></a>Beispiel

Der folgende Code zeigt eine einfache Implementierung von `IWorkerThreadClient::Execute`.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX-Steuerelement Schnittstellen](/windows/win32/com/activex-controls-interfaces)<br/>
[Tutorial](../../atl/active-template-library-atl-tutorial.md)<br/>
[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
