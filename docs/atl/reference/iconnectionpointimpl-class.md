---
title: IConnectionPointImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
ms.openlocfilehash: bd88fd5d00df0347c0bd2161129b8cfa3ca35406
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496078"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl-Klasse

Diese Klasse implementiert einen Verbindungspunkt.

## <a name="syntax"></a>Syntax

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IConnectionPointImpl`abgeleitete Klasse.

*piid*<br/>
Ein Zeiger auf die IID der Schnittstelle, die durch das Verbindungspunkt Objekt dargestellt wird.

*CDV*<br/>
Eine Klasse, die die Verbindungen verwaltet. Der Standardwert ist [ccomdynamicunkarray](../../atl/reference/ccomdynamicunkarray-class.md), der unbegrenzte Verbindungen zulässt. Sie können auch [ccomunkarray](../../atl/reference/ccomunkarray-class.md)verwenden, das eine festgelegte Anzahl von Verbindungen angibt.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IConnectionPointImpl::Advise](#advise)|Stellt eine Verbindung zwischen dem Verbindungspunkt und einer Senke her.|
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Erstellt einen Enumerator zum Durchlaufen der Verbindungen für den Verbindungspunkt.|
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Ruft die IID der Schnittstelle ab, die durch den Verbindungspunkt dargestellt wird.|
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Ruft einen Schnittstellen Zeiger auf das Verbindungs fähige Objekt ab.|
|[IConnectionPointImpl::Unadvise](#unadvise)|Beendet eine Verbindung, die zuvor `Advise`durch hergestellt wurde.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IConnectionPointImpl:: m_vec](#m_vec)|Verwaltet die Verbindungen für den Verbindungspunkt.|

## <a name="remarks"></a>Hinweise

`IConnectionPointImpl`implementiert einen Verbindungspunkt, der es einem Objekt ermöglicht, eine ausgehende Schnittstelle für den Client verfügbar zu machen. Der Client implementiert diese Schnittstelle für ein Objekt, das als Senke bezeichnet wird.

ATL verwendet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) , um das Verbindungs fähige Objekt zu implementieren. Jeder Verbindungspunkt innerhalb des Verbindungs fähigen-Objekts stellt eine ausgehende Schnittstelle dar, die durch *piid*identifiziert wird. Class *CDV* verwaltet die Verbindungen zwischen dem Verbindungspunkt und einer Senke. Jede Verbindung wird durch ein "Cookie" eindeutig identifiziert.

Weitere Informationen zum Verwenden von Verbindungs Punkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="advise"></a>IConnectionPointImpl:: Empfehlung

Stellt eine Verbindung zwischen dem Verbindungspunkt und einer Senke her.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>Hinweise

Verwenden Sie [nicht empfohlen](#unadvise) , um den Verbindungs Befehl zu beenden.

Weitere Informationen finden Sie unter [IConnectionPoint:: Rat](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) im Windows SDK.

##  <a name="enumconnections"></a>IConnectionPointImpl:: EnumConnections

Erstellt einen Enumerator zum Durchlaufen der Verbindungen für den Verbindungspunkt.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>Hinweise

Siehe [IConnectionPoint:: EnumConnections](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) in der Windows SDK.

##  <a name="getconnectioninterface"></a>IConnectionPointImpl:: GetConnectionInterface

Ruft die IID der Schnittstelle ab, die durch den Verbindungspunkt dargestellt wird.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IConnectionPoint:: GetConnectionInterface](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) in der Windows SDK.

##  <a name="getconnectionpointcontainer"></a>IConnectionPointImpl:: GetConnectionPointContainer

Ruft einen Schnittstellen Zeiger auf das Verbindungs fähige Objekt ab.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IConnectionPoint:: GetConnectionPointContainer](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) .

##  <a name="m_vec"></a>IConnectionPointImpl:: m_vec

Verwaltet die Verbindungen zwischen dem Verbindungspunkt Objekt und einer Senke.

```
CDV m_vec;
```

### <a name="remarks"></a>Hinweise

Standardmäßig `m_vec` ist vom Typ [ccomdynamicunkarray](../../atl/reference/ccomdynamicunkarray-class.md).

##  <a name="unadvise"></a>IConnectionPointImpl:: unempfehlung

Beendet eine zuvor durch [Empfehlung](#advise)festgelegte Verbindung.

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IConnectionPoint:: Unrat](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) .

## <a name="see-also"></a>Siehe auch

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
