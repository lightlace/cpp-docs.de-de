---
title: CComObjectGlobal-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 141940ef5d5c7d23ea3cf049e64e9f4c6974fce0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076657"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal-Klasse

Diese Klasse verwaltet einen Verweiszähler für das Modul mit Ihrem `Base` Objekt.

## <a name="syntax"></a>Syntax

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>Parameter

*Basis*<br/>
Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über eine beliebige andere Schnittstelle für das Objekt unterstützt werden sollen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Der Konstruktor.|
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectGlobal::AddRef](#addref)|Implementiert eine globale `AddRef`.|
|[CComObjectGlobal::QueryInterface](#queryinterface)|Implementiert eine globale `QueryInterface`.|
|[CComObjectGlobal::Release](#release)|Implementiert eine globale `Release`.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Das während der Erstellung der zurückgegebene HRESULT enthält die `CComObjectGlobal` Objekt.|

## <a name="remarks"></a>Hinweise

`CComObjectGlobal` verwaltet einen Verweiszähler für das Modul mit Ihrem `Base` Objekt. `CComObjectGlobal` Stellt sicher, dass das Objekt wird nicht gelöscht werden, solange das Modul nicht freigegeben wird. Das Objekt wird nur entfernt werden, wenn der Verweiszähler für das gesamte Modul 0 (null) ist.

Verwenden Sie beispielsweise `CComObjectGlobal`, eine Klassenfactory kann enthalten ein allgemeine globales Objekt, das von allen Clients gemeinsam verwendet wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="addref"></a>  CComObjectGlobal::AddRef

Erhöht den Verweiszähler des Objekts um 1.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der bei der Diagnose hilfreich und Tests sein kann.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `AddRef` Aufrufe `_Module::Lock`, wobei `_Module` ist die globale Instanz des [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet wird.

##  <a name="ccomobjectglobal"></a>  CComObjectGlobal::CComObjectGlobal

Der Konstruktor. Aufrufe `FinalConstruct` und legt dann [M_hResFinalConstruct](#m_hresfinalconstruct) auf die `HRESULT` zurückgegebenes `FinalConstruct`.

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>Hinweise

Wenn Sie nicht Ihre Basisklasse von abgeleiteten [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), geben Sie an Ihre eigenen `FinalConstruct` Methode. Der Destruktor ruft `FinalRelease` auf.

##  <a name="dtor"></a>  CComObjectGlobal:: ~ CComObjectGlobal

Der Destruktor.

```
CComObjectGlobal();
```

### <a name="remarks"></a>Hinweise

Gibt Sie frei, alle zugeordneten Ressourcen und ruft [FinalRelease](ccomobjectrootex-class.md#finalrelease).

##  <a name="m_hresfinalconstruct"></a>  CComObjectGlobal::m_hResFinalConstruct

Enthält den HRESULT-Wert von aufrufenden `FinalConstruct` während der Erstellung der `CComObjectGlobal` Objekt.

```
HRESULT m_hResFinalConstruct;
```

##  <a name="queryinterface"></a>  CComObjectGlobal::QueryInterface

Ruft einen Zeiger auf den angeforderten Schnittstellenzeiger ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parameter

*IID*<br/>
[in] Die GUID der Schnittstelle angefordert wird.

*ppvObject*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger auf identifizierte Iid, oder NULL, wenn die Schnittstelle nicht gefunden wird.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

`QueryInterface` behandelt nur Schnittstellen in der COM-Zuordnungstabelle.

##  <a name="release"></a>  CComObjectGlobal::Release

Dekrementiert den Verweiszähler des Objekts um 1.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In Debugbuilds `Release` gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich und testen. In nicht-Debugbuilds `Release` gibt immer 0 zurück.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `Release` Aufrufe `_Module::Unlock`, wobei `_Module` ist die globale Instanz des [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet wird.

## <a name="see-also"></a>Siehe auch

[CComObjectStack-Klasse](../../atl/reference/ccomobjectstack-class.md)<br/>
[CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject-Klasse](../../atl/reference/ccomobject-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
