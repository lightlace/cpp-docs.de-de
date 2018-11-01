---
title: CComMultiThreadModel-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
ms.openlocfilehash: ae341763ef40125057b815d2071abbebdcf08f2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508900"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel-Klasse

`CComMultiThreadModel` Stellt Thread-sichere-Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen bereit.

## <a name="syntax"></a>Syntax

```
class CComMultiThreadModel
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|Verweist auf Klasse [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|
|[CComMultiThreadModel::CriticalSection](#criticalsection)|Verweist auf Klasse [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|Verweist auf Klasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComMultiThreadModel::Decrement](#decrement)|(Statisch) Dekrementiert den Wert der angegebenen Variablen auf threadsichere Weise.|
|[CComMultiThreadModel::Increment](#increment)|(Statisch) Inkrementiert den Wert der angegebenen Variablen auf threadsichere Weise.|

## <a name="remarks"></a>Hinweise

Normalerweise verwenden Sie `CComMultiThreadModel` über eine von zwei **Typedef** -Namen ist, wird entweder [CComObjectThreadModel] (Atl-typedefs.md #ccomobjectthreadmodel oder [CComGlobalsThreadModel] (Atl-typedefs.md #ccomglobalsthreadmodel. Die Klasse, die auf die verwiesen wird von den einzelnen **Typedef** , hängt das Threadingmodell verwendet, wie in der folgenden Tabelle dargestellt:

|Typedef|Single-threading|Apartmentthreading für Anwendungen|Freies threading|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

`CComMultiThreadModel` selbst definiert drei **Typedef** Namen. `AutoCriticalSection` und `CriticalSection` verweisen auf Klassen, Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts bereitstellen. `ThreadModelNoCS` Verweise-Klasse [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="autocriticalsection"></a>  CComMultiThreadModel::AutoCriticalSection

Bei Verwendung `CComMultiThreadModel`, **Typedef** Namen `AutoCriticalSection` verweist auf Klasse [CComAutoCriticalSection](ccomautocriticalsection-class.md), die stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts bereit. -Objekt.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Hinweise

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) und [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) enthalten auch die Definitionen für `AutoCriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `AutoCriticalSection`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Zusätzlich zu `AutoCriticalSection`, können Sie die **Typedef** Namen [CriticalSection](#criticalsection). Sie sollten keine angeben `AutoCriticalSection` in globaler Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernen möchten.

### <a name="example"></a>Beispiel

Der folgende Code wird nach dem Vorbild [CComObjectRootEx](ccomobjectrootex-class.md), und zeigt `AutoCriticalSection` in einer Umgebung mit threading verwendet wird.

```cpp
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```

In den folgenden Tabellen enthalten die Ergebnisse der `InternalAddRef` und `Lock` Methoden, die je nach der `ThreadModel` Template-Parameter und das Threadingmodell, die von der Anwendung verwendet:

### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel CComObjectThreadModel =

|Methode|Einzelne oder Apartmentthreading für Anwendungen|Freies Threading|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Die Schrittweite ist nicht threadsicher.|Das Inkrement ist threadsicher.|
|`Lock`|Hat keine Auswirkungen; Es gibt keine kritischen Abschnitt, zu sperren.|Der kritische Abschnitt gesperrt ist.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel CComObjectThreadModel::ThreadModelNoCS =

|Methode|Einzelne oder Apartmentthreading für Anwendungen|Freies Threading|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Die Schrittweite ist nicht threadsicher.|Das Inkrement ist threadsicher.|
|`Lock`|Hat keine Auswirkungen; Es gibt keine kritischen Abschnitt, zu sperren.|Hat keine Auswirkungen; Es gibt keine kritischen Abschnitt, zu sperren.|

##  <a name="criticalsection"></a>  CComMultiThreadModel::CriticalSection

Bei Verwendung `CComMultiThreadModel`, wird die **Typedef** Namen `CriticalSection` verweist auf Klasse [CComCriticalSection](ccomcriticalsection-class.md), die zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt stellt Methoden bereit.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Hinweise

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) und [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) enthalten auch die Definitionen für `CriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `CriticalSection`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Zusätzlich zu `CriticalSection`, können Sie die **Typedef** Namen [AutoCriticalSection](#autocriticalsection). Sie sollten keine angeben `AutoCriticalSection` in globaler Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernen möchten.

### <a name="example"></a>Beispiel

Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).

##  <a name="decrement"></a>  CComMultiThreadModel::Decrement

Diese statischen Funktion ruft die Win32-Funktion [InterlockedDecrement](/windows/desktop/api/winbase/nf-winbase-interlockeddecrement), welche dekrementiert der Wert der Variablen auf *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] Zeiger auf die zu verringernde Variable.

### <a name="return-value"></a>Rückgabewert

Wenn das Ergebnis dem Dekrementieren 0 (null), dann ist `Decrement` gibt 0 zurück. Wenn das Ergebnis dem Dekrementieren ungleich NULL ist, wird der Rückgabewert ebenfalls ungleich NULL ist, jedoch kann das Ergebnis dem verringern nicht gleich.

### <a name="remarks"></a>Hinweise

`InterlockedDecrement` verhindert, dass mehrere Threads gleichzeitig die Verwendung dieser Variablen.

##  <a name="increment"></a>  CComMultiThreadModel::Increment

Diese statischen Funktion ruft die Win32-Funktion [InterlockedIncrement](/windows/desktop/api/winbase/nf-winbase-interlockedincrement), die inkrementiert des Wert der Variable verweist *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] Zeiger auf die Variable inkrementiert werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn das Ergebnis des Inkrements 0 (null), dann ist `Increment` gibt 0 zurück. Wenn das Ergebnis des Inkrements ungleich NULL ist, wird der Rückgabewert ebenfalls ungleich NULL ist, jedoch das Ergebnis des Inkrements möglicherweise nicht gleich.

### <a name="remarks"></a>Hinweise

`InterlockedIncrement` verhindert, dass mehrere Threads gleichzeitig die Verwendung dieser Variablen.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModel::ThreadModelNoCS

Bei Verwendung `CComMultiThreadModel`, **Typedef** Namen `ThreadModelNoCS` verweist auf Klasse [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md).

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Hinweise

`CComMultiThreadModelNoCS` Stellt Thread-sichere-Methoden zum Inkrementieren und Dekrementieren eine Variable bereit; Es bietet jedoch kein kritischen Abschnitts.

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) und `CComMultiThreadModelNoCS` enthalten auch die Definitionen für `ThreadModelNoCS`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und die Klasse verweist, auf `ThreadModelNoCS`:

|Klasse definiert|Klasse, die auf die verwiesen wird|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Beispiel

Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).

## <a name="see-also"></a>Siehe auch

[CComSingleThreadModel-Klasse](ccomsinglethreadmodel-class.md)<br/>
[CComAutoCriticalSection-Klasse](ccomautocriticalsection-class.md)<br/>
[CComCriticalSection-Klasse](ccomcriticalsection-class.md)<br/>
[Übersicht über die Klasse](../atl-class-overview.md)
