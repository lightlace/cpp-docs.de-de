---
title: critical_section-Klasse
ms.date: 11/04/2016
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
ms.openlocfilehash: a08cb5049d742a9740361595bd931a2f7a48bd16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498763"
---
# <a name="criticalsection-class"></a>critical_section-Klasse

Ein nicht wieder eintretender Mutex, der explizit die Concurrency Runtime beachtet.

## <a name="syntax"></a>Syntax

```
class critical_section;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`native_handle_type`|Ein Verweis auf ein `critical_section`-Objekt.|

### <a name="public-classes"></a>Öffentliche Klassen

|Name|Beschreibung|
|----------|-----------------|
|[critical_section:: scoped_lock-Klasse](#critical_section__scoped_lock_class)|Ein sicher RAII-Wrapper für eine `critical_section` Objekt.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[critical_section](#ctor)|Erstellt einen neuen kritischen Abschnitt.|
|[~ Critical_section-Destruktor](#dtor)|Löscht einen kritischen Abschnitt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[lock](#lock)|Ruft dieser kritischen Abschnitt ab.|
|[native_handle](#native_handle)|Plattform bestimmte native gibt ein Handle zurück, falls vorhanden.|
|[try_lock](#try_lock)|Versucht, die Sperre abzurufen, ohne zu blockieren.|
|[try_lock_for](#try_lock_for)|Versucht, die Sperre zu übernehmen, ohne Blockierung für eine bestimmte Anzahl von Millisekunden.|
|[unlock](#unlock)|Entsperrt den kritischen Abschnitt.|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Synchronisierungsdatenstrukturen](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`critical_section`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> critical_section

Erstellt einen neuen kritischen Abschnitt.

```
critical_section();
```

##  <a name="dtor"></a> ~critical_section

Löscht einen kritischen Abschnitt.

```
~critical_section();
```

### <a name="remarks"></a>Hinweise

Es wird erwartet, dass die Sperre nicht mehr verwendet wird, wenn der Destruktor ausgeführt wird. Der kritische Abschnitt, mit dem Sperrtoken zerstört gespeichert wird, wird damit weiterhin Ergebnisse nicht definiertem Verhalten.

##  <a name="lock"></a> Sperre

Ruft dieser kritischen Abschnitt ab.

```
void lock();
```

### <a name="remarks"></a>Hinweise

Häufig ist es sicherer, zu verwenden die [Scoped_lock](#critical_section__scoped_lock_class) -Konstrukt zum Abrufen und Freigeben einer `critical_section` Objekt zu einer Ausnahme sichere Weise.

Wenn die Sperre bereits durch den aufrufenden Kontext, in Kraft ist ein [Improper_lock](improper-lock-class.md) Ausnahme ausgelöst.

##  <a name="native_handle"></a> native_handle

Plattform bestimmte native gibt ein Handle zurück, falls vorhanden.

```
native_handle_type native_handle();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf den kritischen Abschnitt.

### <a name="remarks"></a>Hinweise

Ein `critical_section` Objekt ist kein bestimmtes Plattform-native-Handle für das Windows-Betriebssystem zugeordnet. Die Methode gibt einfach einen Verweis auf das Objekt selbst.

##  <a name="critical_section__scoped_lock_class"></a>  critical_section:: scoped_lock-Klasse

Ein sicher RAII-Wrapper für eine `critical_section` Objekt.

```
class scoped_lock;
```

##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock

Erstellt eine `scoped_lock` Objekt, und ruft die `critical_section` Objekt übergeben, der `_Critical_section` Parameter. Wenn von einem anderen Thread der kritische Abschnitt gehalten wird, wird dieser Aufruf blockiert.

```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>Parameter

*_Critical_section*<br/>
Den kritischen Abschnitt, zu sperren.

##  <a name="critical_section__scoped_lock_dtor"></a> Scoped_lock:: ~ Scoped_lock

Zerstört eine `scoped_lock` Objekt und gibt die im Konstruktor bereitgestellte kritischen Abschnitt frei.

```
~scoped_lock();
```

##  <a name="try_lock"></a> try_lock

Versucht, die Sperre abzurufen, ohne zu blockieren.

```
bool try_lock();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Sperre abgerufen wurde, den Wert **"true"** ist, andernfalls der Wert **"false"**.

##  <a name="try_lock_for"></a> try_lock_for

Versucht, die Sperre zu übernehmen, ohne Blockierung für eine bestimmte Anzahl von Millisekunden.

```
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>Parameter

*_Timeout*<br/>
Die Anzahl der Millisekunden, bevor ein Timeout gewartet werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn die Sperre abgerufen wurde, den Wert **"true"** ist, andernfalls der Wert **"false"**.

##  <a name="unlock"></a> Entsperren

Entsperrt den kritischen Abschnitt.

```
void unlock();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[reader_writer_lock-Klasse](reader-writer-lock-class.md)
