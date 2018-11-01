---
title: CComObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
ms.openlocfilehash: 57c054915ce98dd8cff6bb772cdd40f4b0f2b768
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660472"
---
# <a name="ccomobject-class"></a>CComObject-Klasse

Diese Klasse implementiert `IUnknown` für einen zusammengesetzten Objekt.

## <a name="syntax"></a>Syntax

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>Parameter

*Basis*<br/>
Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComObject::CComObject](#ccomobject)|Der Konstruktor.|
|[CComObject::~CComObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComObject::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt an.|
|[CComObject::CreateInstance](#createinstance)|(Statisch) Erstellt ein neues `CComObject` Objekt.|
|[CComObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComObject::Release](#release)|Dekrementiert den Verweiszähler für das Objekt.|

## <a name="remarks"></a>Hinweise

`CComObject` implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) für einen zusammengesetzten Objekt. Ruft jedoch um `QueryInterface`, `AddRef`, und `Release` delegiert werden `CComObjectRootEx`.

Weitere Informationen zur Verwendung von `CComObject`, finden Sie im Artikel [Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComObject`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="addref"></a>  CComObject::AddRef

Inkrementiert den Verweiszähler für das Objekt an.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Diese Funktion gibt den neuen inkrementiert Verweiszähler für das Objekt zurück. Dieser Wert kann für die Diagnose oder testen hilfreich sein.

##  <a name="ccomobject"></a>  CComObject::CComObject

Der Konstruktor erhöht die Sperrenanzahl des Moduls.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>Parameter

<em>void\*</em><br/>
[in] Dieser unbenannte Parameter wird nicht verwendet. Sie vorhanden ist, für die Symmetrie mit anderen `CComXXXObjectXXX` Konstruktoren.

### <a name="remarks"></a>Hinweise

Der Destruktor verringert es.

Wenn eine `CComObject`-abgeleitetes Objekt wurde erfolgreich erstellt mithilfe der **neue** Operatoren und die Initiale Verweisanzahl ist 0. Um die Anzahl der Verweise auf den entsprechenden Wert (1) festzulegen, stellen Sie einen Aufruf der ["AddRef"](#addref) Funktion.

##  <a name="dtor"></a>  CComObject:: ~ CComObject

Der Destruktor.

```
CComObject();
```

### <a name="remarks"></a>Hinweise

Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](ccomobjectrootex-class.md#finalrelease), und verringert die Modul Sperrenanzahl.

##  <a name="createinstance"></a>  CComObject::CreateInstance

Diese statischen Funktion können Sie zum Erstellen eines neuen **CComObject <** `Base` **>** Objekt, ohne den Aufwand für [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>Parameter

*PP*<br/>
[out] Ein Zeiger auf eine **CComObject <** `Base` **>** Zeiger. Wenn `CreateInstance` nicht erfolgreich ist, ist *pp* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Das zurückgegebene Objekt weist einer Verweisanzahl von 0 (null), weshalb `AddRef` verwenden Sie dann sofort `Release` , den Verweis auf den Objektzeiger freizugeben, wenn Sie fertig sind.

Wenn Sie die nicht den Zugriff auf das Objekt weisen müssen, aber dennoch, erstellen Sie ein neues Objekt ohne den Aufwand für möchten `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

##  <a name="queryinterface"></a>  CComObject::QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parameter

*IID*<br/>
[in] Der Bezeichner der angeforderten Schnittstelle.

*ppvObject*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Iid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObject* auf NULL festgelegt ist.

*PP*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom Typ `Q`. Wenn das Objekt nicht über diese Schnittstelle unterstützt *pp* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="release"></a>  CComObject::Release

Dekrementiert den Verweiszähler für das Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

Diese Funktion gibt den neuen dekrementiert Verweiszähler für das Objekt zurück. In Debugbuilds möglicherweise der Rückgabewert bei der Diagnose hilfreich oder testen. In nicht-Debugbuilds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)<br/>
[CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
