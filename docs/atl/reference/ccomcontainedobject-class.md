---
title: Ccomcontainedobject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: c5e2fa64cc0938e632a37eac7dd1d6e9111c3d98
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497321"
---
# <a name="ccomcontainedobject-class"></a>Ccomcontainedobject-Klasse

Diese Klasse implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , indem an die des Besitzer Objekts `IUnknown`delegiert wird.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>Parameter

*Sock*<br/>
Ihre Klasse, abgeleitet von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Der Konstruktor. Initialisiert den Member- `IUnknown`Zeiger auf die des Besitzer Objekts.|
|[CComContainedObject::~CComContainedObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComContainedObject::AddRef](#addref)|Inkremente den Verweis Zähler für das Besitzer Objekt.|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Ruft die des Besitzer Objekts `IUnknown`ab.|
|[CComContainedObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die-Schnittstelle ab, die für das Besitzer Objekt angefordert wurde.|
|[CComContainedObject::Release](#release)|Dekremente den Verweis Zähler für das Besitzer Objekt.|

## <a name="remarks"></a>Hinweise

ATL verwendet `CComContainedObject` in den Klassen [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md)und [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) durch Delegieren an das Besitzer Objekt `IUnknown`. (Der Besitzer ist entweder das äußere Objekt einer Aggregation oder das Objekt, für das eine abtrenn Schnittstelle erstellt wird.) `CComContainedObject` `OuterQueryInterface`Aufrufe ,und`OuterAddRef`, die alle durch`Base`geerbt wurden. `OuterRelease` `CComObjectRootEx`

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComContainedObject`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="addref"></a>Ccomcontainedobject:: adressf

Inkremente den Verweis Zähler für das Besitzer Objekt.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose oder das Testen nützlich sein kann.

##  <a name="ccomcontainedobject"></a>Ccomcontainedobject:: ccomcontainedobject

Der Konstruktor.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Parameter

*teuren*<br/>
in Das Besitzer Objekt `IUnknown`.

### <a name="remarks"></a>Hinweise

Legt den `m_pOuterUnknown` Member-Zeiger (geerbt durch `Base` die-Klasse) auf *PV*fest.

##  <a name="dtor"></a>Ccomcontainedobject:: ~ ccomcontainedobject

Der Destruktor.

```
~CComContainedObject();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei.

##  <a name="getcontrollingunknown"></a>Ccomcontainedobject:: getcontrollingunknown

Gibt den `m_pOuterUnknown` Member- `IUnknown`Zeiger (geerbt durch die *Basis* Klasse) zurück, der das Besitzer Objekt enthält.

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Rückgabewert

Das Besitzer Objekt `IUnknown`.

### <a name="remarks"></a>Hinweise

Diese Methode ist möglicherweise virtuell `Base` , wenn das [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) -Makro deklariert hat.

##  <a name="queryinterface"></a>Ccomcontainedobject:: QueryInterface

Ruft einen Zeiger auf die-Schnittstelle ab, die für das Besitzer Objekt angefordert wurde.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Der Bezeichner der angeforderten Schnittstelle.

*ppvObject*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch *IID*identifiziert wird. Wenn das Objekt diese Schnittstelle nicht unterstützt, wird *ppvobject* auf NULL festgelegt.

*pp*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch `Q`den-Typ identifiziert wird. Wenn das Objekt diese Schnittstelle nicht unterstützt, wird *PP* auf NULL festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="release"></a>Ccomcontainedobject:: Release

Dekremente den Verweis Zähler für das Besitzer Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In Debugbuilds `Release` gibt einen Wert zurück, der für die Diagnose oder das Testen nützlich sein kann. In nicht Debugbuilds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
