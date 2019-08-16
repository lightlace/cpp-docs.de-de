---
title: Ccommultithreadmodelnocs-Klasse
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
ms.openlocfilehash: 01c7f953b6b8916394ee4c2b5b27cf84af52b920
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497088"
---
# <a name="ccommultithreadmodelnocs-class"></a>Ccommultithreadmodelnocs-Klasse

`CComMultiThreadModelNoCS`stellt Thread sichere Methoden zum Inkrementieren und Dekrementieren des Werts einer Variablen bereit, ohne dass eine kritische Abschnitts Sperr-oder entsperrungs Funktionalität besteht.

## <a name="syntax"></a>Syntax

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Verweist auf die Klasse [ccomfakecriticalsection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|References- `CComFakeCriticalSection`Klasse.|
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|References- `CComMultiThreadModelNoCS`Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComMultiThreadModelNoCS::Decrement](#decrement)|Kum Dekremente den Wert der angegebenen Variablen auf Thread sichere Weise.|
|[CComMultiThreadModelNoCS::Increment](#increment)|Kum Erhöht den Wert der angegebenen Variablen auf Thread sichere Weise.|

## <a name="remarks"></a>Hinweise

`CComMultiThreadModelNoCS`ähnelt [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) , da es Thread sichere Methoden zum Inkrementieren und Dekrementieren einer Variablen bereitstellt. Wenn Sie jedoch auf eine kritische Abschnitts Klasse durch `CComMultiThreadModelNoCS`verweisen, werden Methoden `Lock` wie und `Unlock` keine Aktion ausführen.

In der Regel verwenden `CComMultiThreadModelNoCS` Sie den `ThreadModelNoCS` **typedef** -Namen. Diese **typedef** ist in `CComMultiThreadModelNoCS`, `CComMultiThreadModel`und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)definiert.

> [!NOTE]
>  Die globalen **typedef** -Namen " [ccomobjectthreadmodel](atl-typedefs.md#ccomobjectthreadmodel) " und " [ccomglobalsthlock Model](atl-typedefs.md#ccomglobalsthreadmodel) " verweisen `CComMultiThreadModelNoCS`nicht.

`ThreadModelNoCS`Zusätzlich zu `CComMultiThreadModelNoCS` definiert und`AutoCriticalSection` . `CriticalSection` Diese beiden folgenden **typedef** -Namen verweisen auf [ccomfakecriticalsection](../../atl/reference/ccomfakecriticalsection-class.md), das leere Methoden bereitstellt, die mit dem Abrufen und Freigeben eines kritischen Abschnitts verknüpft sind.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase. h

##  <a name="autocriticalsection"></a>Ccommultithreadmodelnocs:: autocriticalsection

Bei Verwendung `CComMultiThreadModelNoCS`von verweist der **typedef** -Name `AutoCriticalSection` auf die Klasse [ccomfakecriticalsection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Hinweise

Da `CComFakeCriticalSection` keinen kritischen Abschnitt bereitstellt, machen seine Methoden nichts.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch Definitionen für `AutoCriticalSection`. In der folgenden Tabelle wird die Beziehung zwischen der Threading Modell Klasse und der Critical-Abschnitts Klasse `AutoCriticalSection`gezeigt, auf die von verwiesen wird:

|In definierte Klasse|Referenzierte Klasse|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Zusätzlich zu `AutoCriticalSection`können Sie den **typedef** -Namen [CriticalSection](#criticalsection)verwenden. Sie sollten nicht in `AutoCriticalSection` globalen Objekten oder statischen Klassenmembern angeben, wenn Sie den CRT-Startcode entfernen möchten.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie unter [CComMultiThreadModel:: autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>Ccommultithreadmodelnocs:: CriticalSection

Bei Verwendung `CComMultiThreadModelNoCS`von verweist der **typedef** -Name `CriticalSection` auf die Klasse [ccomfakecriticalsection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Hinweise

Da `CComFakeCriticalSection` keinen kritischen Abschnitt bereitstellt, machen seine Methoden nichts.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch Definitionen für `CriticalSection`. In der folgenden Tabelle wird die Beziehung zwischen der Threading Modell Klasse und der Critical-Abschnitts Klasse `CriticalSection`gezeigt, auf die von verwiesen wird:

|In definierte Klasse|Referenzierte Klasse|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Zusätzlich zu `CriticalSection`können Sie den **typedef** -Namen `AutoCriticalSection`verwenden. Sie sollten nicht in `AutoCriticalSection` globalen Objekten oder statischen Klassenmembern angeben, wenn Sie den CRT-Startcode entfernen möchten.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie unter [CComMultiThreadModel:: autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>Ccommultithreadmodelnocs::D ecrement

Diese statische Funktion Ruft die Win32-Funktion " [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)" auf, die den Wert der Variablen Dekremente, auf die *p*zeigt.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
in Ein Zeiger auf die Variable, die dekrementiert werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn das Ergebnis des dekrements 0 ist, `Decrement` wird 0 zurückgegeben. Wenn das Ergebnis des dekrements ungleich 0 (null) ist, ist der Rückgabewert auch ungleich 0 (null), ist aber möglicherweise nicht mit dem Ergebnis des dekrements identisch.

### <a name="remarks"></a>Hinweise

Mit **InterlockedDecrement** wird verhindert, dass mehr als ein Thread gleichzeitig diese Variable verwendet.

##  <a name="increment"></a>Ccommultithreadmodelnocs:: Increment

Diese statische Funktion Ruft die Win32-Funktion [interlockedinkrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)auf, mit der der Wert der Variablen erhöht wird, auf die von *p*verwiesen wird.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
in Ein Zeiger auf die Variable, die inkrementiert werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn das Ergebnis des Inkrements 0 ist, gibt **Inkrement** 0 zurück. Wenn das Ergebnis des Inkrements ungleich 0 (null) ist, ist der Rückgabewert auch ungleich 0 (null), kann aber nicht dem Ergebnis des Inkrements entsprechen.

### <a name="remarks"></a>Hinweise

Mit **interlockedinkrement** wird verhindert, dass mehr als ein Thread gleichzeitig diese Variable verwendet.

##  <a name="threadmodelnocs"></a>Ccommultithreadmodelnocs:: threadmodelnocs

Bei Verwendung `CComMultiThreadModelNoCS`von `ThreadModelNoCS` verweist derTypedef-Nameeinfach`CComMultiThreadModelNoCS`auf.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Hinweise

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch Definitionen für `ThreadModelNoCS`. In der folgenden Tabelle wird die Beziehung zwischen der Thread Modell Klasse und der-Klasse, `ThreadModelNoCS`auf die von verwiesen wird, gezeigt:

|In definierte Klasse|Referenzierte Klasse|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

Beachten Sie, dass die `ThreadModelNoCS` Definition `CComMultiThreadModelNoCS` von in die `CComMultiThreadModel` Symmetrie `CComSingleThreadModel`mit und bereitstellt. Angenommen, der Beispielcode in `CComMultiThreadModel::AutoCriticalSection` hat die folgende **typedef**deklariert:

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

Unabhängig von der Klasse, die `ThreadModel` für angegeben wurde `CComMultiThreadModelNoCS`(z `_ThreadModel` . b.), wird entsprechend aufgelöst.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie unter [CComMultiThreadModel:: autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
