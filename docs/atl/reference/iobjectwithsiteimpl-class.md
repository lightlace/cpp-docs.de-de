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
ms.openlocfilehash: e857f739e3ff7235c473e99abbef6aab0d3f4205
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495832"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl-Klasse

Diese Klasse stellt Methoden bereit, mit denen ein Objekt mit seiner Website kommunizieren kann.

## <a name="syntax"></a>Syntax

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IObjectWithSiteImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IObjectWithSiteImpl::GetSite](#getsite)|Fragt die Site nach einem Schnittstellen Zeiger ab.|
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Stellt das-Objekt mit dem- `IUnknown` Zeiger der Site bereit.|
|[IObjectWithSiteImpl::SetSite](#setsite)|Stellt das-Objekt mit dem- `IUnknown` Zeiger der Site bereit.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Verwaltet den `IUnknown` Zeiger der Website.|

## <a name="remarks"></a>Hinweise

Die [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) -Schnittstelle ermöglicht es einem Objekt, mit seiner Website zu kommunizieren. Die `IObjectWithSiteImpl` -Klasse stellt eine Standard Implementierung dieser Schnittstelle `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

`IObjectWithSiteImpl`gibt zwei Methoden an. Der Client ruft `SetSite`zuerst auf und übergibt den `IUnknown` Zeiger der Site. Dieser Zeiger wird im-Objekt gespeichert und kann später durch einen-aufgerufenen `GetSite`abgerufen werden.

Normalerweise leiten Sie die Klasse von `IObjectWithSiteImpl` ab, wenn Sie ein Objekt erstellen, das kein Steuerelement ist. Leiten Sie die Klasse für Steuerelemente von [ioleobjectimpl](../../atl/reference/ioleobjectimpl-class.md)ab, das auch einen Website Zeiger bereitstellt. Leiten Sie die Klasse nicht sowohl `IObjectWithSiteImpl` von als auch `IOleObjectImpl`von ab.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="getsite"></a>IObjectWithSiteImpl:: GetSite

Fragt die Site nach einem Zeiger auf die-Schnittstelle `riid`ab, die durch identifiziert wird.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Hinweise

Wenn die Site diese Schnittstelle unterstützt, wird der Zeiger `ppvSite`über zurückgegeben. `ppvSite` Andernfalls wird auf NULL festgelegt.

Weitere Informationen finden Sie unter [IObjectWithSite:: GetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) im Windows SDK.

##  <a name="m_spunksite"></a>IObjectWithSiteImpl:: m_spUnkSite

Verwaltet den `IUnknown` Zeiger der Website.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Hinweise

`m_spUnkSite`empfängt diesen Zeiger anfänglich durch einen Aufrufen von [SetSite](#setsite).

##  <a name="setchildsite"></a>IObjectWithSiteImpl:: setchildsite

Stellt das-Objekt mit dem- `IUnknown` Zeiger der Site bereit.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Parameter

*pUnkSite*<br/>
in Zeiger auf den `IUnknown` Schnittstellen Zeiger der Site, die dieses-Objekt verwaltet. Wenn der Wert NULL ist, sollte `IUnknown::Release` das Objekt an einer beliebigen vorhandenen Site anrufen, an der das Objekt seine Website nicht mehr kennt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="setsite"></a>IObjectWithSiteImpl:: SetSite

Stellt das-Objekt mit dem- `IUnknown` Zeiger der Site bereit.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
