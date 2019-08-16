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
ms.openlocfilehash: 8b05284104f9d2e5e7704bceaee6f8adf9a33aac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497658"
---
# <a name="ccomaggobject-class"></a>CComAggObject-Klasse

Diese Klasse implementiert die [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) -Schnittstelle für ein aggregiertes Objekt. Definitionsgemäß ist ein aggregiertes Objekt in einem äußeren Objekt enthalten. Die `CComAggObject` -Klasse ähnelt der [CComObject-Klasse](../../atl/reference/ccomobject-class.md), mit der Ausnahme, dass Sie eine Schnittstelle verfügbar macht, auf die externe Clients direkt zugreifen können.

## <a name="syntax"></a>Syntax

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parameter

*ständige*<br/>
Die von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)abgeleitete Klasse sowie von anderen Schnittstellen, die Sie für das Objekt unterstützen möchten.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComAggObject::CComAggObject](#ccomaggobject)|Der Konstruktor.|
|[CComAggObject::~CComAggObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComAggObject::AddRef](#addref)|Inkremente den Verweis Zähler für das aggregierte Objekt.|
|[CComAggObject::CreateInstance](#createinstance)|Diese statische Funktion ermöglicht es Ihnen, ein neues **CComAggObject** `contained` -Objekt < **>** zu erstellen, ohne den Aufwand von [cokreateinstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)zu erhöhen.|
|[CComAggObject::FinalConstruct](#finalconstruct)|Führt die abschließende Initialisierung `m_contained`von aus.|
|[CComAggObject::FinalRelease](#finalrelease)|Führt die endgültige Zerstörung `m_contained`von aus.|
|[CComAggObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComAggObject::Release](#release)|Dekremente den Verweis Zähler für das aggregierte Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComAggObject::m_contained](#m_contained)|Delegiert `IUnknown` Aufrufe an das äußere unbekannte.|

## <a name="remarks"></a>Hinweise

`CComAggObject`implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) für ein aggregiertes Objekt. `CComAggObject`verfügt über eine `IUnknown` eigene Schnittstelle, die von der `IUnknown` Schnittstelle des äußeren Objekts getrennt ist und einen eigenen Verweis Zähler beibehält.

Weitere Informationen zur Aggregation finden Sie im Artikel [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="addref"></a>CComAggObject:: adressf

Inkremente den Verweis Zähler für das aggregierte Objekt.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose oder das Testen nützlich sein kann.

##  <a name="ccomaggobject"></a>CComAggObject:: CComAggObject

Der Konstruktor.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Parameter

*teuren*<br/>
in Das äußere unbekannte.

### <a name="remarks"></a>Hinweise

Initialisiert den `CComContainedObject` Member [m_contained](#m_contained)und Inkremente die Anzahl der Modul sperren.

Der Dekonstruktor Dekremente die Modul Sperr Anzahl.

##  <a name="dtor"></a>CComAggObject:: ~ CComAggObject

Der Destruktor.

```
~CComAggObject();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei, ruft [FinalRelease](#finalrelease)auf und Dekremente die Anzahl der Modul sperren.

##  <a name="createinstance"></a>CComAggObject:: up-Eingabe

Diese statische Funktion ermöglicht es Ihnen, ein neues **CComAggObject** `contained` -Objekt < **>** zu erstellen, ohne den Aufwand von [cokreateinstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)zu erhöhen.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Parameter

*pp*<br/>
vorgenommen Ein Zeiger auf einen<em>enthaltenen</em> **>** **\<CComAggObject**-Zeiger. Wenn `CreateInstance` nicht erfolgreich ist, wird *PP* auf NULL festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Das zurückgegebene Objekt hat einen Verweis Zähler von NULL. führen `AddRef` Sie daher sofort einen `Release` Rückruf aus, und verwenden Sie dann, um den Verweis auf den Objekt Zeiger freizugeben, wenn Sie fertig sind.

Wenn Sie keinen direkten Zugriff auf das Objekt benötigen, aber trotzdem ein neues Objekt ohne den mehr Aufwand von `CoCreateInstance`erstellen möchten, verwenden Sie stattdessen [CComCoClass:: kreateinstance](../../atl/reference/ccomcoclass-class.md#createinstance) .

##  <a name="finalconstruct"></a>CComAggObject:: FinalConstruct

Wird während der letzten Phasen der Objekt Erstellung aufgerufen. diese Methode führt jede abschließende Initialisierung für den [m_contained](#m_contained) -Member aus.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="finalrelease"></a>CComAggObject:: FinalRelease

Wird während der Objekt Zerstörung aufgerufen, gibt diese Methode den [m_contained](#m_contained) -Member frei.

```
void FinalRelease();
```

##  <a name="m_contained"></a>CComAggObject:: m_contained

Ein [ccomcontainedobject](../../atl/reference/ccomcontainedobject-class.md) -Objekt, das von der-Klasse abgeleitet ist.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parameter

*ständige*<br/>
in Die von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)abgeleitete Klasse sowie von anderen Schnittstellen, die Sie für das Objekt unterstützen möchten.

### <a name="remarks"></a>Hinweise

Alle `IUnknown` Aufrufe durch `m_contained` werden an den äußeren unbekannten delegiert.

##  <a name="queryinterface"></a>CComAggObject:: QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

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

### <a name="remarks"></a>Hinweise

Wenn die angeforderte Schnitt `IUnknown`Stelle `QueryInterface` ist, gibt einen Zeiger auf den eigenen `IUnknown` des aggregierten Objekts zurück und erhöht den Verweis Zähler. Andernfalls fragt diese Methode die Schnittstelle über den `CComContainedObject` Member ab, [m_contained](#m_contained).

##  <a name="release"></a>CComAggObject:: Release

Dekremente den Verweis Zähler für das aggregierte Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In Debugbuilds `Release` gibt einen Wert zurück, der für die Diagnose oder das Testen nützlich sein kann. In nicht Debugbuilds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[CComObject-Klasse](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
