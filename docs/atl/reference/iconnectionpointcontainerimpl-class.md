---
title: IConnectionPointContainerImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27c1d945cf9e801ec1fe2346232aebcad559982a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019896"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl-Klasse

Diese Klasse implementiert eine Verbindungspunktcontainer zur Verwaltung einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Objekte.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IConnectionPointContainerImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Erstellt einen Enumerator zum Durchlaufen der Verbindungspunkte, die in dem verbindungsfähigen Objekt unterstützt.|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Ruft einen Schnittstellenzeiger auf den Verbindungspunkt, der die angegebene IID unterstützt ab.|

## <a name="remarks"></a>Hinweise

`IConnectionPointContainerImpl` implementiert eine Verbindungspunktcontainer zur Verwaltung einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Objekte. `IConnectionPointContainerImpl` bietet zwei Methoden, die ein Client aufrufen kann, um weitere Informationen zu einem verbindungsfähigen Objekt abzurufen:

- `EnumConnectionPoints` ermöglicht dem Client, um zu bestimmen, welche ausgehend vom Objekt unterstützte Schnittstellen.

- `FindConnectionPoint` ermöglicht dem Client zu bestimmen, ob das Objekt eine bestimmte Schnittstelle für ausgehende unterstützt.

Informationen zur Verwendung von Verbindungspunkten in ATL, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints

Erstellt einen Enumerator zum Durchlaufen der Verbindungspunkte, die in dem verbindungsfähigen Objekt unterstützt.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IConnectionPointContainer:: EnumConnectionPoints](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) in das Windows SDK.

##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint

Ruft einen Schnittstellenzeiger auf den Verbindungspunkt, der die angegebene IID unterstützt ab.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IConnectionPointContainer:: FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
