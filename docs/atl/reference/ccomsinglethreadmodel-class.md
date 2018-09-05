---
title: CComSingleThreadModel-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 0a29e7da1c4f1662d7342a507bed786fcbf82bc4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765045"
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel-Klasse

Diese Klasse stellt Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen zu.

## <a name="syntax"></a>Syntax

```
class CComSingleThreadModel
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|Verweist auf Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComSingleThreadModel::CriticalSection](#criticalsection)|Verweist auf Klasse `CComFakeCriticalSection`.|
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Verweise `CComSingleThreadModel`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComSingleThreadModel::Decrement](#decrement)|Dekrementiert den Wert der angegebenen Variablen. Diese Implementierung ist nicht threadsicher.|
|[CComSingleThreadModel::Increment](#increment)|Erhöht den Wert der angegebenen Variablen. Diese Implementierung ist nicht threadsicher.|

## <a name="remarks"></a>Hinweise

`CComSingleThreadModel` Stellt Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen bereit. Im Gegensatz zu [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), diese Methoden sind nicht threadsicher.  

Normalerweise verwenden Sie `CComSingleThreadModel` über eine von zwei **Typedef** -Namen ist, wird entweder [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) oder [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Die Klasse, die auf die verwiesen wird von den einzelnen **Typedef** , hängt das Threadingmodell verwendet, wie in der folgenden Tabelle dargestellt:  

|Typedef|Einzelne threading-Modell|Threading Apartment-Modell|Kostenlose threading-Modell|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

`CComSingleThreadModel` selbst definiert drei **Typedef** Namen. `ThreadModelNoCS` Verweise `CComSingleThreadModel`. `AutoCriticalSection` und `CriticalSection` reference-Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), die leere Methoden abrufen und Freigeben des Besitzes eines kritischen Abschnitts bereitstellt.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="autocriticalsection"></a>  CComSingleThreadModel::AutoCriticalSection

Bei Verwendung `CComSingleThreadModel`, **Typedef** Namen `AutoCriticalSection` verweist auf Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Hinweise

Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts, dessen Methoden keine Aktion durchführen.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `AutoCriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `AutoCriticalSection`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Zusätzlich zu `AutoCriticalSection`, können Sie die **Typedef** Namen [CriticalSection](#criticalsection). Sie sollten keine angeben `AutoCriticalSection` in globaler Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernen möchten.

### <a name="example"></a>Beispiel

Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>  CComSingleThreadModel::CriticalSection

Bei Verwendung `CComSingleThreadModel`, **Typedef** Namen `CriticalSection` verweist auf Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Hinweise

Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts, dessen Methoden keine Aktion durchführen.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `CriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `CriticalSection`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Zusätzlich zu `CriticalSection`, können Sie die **Typedef** Namen [AutoCriticalSection](#autocriticalsection). Sie sollten keine angeben `AutoCriticalSection` in globaler Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernen möchten.

### <a name="example"></a>Beispiel

Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>  CComSingleThreadModel::Decrement

Diese statische Funktion dekrementiert der Wert der Variable verweist *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parameter

*p*  
[in] Zeiger auf die zu verringernde Variable.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis dem verringern.

##  <a name="increment"></a>  CComSingleThreadModel::Increment

Diese statische Funktion dekrementiert der Wert der Variable verweist *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parameter

*p*  
[in] Zeiger auf die Variable inkrementiert werden soll.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des Inkrements.

##  <a name="threadmodelnocs"></a>  CComSingleThreadModel::ThreadModelNoCS

Bei Verwendung `CComSingleThreadModel`, **Typedef** Namen `ThreadModelNoCS` verweist einfach auf `CComSingleThreadModel`.

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>Hinweise

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `ThreadModelNoCS`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und die Klasse verweist, auf `ThreadModelNoCS`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Beispiel

Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
