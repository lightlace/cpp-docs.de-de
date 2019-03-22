---
title: CComMultiThreadModelNoCS-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
ms.openlocfilehash: ef2038a203b6cbfb2564bbe11d508ee43df0fd1b
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328661"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS-Klasse

`CComMultiThreadModelNoCS` Stellt Thread-sichere-Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen, ohne kritischen Abschnitt zu sperren oder Entsperren Funktionalität.

## <a name="syntax"></a>Syntax

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|name|Beschreibung|
|----------|-----------------|
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Verweist auf Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|Verweist auf Klasse `CComFakeCriticalSection`.|
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Verweist auf Klasse `CComMultiThreadModelNoCS`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Statisch) Dekrementiert den Wert der angegebenen Variablen auf threadsichere Weise.|
|[CComMultiThreadModelNoCS::Increment](#increment)|(Statisch) Inkrementiert den Wert der angegebenen Variablen auf threadsichere Weise.|

## <a name="remarks"></a>Hinweise

`CComMultiThreadModelNoCS` ist vergleichbar mit [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) insofern sie threadsichere Methoden zum Inkrementieren und Dekrementieren eine Variable enthält. Wenn Sie jedoch eine kritischen Abschnitt-Klasse über verweisen `CComMultiThreadModelNoCS`, Methoden, z. B. `Lock` und `Unlock` geschieht nichts.

Normalerweise verwenden Sie `CComMultiThreadModelNoCS` über die `ThreadModelNoCS` **Typedef** Name. Dies **Typedef** ist definiert `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).

> [!NOTE]
>  Die globale **Typedef** Namen [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) und [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) verweisen nicht `CComMultiThreadModelNoCS`.

Zusätzlich zu `ThreadModelNoCS`, `CComMultiThreadModelNoCS` definiert `AutoCriticalSection` und `CriticalSection`. Diese beiden letztgenannten **Typedef** Namen Verweis [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), die leere Methoden abrufen und Freigeben eines kritischen Abschnitts bereitstellt.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection

Bei Verwendung `CComMultiThreadModelNoCS`, **Typedef** Namen `AutoCriticalSection` verweist auf Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Hinweise

Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts, dessen Methoden keine Aktion durchführen.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch die Definitionen für `AutoCriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `AutoCriticalSection`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Zusätzlich zu `AutoCriticalSection`, können Sie die **Typedef** Namen [CriticalSection](#criticalsection). Sie sollten keine angeben `AutoCriticalSection` in globaler Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernen möchten.

### <a name="example"></a>Beispiel

Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection

Bei Verwendung `CComMultiThreadModelNoCS`, **Typedef** Namen `CriticalSection` verweist auf Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Hinweise

Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts, dessen Methoden keine Aktion durchführen.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch die Definitionen für `CriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `CriticalSection`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Zusätzlich zu `CriticalSection`, können Sie die **Typedef** Namen `AutoCriticalSection`. Sie sollten keine angeben `AutoCriticalSection` in globaler Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernen möchten.

### <a name="example"></a>Beispiel

Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement

Diese statischen Funktion ruft die Win32-Funktion [InterlockedDecrement](/windows/desktop/api/winnt/nf-winnt-interlockeddecrement), welche dekrementiert der Wert der Variablen auf *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] Zeiger auf die zu verringernde Variable.

### <a name="return-value"></a>Rückgabewert

Wenn das Ergebnis dem Dekrementieren 0 (null), dann ist `Decrement` gibt 0 zurück. Wenn das Ergebnis dem Dekrementieren ungleich NULL ist, wird der Rückgabewert ebenfalls ungleich NULL ist, jedoch kann das Ergebnis dem verringern nicht gleich.

### <a name="remarks"></a>Hinweise

**InterlockedDecrement** verhindert, dass mehrere Threads gleichzeitig verwenden diese Variable.

##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment

Diese statischen Funktion ruft die Win32-Funktion [InterlockedIncrement](/windows/desktop/api/winnt/nf-winnt-interlockedincrement), die inkrementiert des Wert der Variable verweist *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] Zeiger auf die Variable inkrementiert werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn das Ergebnis des Inkrements 0 (null), dann ist **Inkrement** gibt 0 zurück. Wenn das Ergebnis des Inkrements ungleich NULL ist, wird der Rückgabewert ebenfalls ungleich NULL ist, jedoch das Ergebnis des Inkrements möglicherweise nicht gleich.

### <a name="remarks"></a>Hinweise

**InterlockedIncrement** verhindert, dass mehrere Threads gleichzeitig verwenden diese Variable.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS

Bei Verwendung `CComMultiThreadModelNoCS`, **Typedef** Namen `ThreadModelNoCS` verweist einfach auf `CComMultiThreadModelNoCS`.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Hinweise

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch die Definitionen für `ThreadModelNoCS`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und die Klasse verweist, auf `ThreadModelNoCS`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

Beachten Sie, dass die Definition der `ThreadModelNoCS` in `CComMultiThreadModelNoCS` bietet die Symmetrie mit `CComMultiThreadModel` und `CComSingleThreadModel`. Nehmen wir beispielsweise an der Beispielcode im `CComMultiThreadModel::AutoCriticalSection` deklariert die folgenden **Typedef**:

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

Unabhängig davon, für die angegebene Klasse `ThreadModel` (z. B. `CComMultiThreadModelNoCS`), `_ThreadModel` löst entsprechend.

### <a name="example"></a>Beispiel

Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
