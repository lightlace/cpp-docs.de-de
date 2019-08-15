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
ms.openlocfilehash: a2051932413d8658eb7cedb67ed0eab2077b599d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497132"
---
# <a name="ccomobject-class"></a>CComObject-Klasse

Diese Klasse implementiert `IUnknown` für ein nicht aggregiertes-Objekt.

## <a name="syntax"></a>Syntax

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>Parameter

*Sock*<br/>
Die von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)abgeleitete Klasse sowie von anderen Schnittstellen, die Sie für das Objekt unterstützen möchten.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComObject::CComObject](#ccomobject)|Der Konstruktor.|
|[CComObject::~CComObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComObject::AddRef](#addref)|Inkremente den Verweis Zähler für das Objekt.|
|[CComObject::CreateInstance](#createinstance)|Kum Erstellt ein neues `CComObject` -Objekt.|
|[CComObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|
|[CComObject::Release](#release)|Dekremente den Verweis Zähler für das Objekt.|

## <a name="remarks"></a>Hinweise

`CComObject`implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) für ein nicht aggregiertes Objekt. Aufrufe von `QueryInterface` `CComObjectRootEx`, `AddRef` und`Release` werden jedoch an delegiert.

Weitere Informationen zum Verwenden von `CComObject`finden Sie im Artikel [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComObject`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="addref"></a>CComObject:: adressf

Inkremente den Verweis Zähler für das Objekt.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Diese Funktion gibt den neuen inkrementierten Verweis Zähler für das-Objekt zurück. Dieser Wert kann für Diagnose-oder Testzwecke nützlich sein.

##  <a name="ccomobject"></a>CComObject:: CComObject

Der Konstruktor erhöht die Modul Sperr Anzahl.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>Parameter

<em>void\*</em><br/>
in Dieser unbenannte Parameter wird nicht verwendet. Es ist für die Symmetrie mit `CComXXXObjectXXX` anderen Konstruktoren vorhanden.

### <a name="remarks"></a>Hinweise

Der Dekonstruktor Dekremente ihn.

Wenn ein `CComObject`von abgeleitetes Objekt mit dem **New** -Operator erfolgreich erstellt wird, ist der anfängliche Verweis Zähler 0. Um den Verweis Zähler auf den richtigen Wert (1) festzulegen, führen Sie einen Rückruf für die [adressf](#addref) -Funktion aus.

##  <a name="dtor"></a>CComObject:: ~ CComObject

Der Destruktor.

```
CComObject();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei, ruft [FinalRelease](ccomobjectrootex-class.md#finalrelease)auf und Dekremente die Anzahl der Modul sperren.

##  <a name="createinstance"></a>CComObject:: kreateinstance

Diese statische Funktion ermöglicht das Erstellen eines neuen **CComObject-<** `Base` **>** Objekts ohne den Aufwand von [cokreateinstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>Parameter

*pp*<br/>
vorgenommen Ein Zeiger auf einen **CComObject-<** `Base` **>** Zeiger. Wenn `CreateInstance` nicht erfolgreich ist, wird *PP* auf NULL festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Das zurückgegebene Objekt hat einen Verweis Zähler von NULL. führen `AddRef` Sie daher sofort einen `Release` Rückruf aus, und verwenden Sie dann, um den Verweis auf den Objekt Zeiger freizugeben, wenn Sie fertig sind.

Wenn Sie keinen direkten Zugriff auf das Objekt benötigen, aber trotzdem ein neues Objekt ohne den mehr Aufwand von `CoCreateInstance`erstellen möchten, verwenden Sie stattdessen [CComCoClass:: kreateinstance](../../atl/reference/ccomcoclass-class.md#createinstance) .

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

##  <a name="queryinterface"></a>CComObject:: QueryInterface

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

##  <a name="release"></a>CComObject:: Release

Dekremente den Verweis Zähler für das Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

Diese Funktion gibt den neuen dekrementierten Verweis Zähler für das-Objekt zurück. In Debugbuilds kann der Rückgabewert für Diagnose-oder Testzwecke nützlich sein. In nicht Debugbuilds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)<br/>
[CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
