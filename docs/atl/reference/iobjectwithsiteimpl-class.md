---
title: IObjectWithSiteImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
ms.openlocfilehash: ad27c4288d7e16949fe38ea6b8a686e3d6916ee6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296968"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl-Klasse

Diese Klasse stellt die Methoden, dass ein Objekt mit dem Standort kommunizieren.

## <a name="syntax"></a>Syntax

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IObjectWithSiteImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IObjectWithSiteImpl::GetSite](#getsite)|Fragt den Standort für einen Schnittstellenzeiger auf.|
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Stellt das Objekt mit des Standorts des `IUnknown` Zeiger.|
|[IObjectWithSiteImpl::SetSite](#setsite)|Stellt das Objekt mit des Standorts des `IUnknown` Zeiger.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Verwaltet den Standort des `IUnknown` Zeiger.|

## <a name="remarks"></a>Hinweise

Die [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) Schnittstelle ermöglicht es, ein Objekt mit dem Standort kommunizieren. Klasse `IObjectWithSiteImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

`IObjectWithSiteImpl` gibt zwei Methoden an. Der Client ruft zuerst `SetSite`, und übergeben des Standorts `IUnknown` Zeiger. This-Zeiger wird innerhalb des Objekts gespeichert und können später abgerufen werden, durch einen Aufruf von `GetSite`.

In der Regel, leiten Sie Ihre Klasse von `IObjectWithSiteImpl` ein Objekt, das für die Erstellung ist kein Steuerelement. Für Steuerelemente, leiten Sie Ihre Klasse von [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), die bietet auch eines Standort-Zeigers. Leiten Sie die Klasse nicht von beiden `IObjectWithSiteImpl` und `IOleObjectImpl`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite

Fragt den Standort für einen Zeiger auf die Schnittstelle identifizierte `riid`.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Hinweise

Wenn der Standort über diese Schnittstelle unterstützt, wird der Zeiger über zurückgegeben `ppvSite`. Andernfalls `ppvSite` auf NULL festgelegt ist.

Finden Sie unter [IObjectWithSite::GetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-getsite) in das Windows SDK.

##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite

Verwaltet den Standort des `IUnknown` Zeiger.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Hinweise

`m_spUnkSite` anfänglich empfängt diese Zeiger durch einen Aufruf von [SetSite](#setsite).

##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite

Stellt das Objekt mit des Standorts des `IUnknown` Zeiger.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Parameter

*pUnkSite*<br/>
[in] Zeiger auf die `IUnknown` -Schnittstellenzeiger des Standorts, der dieses Objekt zu verwalten. Wenn der Wert NULL ist, sollte das Objekt aufrufen `IUnknown::Release` an einem vorhandenen Standort, die zu diesem Zeitpunkt das Objekt nicht mehr den Standort weiß.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite

Stellt das Objekt mit des Standorts des `IUnknown` Zeiger.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
