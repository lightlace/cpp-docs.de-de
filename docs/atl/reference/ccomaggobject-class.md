---
title: CComAggObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: 52cdddb1d922ca21e24122422ca14d9c12d13a83
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301661"
---
# <a name="ccomaggobject-class"></a>CComAggObject-Klasse

Diese Klasse implementiert die [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) Schnittstelle für ein zusammengesetztes Objekt. Definitionsgemäß ist ein zusammengesetztes Objekt in einem äußeren Objekt enthalten. Die `CComAggObject` Klasse ist vergleichbar mit der [CComObject-Klasse](../../atl/reference/ccomobject-class.md), außer dass er eine Schnittstelle verfügbar macht, die für externe Clients direkt zugegriffen werden kann.

## <a name="syntax"></a>Syntax

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parameter

*contained*<br/>
Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComAggObject::CComAggObject](#ccomaggobject)|Der Konstruktor.|
|[CComAggObject::~CComAggObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComAggObject::AddRef](#addref)|Inkrementiert den Verweiszähler des aggregierten Objekts.|
|[CComAggObject::CreateInstance](#createinstance)|Diese statischen Funktion können Sie zum Erstellen eines neuen **CComAggObject <** `contained` **>** Objekt ohne den Aufwand für [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComAggObject::FinalConstruct](#finalconstruct)|Führt die endgültige Initialisierung der `m_contained`.|
|[CComAggObject::FinalRelease](#finalrelease)|Führt die endgültige Löschung von `m_contained`.|
|[CComAggObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComAggObject::Release](#release)|Dekrementiert den Verweiszähler des aggregierten Objekts.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComAggObject::m_contained](#m_contained)|Delegaten `IUnknown` Aufrufe an die äußere unbekannte.|

## <a name="remarks"></a>Hinweise

`CComAggObject` implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) für ein zusammengesetztes Objekt. `CComAggObject` verfügt über eine eigene `IUnknown` -Schnittstelle, des äußeren Objekts als `IUnknown` -Schnittstelle und verwaltet einen eigenen Verweiszähler.

Weitere Informationen über die Aggregation finden Sie im Artikel [Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="addref"></a>  CComAggObject::AddRef

Inkrementiert den Verweiszähler des aggregierten Objekts.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.

##  <a name="ccomaggobject"></a>  CComAggObject::CComAggObject

Der Konstruktor.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Parameter

*pv*<br/>
[in] Die äußere unbekannte.

### <a name="remarks"></a>Hinweise

Initialisiert die `CComContainedObject` Member [M_contained](#m_contained), und erhöht die Sperrenanzahl des Moduls.

Der Destruktor verringert die Modul Sperrenanzahl.

##  <a name="dtor"></a>  CComAggObject:: ~ CComAggObject

Der Destruktor.

```
~CComAggObject();
```

### <a name="remarks"></a>Hinweise

Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](#finalrelease), und verringert die Modul Sperrenanzahl.

##  <a name="createinstance"></a>  CComAggObject::CreateInstance

Diese statischen Funktion können Sie zum Erstellen eines neuen **CComAggObject <** `contained` **>** Objekt ohne den Aufwand für [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Parameter

*pp*<br/>
[out] Ein Zeiger auf eine **CComAggObject\<**<em>enthaltenen</em> **>** Zeiger. Wenn `CreateInstance` nicht erfolgreich ist, ist *pp* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Das zurückgegebene Objekt weist einer Verweisanzahl von 0 (null), weshalb `AddRef` verwenden Sie dann sofort `Release` , den Verweis auf den Objektzeiger freizugeben, wenn Sie fertig sind.

Wenn Sie die nicht den Zugriff auf das Objekt weisen müssen, aber dennoch, erstellen Sie ein neues Objekt ohne den Aufwand für möchten `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.

##  <a name="finalconstruct"></a>  CComAggObject::FinalConstruct

Wird aufgerufen, während der letzten Stufen der Objektkonstruktion, diese Methode führt endgültige Initialisierung der [M_contained](#m_contained) Member.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="finalrelease"></a>  CComAggObject::FinalRelease

Diese Methode aufgerufen wird, während die Zerstörung von Objekten, freigegeben werden. die [M_contained](#m_contained) Member.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComAggObject::m_contained

Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) von Ihrer Klasse abgeleitetes Objekt.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parameter

*contained*<br/>
[in] Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.

### <a name="remarks"></a>Hinweise

Alle `IUnknown` ruft `m_contained` werden an die äußere unbekannte delegiert.

##  <a name="queryinterface"></a>  CComAggObject::QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
[in] Der Bezeichner der angeforderten Schnittstelle.

*ppvObject*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Iid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObject* auf NULL festgelegt ist.

*pp*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom Typ `Q`. Wenn das Objekt nicht über diese Schnittstelle unterstützt *pp* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Wenn die angeforderte Schnittstelle wird `IUnknown`, `QueryInterface` gibt einen Zeiger auf die aggregierten Objekts `IUnknown` und inkrementiert den Verweiszähler. Andernfalls Schnittstelle durch diese Methode fragt den `CComContainedObject` Member [M_contained](#m_contained).

##  <a name="release"></a>  CComAggObject::Release

Dekrementiert den Verweiszähler des aggregierten Objekts.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In Debugbuilds `Release` gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich oder Tests zurück. In nicht-Debugbuilds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[CComObject-Klasse](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
