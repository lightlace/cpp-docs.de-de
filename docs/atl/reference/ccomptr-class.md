---
title: CComPtr-Klasse
description: Referenzhandbuch für die Microsoft C++ Active Template Library (ATL)-Klasse "CComPtr".
ms.date: 02/07/2020
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 74a12b460f55a782fa2747b02f7d00287786fae6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127404"
---
# <a name="ccomptr-class"></a>CComPtr-Klasse

Eine intelligente Zeiger Klasse zum Verwalten von COM-Schnittstellen Zeigern.

## <a name="syntax"></a>Syntax

```cpp
template<class T>
class CComPtr
```

### <a name="parameters"></a>Parameter

*T*<br/>
Eine COM-Schnittstelle, die den Typ des zu speichernden Zeigers angibt.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[CComPtr:: CComPtr](#ccomptr)|Der Konstruktor.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[CComPtr:: Operator =](#operator_eq)|Weist einen Zeiger auf den Member-Zeiger zu.|

## <a name="remarks"></a>Bemerkungen

ATL verwendet `CComPtr` und [CComQIPtr](../../atl/reference/ccomqiptr-class.md) zum Verwalten von COM-Schnittstellen Zeigern. Beide werden von [CComPtrBase](../../atl/reference/ccomptrbase-class.md)abgeleitet, und beide führen eine automatische Verweis Zählung aus.

Die Klassen `CComPtr` und [CComQIPtr](../../atl/reference/ccomqiptr-class.md) können dabei helfen, Speicher Verluste durch die automatische Verweis Zählung zu vermeiden.  Die folgenden Funktionen führen beide dieselben logischen Vorgänge aus. Die zweite Version kann jedoch weniger fehleranfällig sein, da Sie die `CComPtr`-Klasse verwendet:

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

Verknüpfen Sie atlsd. lib in Debugbuilds mit der Code Ablauf Verfolgung.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** atlbase. h

## <a name="ccomptr"></a>CComPtr:: CComPtr

Der Konstruktor.

```cpp
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>Parameter

*LP*<br/>
Wird verwendet, um den Schnittstellen Zeiger zu initialisieren.

*T*<br/>
Eine COM-Schnittstelle.

### <a name="remarks"></a>Bemerkungen

Die Konstruktoren, die einen Argument Aufrufe übernehmen, `AddRef` auf *LP*, wenn es kein NULL-Zeiger ist. Ein Objekt, das nicht NULL ist, erhält einen `Release` aufzurufenden CComPtr-Objekts oder, wenn dem CComPtr-Objekt ein neues Objekt zugewiesen wird.

## <a name="operator_eq"></a>CComPtr:: Operator =

Zuweisungsoperator.

```cpp
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf das aktualisierte `CComPtr` Objekt zurück.

### <a name="remarks"></a>Bemerkungen

Dieser Vorgang adressiert das neue-Objekt und gibt ggf. das vorhandene-Objekt frei.

## <a name="see-also"></a>Weitere Informationen

[CComPtr:: CComPtr](#ccomptr)<br/>
[CComQIPtr:: CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
