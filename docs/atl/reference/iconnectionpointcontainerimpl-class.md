---
title: IConnectionPointContainerImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
ms.openlocfilehash: 278ca6b1b9aac9539680d90b6fa0b18df22fc2f0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496021"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl-Klasse

Diese Klasse implementiert einen Verbindungspunkt Container zum Verwalten einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) -Objekten.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IConnectionPointContainerImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Erstellt einen Enumerator zum Durchlaufen der Verbindungspunkte, die im Verbindungs fähigen-Objekt unterstützt werden.|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Ruft einen Schnittstellen Zeiger auf den Verbindungspunkt ab, der die angegebene IID unterstützt.|

## <a name="remarks"></a>Hinweise

`IConnectionPointContainerImpl`implementiert einen Verbindungspunkt Container zum Verwalten einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) -Objekten. `IConnectionPointContainerImpl`stellt zwei Methoden bereit, die ein Client aufrufen kann, um weitere Informationen zu einem Verbindungs fähigen Objekt abzurufen:

- `EnumConnectionPoints`ermöglicht dem Client, zu bestimmen, welche ausgehenden Schnittstellen vom Objekt unterstützt werden.

- `FindConnectionPoint`ermöglicht dem Client, zu bestimmen, ob das Objekt eine bestimmte ausgehende Schnittstelle unterstützt.

Informationen zur Verwendung von Verbindungs Punkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="enumconnectionpoints"></a>IConnectionPointContainerImpl:: EnumConnectionPoints

Erstellt einen Enumerator zum Durchlaufen der Verbindungspunkte, die im Verbindungs fähigen-Objekt unterstützt werden.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Hinweise

Siehe [IConnectionPointContainer:: EnumConnectionPoints](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) in der Windows SDK.

##  <a name="findconnectionpoint"></a>IConnectionPointContainerImpl:: FindConnectionPoint

Ruft einen Schnittstellen Zeiger auf den Verbindungspunkt ab, der die angegebene IID unterstützt.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IConnectionPointContainer:: FindConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) .

## <a name="see-also"></a>Siehe auch

[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
