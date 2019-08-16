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
ms.openlocfilehash: deed29b5fb80ea8bbd06b3d50f45e38740b1619f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497150"
---
# <a name="ccompolyobject-class"></a>CComPolyObject-Klasse

Diese Klasse implementiert `IUnknown` für ein aggregiertes oder nicht aggregiertes Objekt.

## <a name="syntax"></a>Syntax

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parameter

*ständige*<br/>
Die von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)abgeleitete Klasse sowie von anderen Schnittstellen, die Sie für das Objekt unterstützen möchten.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComPolyObject::CComPolyObject](#ccompolyobject)|Der Konstruktor.|
|[CComPolyObject::~CComPolyObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComPolyObject::AddRef](#addref)|Inkremente den Verweis Zähler des Objekts.|
|[CComPolyObject::CreateInstance](#createinstance)|Kum Ermöglicht das Erstellen eines neuen **CComPolyObject** `contained` -Objekts < **>** Objekts ohne den Aufwand von [cokreateinstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComPolyObject::FinalConstruct](#finalconstruct)|Führt die abschließende Initialisierung `m_contained`von aus.|
|[CComPolyObject::FinalRelease](#finalrelease)|Führt die endgültige Zerstörung `m_contained`von aus.|
|[CComPolyObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComPolyObject::Release](#release)|Dekremente den Verweis Zähler des Objekts.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|Delegiert `IUnknown` Aufrufe an den äußeren unbekannten, wenn das Objekt aggregiert wird, oder `IUnknown` auf den des Objekts, wenn das Objekt nicht aggregiert wird.|

## <a name="remarks"></a>Hinweise

`CComPolyObject`implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) für ein aggregiertes oder nicht aggregiertes Objekt.

Wenn eine Instanz von `CComPolyObject` erstellt wird, wird der Wert des äußeren unbekannten aktiviert. Wenn er NULL ist, `IUnknown` wird für ein nicht aggregiertes Objekt implementiert. Wenn das äußere unbekannte nicht NULL ist, `IUnknown` wird für ein aggregiertes Objekt implementiert.

Der Vorteil der Verwendung `CComPolyObject` von besteht darin, dass es nicht möglich ist, dass sowohl [CComAggObject](../../atl/reference/ccomaggobject-class.md) als auch [CComObject](../../atl/reference/ccomobject-class.md) in Ihrem Modul vorhanden sind, um die aggregierten und nicht aggregierten Fälle zu verarbeiten. Ein einzelnes `CComPolyObject` -Objekt behandelt beide Fälle. Dies bedeutet, dass nur eine Kopie der vtable und eine Kopie der Funktionen in Ihrem Modul vorhanden sind. Wenn Ihre Vtable groß ist, kann dies die Modulgröße erheblich verringern. Wenn die Vtable jedoch klein ist, kann die `CComPolyObject` Verwendung von zu einer etwas größeren Modulgröße führen, da Sie nicht für ein aggregiertes oder nicht aggregiertes Objekt `CComAggObject` wie und `CComObject`optimiert ist.

Wenn das DECLARE_POLY_AGGREGATABLE-Makro in der Klassendefinition des-Objekts angegeben `CComPolyObject` wird, wird zum Erstellen des-Objekts verwendet. DECLARE_POLY_AGGREGATABLE wird automatisch deklariert, wenn Sie den ATL-Projekt-Assistenten verwenden, um ein vollständiges Steuerelement oder ein Internet Explorer-Steuerelement zu erstellen.

Wenn das Objekt aggregiert `CComPolyObject` wird, verfügt das `IUnknown`Objekt über ein eigenes, getrennt `IUnknown`vom äußeren Objekt und verwaltet seinen eigenen Verweis Zähler. `CComPolyObject`verwendet [ccomcontainedobject](../../atl/reference/ccomcontainedobject-class.md) , um an den äußeren unbekannten Delegaten zu delegieren.

Weitere Informationen zur Aggregation finden Sie im Artikel [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="addref"></a>CComPolyObject:: adressf

Inkremente den Verweis Zähler für das Objekt.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose oder das Testen nützlich sein kann.

##  <a name="ccompolyobject"></a>CComPolyObject:: CComPolyObject

Der Konstruktor.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Parameter

*teuren*<br/>
in Ein Zeiger auf das äußere unbekannte, wenn das Objekt aggregiert werden soll, oder NULL, wenn das Objekt nicht aggregiert wird.

### <a name="remarks"></a>Hinweise

Initialisiert den `CComContainedObject` Datenmember [m_contained](#m_contained)und Inkremente die Modul Sperr Anzahl.

Der Dekonstruktor Dekremente die Modul Sperr Anzahl.

##  <a name="dtor"></a>CComPolyObject:: ~ CComPolyObject

Der Destruktor.

```
~CComPolyObject();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei, ruft [FinalRelease](#finalrelease)auf und Dekremente die Anzahl der Modul sperren.

##  <a name="createinstance"></a>CComPolyObject:: kreateinstance

Ermöglicht das Erstellen eines neuen **CComPolyObject** `contained` -Objekts < **>** Objekts ohne den Aufwand von [cokreateinstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Parameter

*pp*<br/>
vorgenommen Ein Zeiger auf einen **CComPolyObject-<** `contained` **>** Zeiger. Wenn `CreateInstance` nicht erfolgreich ist, wird *PP* auf NULL festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Das zurückgegebene Objekt hat einen Verweis Zähler von NULL. führen `AddRef` Sie daher sofort einen `Release` Rückruf aus, und verwenden Sie dann, um den Verweis auf den Objekt Zeiger freizugeben, wenn Sie fertig sind.

Wenn Sie keinen direkten Zugriff auf das Objekt benötigen, aber trotzdem ein neues Objekt ohne den mehr Aufwand von `CoCreateInstance`erstellen möchten, verwenden Sie stattdessen [CComCoClass:: kreateinstance](../../atl/reference/ccomcoclass-class.md#createinstance) .

##  <a name="finalconstruct"></a>CComPolyObject:: FinalConstruct

Wird während der letzten Phasen der Objekt Erstellung aufgerufen. diese Methode führt jede abschließende Initialisierung für den [m_contained](#m_contained) -Datenmember aus.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="finalrelease"></a>CComPolyObject:: FinalRelease

Wird während der Objekt Zerstörung aufgerufen, gibt diese Methode den [m_contained](#m_contained) -Datenmember frei.

```
void FinalRelease();
```

##  <a name="m_contained"></a>CComPolyObject:: m_contained

Ein [ccomcontainedobject](../../atl/reference/ccomcontainedobject-class.md) -Objekt, das von der-Klasse abgeleitet ist.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parameter

*ständige*<br/>
in Die von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)abgeleitete Klasse sowie von anderen Schnittstellen, die Sie für das Objekt unterstützen möchten.

### <a name="remarks"></a>Hinweise

`IUnknown`Aufrufe durch `m_contained` werden an das äußere unbekannte delegiert, wenn das Objekt aggregiert wird, oder auf `IUnknown` den dieses Objekts, wenn das Objekt nicht aggregiert wird.

##  <a name="queryinterface"></a>CComPolyObject:: QueryInterface

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
in Der Bezeichner der angeforderten Schnittstelle.

*ppvObject*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch *IID*identifiziert wird. Wenn das Objekt diese Schnittstelle nicht unterstützt, wird *ppvobject* auf NULL festgelegt.

*pp*<br/>
vorgenommen Ein Zeiger auf die Schnittstelle, `__uuidof(Q)`die durch identifiziert wird.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Gibt bei einem aggregierten Objekt, wenn die angeforderte `IUnknown`Schnitt `QueryInterface` Stelle ist, einen Zeiger auf den eigenen `IUnknown` des aggregierten Objekts zurück und erhöht den Verweis Zähler. Andernfalls fragt diese Methode die Schnittstelle über den `CComContainedObject` Datenmember [m_contained](#m_contained)ab.

##  <a name="release"></a>CComPolyObject:: Release

Dekremente den Verweis Zähler für das Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In Debugbuilds `Release` gibt einen Wert zurück, der für die Diagnose oder das Testen nützlich sein kann. In nicht Debugbuilds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
