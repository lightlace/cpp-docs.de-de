---
title: CComCachedTearOffObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: d993a349d38342bda30a83dfdbe25577953799b3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497540"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject-Klasse

Diese Klasse implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) für eine abtrennbare Schnittstelle.

## <a name="syntax"></a>Syntax

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parameter

*ständige*<br/>
Die von abgeleitete Klasse, die von `CComTearOffObjectBase` abgeleitet ist, und die Schnittstellen, die von dem abzurufenden Objekt unterstützt werden sollen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Der Konstruktor.|
|[CComCachedTearOffObject::~CComCachedTearOffObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComCachedTearOffObject::AddRef](#addref)|Erhöht den Verweis Zähler für ein `CComCachedTearOffObject` -Objekt.|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Ruft den `m_contained::FinalConstruct` (die Methode der abtrenn Methode der Klasse) auf.|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Ruft den `m_contained::FinalRelease` (die Methode der abtrenn Methode der Klasse) auf.|
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die `IUnknown` `CComCachedTearOffObject` des-Objekts oder auf die angeforderte Schnittstelle der abtrenn Klasse (der-Klasse `contained`) zurück.|
|[CComCachedTearOffObject::Release](#release)|Verringert den Verweis Zähler für ein `CComCachedTearOffObject` -Objekt und zerstört ihn, wenn der Verweis Zähler 0 (null) ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|Ein `CComContainedObject` -Objekt, das von der abgeleiteten Klasse (der `contained`-Klasse) abgeleitet ist.|

## <a name="remarks"></a>Hinweise

`CComCachedTearOffObject`implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) für eine abtrennbare Schnittstelle. Diese Klasse unterscheidet `CComTearOffObject` sich von `CComCachedTearOffObject` in, der `IUnknown`über eine eigene, getrennt vom Besitzer `IUnknown` Objekt (der Besitzer ist das Objekt, für das das Abbild erstellt wird). `CComCachedTearOffObject`behält seinen eigenen Verweis Zähler für den `IUnknown` und löscht sich selbst, sobald der Verweis Zähler Null ist. Wenn Sie jedoch eine Abfrage für eine der abtrenn Schnittstellen durch `IUnknown` führt, wird der Verweis Zähler der Besitzer Objekte inkrementiert.

Wenn das `CComCachedTearOffObject` Objekt, das das Abbild implementiert, bereits instanziiert ist und die abtrenn Schnittstelle erneut abgefragt wird, wird das gleiche `CComCachedTearOffObject` Objekt wieder verwendet. Wenn im Gegensatz dazu eine durch eine `CComTearOffObject` implementierte Schnittstelle, die durch das Besitzer Objekt erneut abgefragt wird, eine andere instanziiert wird, wird eine andere `CComTearOffObject` instanziiert.

Die Owner-Klasse muss `FinalRelease` implementieren und `Release` für den zwischen `IUnknown` gespeicherten für `CComCachedTearOffObject`den aufzurufen, wodurch der Verweis Zähler verringert wird. Dies bewirkt `CComCachedTearOffObject` `FinalRelease` , dass der aufgerufen wird und die Löschung gelöscht wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="addref"></a>CComCachedTearOffObject:: adressf

Erhöht den Verweis Zähler des `CComCachedTearOffObject` -Objekts um 1.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose und das Testen nützlich sein kann.

##  <a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject:: CComCachedTearOffObject

Der Konstruktor.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>Parameter

*teuren*<br/>
in Zeiger auf den `IUnknown` `CComCachedTearOffObject`von.

### <a name="remarks"></a>Hinweise

Initialisiert den `CComContainedObject` Member, [m_contained](#m_contained).

##  <a name="dtor"></a>CComCachedTearOffObject:: ~ CComCachedTearOffObject

Der Destruktor.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei und ruft [FinalRelease](#finalrelease)auf.

##  <a name="finalconstruct"></a>CComCachedTearOffObject:: FinalConstruct

Aufrufe `m_contained::FinalConstruct` von Create `m_contained`, das `CComContainedObject`> Objekt, das <  `contained`für den Zugriff auf die Schnittstelle verwendet wird, die von ihrer abtrenn Klasse implementiert wird.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="finalrelease"></a>CComCachedTearOffObject:: FinalRelease

Aufrufe `m_contained::FinalRelease` von Free `m_contained`, das `CComContainedObject` >-Objekt`contained`. < 

```
void FinalRelease();
```

##  <a name="m_contained"></a>CComCachedTearOffObject:: m_contained

Ein [ccomcontainedobject](../../atl/reference/ccomcontainedobject-class.md) -Objekt, das von der abgeleiteten Klasse abgeleitet ist.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>Parameter

*ständige*<br/>
in Die von abgeleitete Klasse, die von `CComTearOffObjectBase` abgeleitet ist, und die Schnittstellen, die von dem abzurufenden Objekt unterstützt werden sollen.

### <a name="remarks"></a>Hinweise

Die- `m_contained` `QueryInterface`Methoden erben werden verwendet, um auf die abtrennbare Schnittstelle in der abzurufenden Klasse durch das zwischengespeicherte, `FinalConstruct`und `FinalRelease`das zwischengespeicherte abzurufende Objekt zuzugreifen.

##  <a name="queryinterface"></a>CComCachedTearOffObject:: QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Der GUID der angeforderten Schnittstelle.

*ppvObject*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch *IID*identifiziert wird, oder NULL, wenn die Schnittstelle nicht gefunden wurde.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Wenn die angeforderte Schnitt `IUnknown`Stelle ist, gibt einen Zeiger `CComCachedTearOffObject`auf die `IUnknown` eigene zurück und erhöht den Verweis Zähler. Andernfalls werden Abfragen für die-Schnittstelle in ihrer abtrenn Klasse mithilfe der [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) -Methode `CComObjectRootEx`, die von geerbt wurde.

##  <a name="release"></a>CComCachedTearOffObject:: Release

Dekremente den Verweis Zähler um 1 und, wenn der Verweis Zähler 0 ist, das `CComCachedTearOffObject` -Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In nicht Debugbuilds gibt immer 0 zurück. In Debugbuilds gibt einen Wert zurück, der für die Diagnose oder das Testen nützlich sein kann.

## <a name="see-also"></a>Siehe auch

[CComTearOffObject-Klasse](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
