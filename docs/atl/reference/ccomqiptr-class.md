---
title: CComQIPtr-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: c231d4d83a3030ea63e781e6f3d185270a483ccc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624925"
---
# <a name="ccomqiptr-class"></a>CComQIPtr-Klasse

Eine intelligente Zeiger-Klasse für die Verwaltung von COM-Schnittstellenzeiger.

## <a name="syntax"></a>Syntax

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Eine COM-Schnittstelle, die den Typ des Zeigers gespeichert werden.

*piid*<br/>
Ein Zeiger auf die IID der *T*.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComQIPtr::CComQIPtr](#ccomqiptr)|Konstruktor.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComQIPtr::operator =](#operator_eq)|Weist einen Zeiger auf den Member-Zeiger.|

## <a name="remarks"></a>Hinweise

ATL verwendet `CComQIPtr` und [CComPtr](../../atl/reference/ccomptr-class.md) zum Verwalten von COM-Schnittstellenzeiger auf beide abgeleitet [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Beide Klassen führen Sie automatische verweiszählung, die durch Aufrufe von `AddRef` und `Release`. Überladene Operatoren Zeigeroperationen zu behandeln.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[CComPtr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>Anforderungen

**Header:** "atlcomcli.h"

##  <a name="ccomqiptr"></a>  CComQIPtr::CComQIPtr

Der Konstruktor.

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>Parameter

*LP*<br/>
Wird verwendet, um den Schnittstellenzeiger zu initialisieren.

*T*<br/>
Eine COM-Schnittstelle.

*piid*<br/>
Ein Zeiger auf die IID der *T*.

##  <a name="operator_eq"></a>  CComQIPtr::operator =

Der Zuweisungsoperator.

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>Parameter

*LP*<br/>
Wird verwendet, um den Schnittstellenzeiger zu initialisieren.

*T*<br/>
Eine COM-Schnittstelle.

*piid*<br/>
Ein Zeiger auf die IID der *T*.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die aktualisierte `CComQIPtr` Objekt.

## <a name="see-also"></a>Siehe auch

[CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr::CComQIPtr](#ccomqiptr)<br/>
[CComPtrBase-Klasse](../../atl/reference/ccomptrbase-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)
