---
title: CComObjectNoLock-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76b8b3b329f3282a53eacb4fe27d6cfa79e08b7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078958"
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

*IID*<br/>
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
