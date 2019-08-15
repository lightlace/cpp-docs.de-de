---
title: Ccomobjectnolock-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: 9253c7495f4d13ed6ce609988251d8abd09592ad
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497032"
---
# <a name="ccomobjectnolock-class"></a>Ccomobjectnolock-Klasse

Diese Klasse implementiert `IUnknown` für ein nicht aggregiertes Objekt, erhöht jedoch nicht die Anzahl der Modul Sperren im Konstruktor.

## <a name="syntax"></a>Syntax

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>Parameter

*Sock*<br/>
Die von [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)abgeleitete Klasse sowie von jeder anderen Schnittstelle, die Sie für das Objekt unterstützen möchten.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Konstruktor.|
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|Inkremente den Verweis Zähler für das Objekt.|
|[CComObjectNoLock::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die angeforderte Schnittstelle zurück.|
|[CComObjectNoLock::Release](#release)|Dekremente den Verweis Zähler für das Objekt.|

## <a name="remarks"></a>Hinweise

`CComObjectNoLock`ähnelt [CComObject](../../atl/reference/ccomobject-class.md) darin, dass [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) für ein nicht aggregiertes Objekt implementiert wird. `CComObjectNoLock` erhöht jedoch nicht die Anzahl der Modul Sperren im Konstruktor.

ATL verwendet `CComObjectNoLock` intern für Klassenfactorys. Im Allgemeinen verwenden Sie diese Klasse nicht direkt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="addref"></a>Ccomobjectnolock:: adressf

Inkremente den Verweis Zähler für das Objekt.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose oder das Testen nützlich sein kann.

##  <a name="ccomobjectnolock"></a>Ccomobjectnolock:: ccomobjectnolock

Der Konstruktor. Im Unterschied zu [CComObject](../../atl/reference/ccomobject-class.md)erhöht nicht die Anzahl der Modul sperren.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>Parameter

<em>void\*</em><br/>
in Dieser unbenannte Parameter wird nicht verwendet. Es ist für die Symmetrie mit `CComXXXObjectXXX` anderen Konstruktoren vorhanden.

##  <a name="dtor"></a>Ccomobjectnolock:: ~ ccomobjectnolock

Der Destruktor.

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei und ruft [FinalRelease](ccomobjectrootex-class.md#finalrelease)auf.

##  <a name="queryinterface"></a>Ccomobjectnolock:: QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Der Bezeichner der angeforderten Schnittstelle.

*ppvObject*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch *IID*identifiziert wird. Wenn das Objekt diese Schnittstelle nicht unterstützt, wird *ppvobject* auf NULL festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="release"></a>Ccomobjectnolock:: Release

Dekremente den Verweis Zähler für das Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In Debugbuilds `Release` gibt einen Wert zurück, der für die Diagnose oder das Testen nützlich sein kann. In nicht Debugbuilds `Release` gibt immer 0 zurück.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
