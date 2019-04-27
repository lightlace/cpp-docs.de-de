---
title: CComPolyObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
ms.openlocfilehash: a8dbbc06d35d2606cc76e89cc555ba7f8577daa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246256"
---
# <a name="ccompolyobject-class"></a>CComPolyObject-Klasse

Diese Klasse implementiert `IUnknown` für ein Objekt zusammengesetzten oder aggregiert.

## <a name="syntax"></a>Syntax

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parameter

*contained*<br/>
Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComPolyObject::CComPolyObject](#ccompolyobject)|Der Konstruktor.|
|[CComPolyObject::~CComPolyObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComPolyObject::AddRef](#addref)|Inkrementiert Verweiszähler des Objekts.|
|[CComPolyObject::CreateInstance](#createinstance)|(Statisch) Können Sie zum Erstellen eines neuen **CComPolyObject <** `contained` **>** Objekt ohne den Aufwand für [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComPolyObject::FinalConstruct](#finalconstruct)|Führt die endgültige Initialisierung der `m_contained`.|
|[CComPolyObject::FinalRelease](#finalrelease)|Führt die endgültige Löschung von `m_contained`.|
|[CComPolyObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComPolyObject::Release](#release)|Dekrementiert die Verweiszähler des Objekts.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|Delegaten `IUnknown` an die äußere unbekannte aufgerufen wird, wenn das Objekt aggregiert wird, oder um die `IUnknown` des Objekts, wenn das Objekt nicht aggregiert werden.|

## <a name="remarks"></a>Hinweise

`CComPolyObject` implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) für ein Objekt zusammengesetzten oder aggregiert.

Wenn eine Instanz des `CComPolyObject` erstellt wird, wird den Wert des äußeren unbekannt aktiviert ist. Wenn auf NULL, `IUnknown` für einen zusammengesetzten Objekt implementiert wird. Wenn die äußere unbekannte ungleich NULL ist `IUnknown` wird für ein zusammengesetztes Objekt implementiert.

Der Vorteil der Verwendung `CComPolyObject` besteht darin, dass Sie vermeiden, dass beide [CComAggObject](../../atl/reference/ccomaggobject-class.md) und [CComObject](../../atl/reference/ccomobject-class.md) innerhalb des Moduls, die aggregierte und zusammengesetzten Fälle zu behandeln. Ein einzelnes `CComPolyObject` Objekt behandelt beide Fälle. Dies bedeutet, dass nur eine Kopie der Vtable und eine Kopie der Funktionen, die innerhalb des Moduls vorhanden sind. Wenn Ihre Vtable groß ist, kann dies Modulgröße erheblich verringern. Die Vtable klein ist, jedoch verwenden `CComPolyObject` kann dazu führen, etwas Modul größer, da sie nicht für ein Objekt zusammengesetzten oder aggregiert, optimiert ist wie `CComAggObject` und `CComObject`.

Wenn das DECLARE_POLY_AGGREGATABLE-Makro in der Klassendefinition des Objekts angegeben ist `CComPolyObject` verwendet werden, um das Objekt zu erstellen. DECLARE_POLY_AGGREGATABLE werden automatisch deklariert werden, wenn Sie ATL-Projektassistenten verwenden, um eine vollständige Kontrolle oder Internet Explorer-Steuerelement erstellen.

Wenn Sie aggregiert, die `CComPolyObject` Objekt verfügt über eine eigene `IUnknown`getrennt von des äußeren Objekts `IUnknown`, und verwaltet einen eigenen Verweiszähler. `CComPolyObject` verwendet [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) an die äußere unbekannte delegieren.

Weitere Informationen über die Aggregation finden Sie im Artikel [Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="addref"></a>  CComPolyObject::AddRef

Inkrementiert den Verweiszähler für das Objekt an.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.

##  <a name="ccompolyobject"></a>  CComPolyObject::CComPolyObject

Der Konstruktor.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Parameter

*pv*<br/>
[in] Ein Zeiger auf die äußere unbekannte, wenn das Objekt aggregiert werden, oder NULL, wenn das Objekt, wenn das Objekt nicht aggregiert werden.

### <a name="remarks"></a>Hinweise

Initialisiert die `CComContainedObject` Datenmember, [M_contained](#m_contained), und erhöht die Sperrenanzahl des Moduls.

Der Destruktor verringert die Modul Sperrenanzahl.

##  <a name="dtor"></a>  CComPolyObject:: ~ CComPolyObject

Der Destruktor.

```
~CComPolyObject();
```

### <a name="remarks"></a>Hinweise

Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](#finalrelease), und verringert die Modul Sperrenanzahl.

##  <a name="createinstance"></a>  CComPolyObject::CreateInstance

Können Sie zum Erstellen eines neuen **CComPolyObject <** `contained` **>** Objekt ohne den Aufwand für [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Parameter

*pp*<br/>
[out] Ein Zeiger auf eine **CComPolyObject <** `contained` **>** Zeiger. Wenn `CreateInstance` nicht erfolgreich ist, ist *pp* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Das zurückgegebene Objekt weist einer Verweisanzahl von 0 (null), weshalb `AddRef` verwenden Sie dann sofort `Release` , den Verweis auf den Objektzeiger freizugeben, wenn Sie fertig sind.

Wenn Sie nicht die Zugriff auf das Objekt direkten benötigen, aber dennoch, erstellen Sie ein neues Objekt ohne den Aufwand für möchten `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.

##  <a name="finalconstruct"></a>  CComPolyObject::FinalConstruct

Wird aufgerufen, während der letzten Stufen der Objektkonstruktion, diese Methode führt endgültige Initialisierung der [M_contained](#m_contained) -Datenmember.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="finalrelease"></a>  CComPolyObject::FinalRelease

Diese Methode aufgerufen wird, während die Zerstörung von Objekten, freigegeben werden. die [M_contained](#m_contained) -Datenmember.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComPolyObject::m_contained

Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) von Ihrer Klasse abgeleitetes Objekt.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parameter

*contained*<br/>
[in] Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.

### <a name="remarks"></a>Hinweise

`IUnknown` Ruft über `m_contained` werden an die äußere unbekannte delegiert, wenn das Objekt aggregiert wird, oder mit der `IUnknown` dieses Objekts, wenn das Objekt nicht aggregiert werden.

##  <a name="queryinterface"></a>  CComPolyObject::QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parameter

*Q*<br/>
Die COM-Schnittstelle.

*iid*<br/>
[in] Der Bezeichner der angeforderten Schnittstelle.

*ppvObject*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Iid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObject* auf NULL festgelegt ist.

*pp*<br/>
[out] Ein Zeiger auf die Schnittstelle identifizierte `__uuidof(Q)`.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Für ein zusammengesetztes Objekt, wenn die angeforderte Schnittstelle wird `IUnknown`, `QueryInterface` gibt einen Zeiger auf die aggregierten Objekts `IUnknown` und inkrementiert den Verweiszähler. Andernfalls Schnittstelle durch diese Methode fragt den `CComContainedObject` Datenmember, [M_contained](#m_contained).

##  <a name="release"></a>  CComPolyObject::Release

Dekrementiert den Verweiszähler für das Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In Debugbuilds `Release` gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich oder Tests zurück. In aufgeführt Builds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
