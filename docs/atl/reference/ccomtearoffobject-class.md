---
title: CcomTearOffObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: 0d27a6fa3c0070cd32c78971a7544327c51d4393
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496918"
---
# <a name="ccomtearoffobject-class"></a>CcomTearOffObject-Klasse

Diese Klasse implementiert eine deaktivierte Schnittstelle.

## <a name="syntax"></a>Syntax

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Parameter

*Sock*<br/>
Die von abgeleitete Klasse, die von `CComTearOffObjectBase` abgeleitet ist, und die Schnittstellen, die von dem abzurufenden Objekt unterstützt werden sollen.

ATL implementiert seine Debugschnittstellen in `CComTearOffObjectBase` zwei Phasen – die Methoden behandeln den Verweis Zähler und `QueryInterface`, während `CComTearOffObject` [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)implementiert.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Der Konstruktor.|
|[CComTearOffObject::~CComTearOffObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComTearOffObject::AddRef](#addref)|Erhöht den Verweis Zähler für ein `CComTearOffObject` -Objekt.|
|[CComTearOffObject::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die angeforderte Schnittstelle entweder in der abzurufenden Klasse oder der Besitzer Klasse zurück.|
|[CComTearOffObject::Release](#release)|Verringert den Verweis Zähler für ein `CComTearOffObject` -Objekt und zerstört diesen.|

### <a name="ccomtearoffobjectbase-methods"></a>Ccomtearoffobjectbase-Methoden

|||
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Konstruktor.|

### <a name="ccomtearoffobjectbase-data-members"></a>Ccomtearoffobjectbase-Datenmember

|||
|-|-|
|[m_pOwner](#m_powner)|Ein Zeiger auf einen `CComObject` , der von der Besitzer Klasse abgeleitet ist.|

## <a name="remarks"></a>Hinweise

`CComTearOffObject`implementiert eine abtrennbare Schnittstelle als separates Objekt, das nur instanziiert wird, wenn diese Schnittstelle abgefragt wird. Die Löschung wird gelöscht, wenn der Verweis Zähler Null wird. In der Regel erstellen Sie eine abtrenn Schnittstelle für eine Schnittstelle, die selten verwendet wird, da durch die Verwendung eines deaktivierten in allen Instanzen des Haupt Objekts ein vtable-Zeiger gespeichert wird.

Sie sollten die Klasse ableiten, die das Abbild von `CComTearOffObjectBase` und von den Schnittstellen implementiert, die von dem abzurufenden Objekt unterstützt werden sollen. `CComTearOffObjectBase`ist für die Besitzer Klasse und das Thread Modellvorlagen basiert. Die Owner-Klasse ist die Klasse des Objekts, für das eine Löschung implementiert wird. Wenn Sie kein Thread Modell angeben, wird das standardmäßige Thread Modell verwendet.

Sie sollten eine COM-Zuordnung für Ihre abtrenn Klasse erstellen. Wenn ATL die Löschung instanziiert, wird oder `CComTearOffObject<CYourTearOffClass>` `CComCachedTearOffObject<CYourTearOffClass>`erstellt.

Beispielsweise ist im BEEPER-Beispiel die- `CBeeper2` Klasse die abtrenn Klasse, und die `CBeeper` -Klasse ist die Besitzer Klasse:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="addref"></a>CcomTearOffObject:: adressf

Erhöht den Verweis Zähler des `CComTearOffObject` -Objekts um 1.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose und das Testen nützlich sein kann.

##  <a name="ccomtearoffobject"></a>CcomTearOffObject:: CcomTearOffObject

Der Konstruktor.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Parameter

*teuren*<br/>
in Ein Zeiger, der in einen Zeiger auf ein `CComObject<Owner>` -Objekt konvertiert wird.

### <a name="remarks"></a>Hinweise

Erhöht den Verweis Zähler des Besitzers um 1.

##  <a name="dtor"></a>CcomTearOffObject:: ~ CcomTearOffObject

Der Destruktor.

```
~CComTearOffObject();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei, ruft FinalRelease auf und Dekremente die Anzahl der Modul sperren.

##  <a name="ccomtearoffobjectbase"></a>CcomTearOffObject:: ccomtearoffobjectbase

Der Konstruktor.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Hinweise

Initialisiert den [m_pOwner](#m_powner) -Member mit NULL.

##  <a name="m_powner"></a>CcomTearOffObject:: m_pOwner

Ein Zeiger auf ein vom *Besitzer*abgeleitetes [CComObject](../../atl/reference/ccomobject-class.md) -Objekt.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Parameter

*Besitzer*<br/>
in Die Klasse, für die eine Löschung implementiert wird.

### <a name="remarks"></a>Hinweise

Der Zeiger wird während der Erstellung mit NULL initialisiert.

##  <a name="queryinterface"></a>CcomTearOffObject:: QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Die IID der angeforderten Schnittstelle.

*ppvObject*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch *IID*identifiziert wird, oder NULL, wenn die Schnittstelle nicht gefunden wurde.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Fragt zuerst nach Schnittstellen für Ihre abtrenn Klasse ab. Wenn die Schnittstelle nicht vorhanden ist, wird die-Schnittstelle für das Besitzer Objekt abgefragt. Wenn die angeforderte Schnitt `IUnknown`Stelle ist, `IUnknown` wird von der des Besitzers zurückgegeben.

##  <a name="release"></a>CcomTearOffObject:: Release

Dekremente den Verweis Zähler um 1 und, wenn der Verweis Zähler Null ist, den `CComTearOffObject`löscht.

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Rückgabewert

In nicht-Debugbuilds gibt immer 0 (null) zurück. In Debugbuilds gibt einen Wert zurück, der für die Diagnose oder das Testen nützlich sein kann.

## <a name="see-also"></a>Siehe auch

[CComCachedTearOffObject-Klasse](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
