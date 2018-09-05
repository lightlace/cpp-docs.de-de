---
title: IConnectionPointImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e2b3e7a0589c0da4d41cab419fa68039e4f0b62c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763353"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl-Klasse

Diese Klasse implementiert einen Verbindungspunkt.

## <a name="syntax"></a>Syntax

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>Parameter

*T*  
Abgeleitet von die Klasse `IConnectionPointImpl`.

*piid*  
Ein Zeiger auf die IID der Schnittstelle, die durch das Objekt dargestellt wird.

*CDV*  
Eine Klasse, die Verbindungen verwaltet. Der Standardwert ist [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), womit unbegrenzte Verbindungen. Sie können auch [CComUnkArray](../../atl/reference/ccomunkarray-class.md), die eine feste Anzahl von Verbindungen angibt.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IConnectionPointImpl::Advise](#advise)|Herstellen einer Verbindung zwischen dem Verbindungspunkt und eine Senke.|
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Erstellt einen Enumerator zum Durchlaufen der Verbindungen für den Verbindungspunkt.|
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Ruft die IID der Schnittstelle dargestellt, die von den Verbindungspunkt ab.|
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Ruft einen Schnittstellenzeiger auf das verbindungsfähige Objekt ab.|
|[IConnectionPointImpl::Unadvise](#unadvise)|Beendet eine Verbindung zuvor mit `Advise`.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IConnectionPointImpl::m_vec](#m_vec)|Verwaltet die Verbindungen für den Verbindungspunkt an.|

## <a name="remarks"></a>Hinweise

`IConnectionPointImpl` implementiert einen Verbindungspunkt, auf der ein Objekt, das eine Ausgangsschnittstelle an den Client verfügbar machen kann. Der Client implementiert diese Schnittstelle für ein Objekt, das als Sink bezeichnet wird.

ATL verwendet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) das verbindungsfähige Objekt zu implementieren. Jeder Verbindungspunkt in das verbindungsfähige Objekt darstellt, eine Ausgangsschnittstelle identifizierte *Piid*. Klasse *CDV* verwaltet die Verbindungen zwischen dem Verbindungspunkt und eine Senke. Jede Verbindung wird durch ein "Cookie". eindeutig identifiziert.

Weitere Informationen zur Verwendung von Verbindungspunkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="advise"></a>  IConnectionPointImpl::Advise

Herstellen einer Verbindung zwischen dem Verbindungspunkt und eine Senke.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>Hinweise

Verwendung [Unadvise](#unadvise) auf den Aufruf für die Verbindung beenden.

Finden Sie unter [IConnectionPoint:: Advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) in das Windows SDK.

##  <a name="enumconnections"></a>  IConnectionPointImpl::EnumConnections

Erstellt einen Enumerator zum Durchlaufen der Verbindungen für den Verbindungspunkt.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IConnectionPoint:: EnumConnections](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) in das Windows SDK.

##  <a name="getconnectioninterface"></a>  IConnectionPointImpl::GetConnectionInterface

Ruft die IID der Schnittstelle dargestellt, die von den Verbindungspunkt ab.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IConnectionPoint:: GetConnectionInterface](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) in das Windows SDK.

##  <a name="getconnectionpointcontainer"></a>  IConnectionPointImpl::GetConnectionPointContainer

Ruft einen Schnittstellenzeiger auf das verbindungsfähige Objekt ab.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IConnectionPoint:: GetConnectionPointContainer](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) in das Windows SDK.

##  <a name="m_vec"></a>  IConnectionPointImpl::m_vec

Verwaltet die Verbindungen zwischen das-Objekt und eine Senke an.

```
CDV m_vec;
```

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `m_vec` ist vom Typ [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).

##  <a name="unadvise"></a>  IConnectionPointImpl::Unadvise

Beendet eine Verbindung zuvor mit [Advise](#advise).

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IConnectionPoint:: Unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
