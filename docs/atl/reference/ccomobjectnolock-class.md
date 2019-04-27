---
title: CComObjectNoLock-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: 50dc4505c1da8df9efc0c9d0028461ef49c0840e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246299"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock-Klasse

Diese Klasse implementiert `IUnknown` eines zusammengesetzten Objekts, aber wird nicht erhöhen, die die Sperrenanzahl Modul im Konstruktor.

## <a name="syntax"></a>Syntax

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>Parameter

*Basis*<br/>
Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über eine beliebige andere Schnittstelle für das Objekt unterstützt werden sollen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Konstruktor.|
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt an.|
|[CComObjectNoLock::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die angeforderte Schnittstelle zurück.|
|[CComObjectNoLock::Release](#release)|Dekrementiert den Verweiszähler für das Objekt.|

## <a name="remarks"></a>Hinweise

`CComObjectNoLock` ist vergleichbar mit [CComObject](../../atl/reference/ccomobject-class.md) , implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) für einen zusammengesetzten Objekt; allerdings `CComObjectNoLock` zählt nicht erhöhen die Modul-Sperre im Konstruktor.

ATL verwendet `CComObjectNoLock` intern für Klassenfactorys. Im Allgemeinen verwenden Sie diese Klasse nicht direkt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="addref"></a>  CComObjectNoLock::AddRef

Inkrementiert den Verweiszähler für das Objekt an.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.

##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock

Der Konstruktor. Im Gegensatz zu [CComObject](../../atl/reference/ccomobject-class.md), die Sperrenanzahl des Moduls nicht inkrementiert.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>Parameter

<em>void\*</em><br/>
[in] Dieser unbenannte Parameter wird nicht verwendet. Sie vorhanden ist, für die Symmetrie mit anderen `CComXXXObjectXXX` Konstruktoren.

##  <a name="dtor"></a>  CComObjectNoLock:: ~ CComObjectNoLock

Der Destruktor.

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Hinweise

Gibt Sie frei, alle zugeordneten Ressourcen und ruft [FinalRelease](ccomobjectrootex-class.md#finalrelease).

##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
[in] Der Bezeichner der angeforderten Schnittstelle.

*ppvObject*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Iid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObject* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="release"></a>  CComObjectNoLock::Release

Dekrementiert den Verweiszähler für das Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In Debugbuilds `Release` gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich oder Tests zurück. In nicht-Debugbuilds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
