---
title: CComPtr-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 5e3e510291daa50ddcf5d63451edef0428d66ed1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280464"
---
# <a name="ccomptr-class"></a>CComPtr-Klasse

Eine intelligente Zeiger-Klasse für die Verwaltung von COM-Schnittstellenzeiger.

## <a name="syntax"></a>Syntax

```
template<class T>
class CComPtr
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Eine COM-Schnittstelle, die den Typ des Zeigers gespeichert werden.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComPtr::CComPtr](#ccomptr)|Der Konstruktor.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComPtr::operator =](#operator_eq)|Weist einen Zeiger auf den Member-Zeiger.|

## <a name="remarks"></a>Hinweise

ATL verwendet `CComPtr` und [CComQIPtr](../../atl/reference/ccomqiptr-class.md) zum Verwalten von COM-Schnittstellenzeiger. Beide basieren auf [CComPtrBase](../../atl/reference/ccomptrbase-class.md), und führen Sie sowohl automatische verweiszählung.

Die `CComPtr` und [CComQIPtr](../../atl/reference/ccomqiptr-class.md) Klassen können helfen, Speicherverluste zu vermeiden, indem Sie Ausführung automatische verweiszählung.  Die folgenden Funktionen ausführen, die gleichen logischen Vorgängen; Beachten Sie jedoch, wie die zweite Version weniger fehleranfällige mit möglicherweise die `CComPtr` Klasse:

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

Verknüpfen Sie in Debugbuilds atlsd.lib für die codeablaufverfolgung ein.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="ccomptr"></a>  CComPtr::CComPtr

Der Konstruktor.

```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>Parameter

*lp*<br/>
Wird verwendet, um den Schnittstellenzeiger zu initialisieren.

*T*<br/>
Eine COM-Schnittstelle.

##  <a name="operator_eq"></a>  CComPtr::operator =

Zuweisungsoperator.

```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die aktualisierte `CComPtr` Objekt

### <a name="remarks"></a>Hinweise

Dieser Vorgang AddRefs das neue Objekt und Versionen, die im vorhandene Objekt, wenn eine vorhanden ist.

## <a name="see-also"></a>Siehe auch

[CComPtr::CComPtr](#ccomptr)<br/>
[CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
