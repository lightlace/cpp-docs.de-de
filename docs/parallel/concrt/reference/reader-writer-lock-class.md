---
title: reader_writer_lock-Klasse
ms.date: 11/04/2016
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
ms.openlocfilehash: 111d48b9c4a575078f2342bfaa944871bbd628f5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268654"
---
# <a name="readerwriterlock-class"></a>reader_writer_lock-Klasse

Eine im Writer festgelegte, warteschlangenbasierte Lese-/Schreibsperre mit ausschließlich lokalem Spinning. Die Sperre gewährt "First In, First Out"-Zugriff (FIFO-Zugriff) auf Writer und blockiert Reader unter einer fortlaufenden Last von Writern.

## <a name="syntax"></a>Syntax

```
class reader_writer_lock;
```

## <a name="members"></a>Member

### <a name="public-classes"></a>Öffentliche Klassen

|Name|Beschreibung|
|----------|-----------------|
|[reader_writer_lock:: scoped_lock-Klasse](#scoped_lock_class)|Eine sichere RAII-Wrapper, die verwendet werden kann, zum Abrufen `reader_writer_lock` Sperren von Objekten als Autor.|
|[reader_writer_lock:: scoped_lock_read-Klasse](#scoped_lock_read_class)|Eine sichere RAII-Wrapper, die verwendet werden kann, zum Abrufen `reader_writer_lock` Sperren von Objekten als Reader.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[reader_writer_lock](#ctor)|Erstellt ein neues `reader_writer_lock`-Objekt.|
|[~reader_writer_lock Destructor](#dtor)|Zerstört das `reader_writer_lock`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[lock](#lock)|Ruft den Lese-/ Schreibsperre als Autor ab.|
|[lock_read](#lock_read)|Ruft den Lese-/ Schreibsperre als Reader ab. Wenn Writer, müssen aktive Reader warten, bis sie fertig sind. Der Reader wird einfach registriert Interesse an der die Sperre und wartet, bis Writer sie freigeben.|
|[try_lock](#try_lock)|Versucht, die Lese-/ Schreibsperre als Writer ohne Blockierung zu erhalten.|
|[try_lock_read](#try_lock_read)|Versucht, die Lese-/ Schreibsperre als Reader ohne Blockierung zu erhalten.|
|[unlock](#unlock)|Entsperrt den Lese-/ Schreibsperre, die basierend auf, die, Reader oder Writer gesperrt.|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Synchronisierungsdatenstrukturen](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`reader_writer_lock`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="lock"></a> Sperre

Ruft den Lese-/ Schreibsperre als Autor ab.

```
void lock();
```

### <a name="remarks"></a>Hinweise

Häufig ist es sicherer, zu verwenden die [Scoped_lock](#scoped_lock_class) -Konstrukt zum Abrufen und Freigeben einer `reader_writer_lock` Objekt als Autor einer Ausnahme sichere Weise.

Nachdem ein Writer versucht, die Sperre abzurufen, blockiert alle zukünftigen Reader, bis die Writer wurde erfolgreich abgerufen und die Sperre aufgehoben haben. Diese Sperre ist unvoreingenommen gegenüber Writer und Leser unter einer fortlaufenden Last von Writern blockieren, kann.

Autoren werden verkettet, sodass ein Writer, der das Beenden der Sperre auf den nächsten Writer in Zeile frei.

Wenn die Sperre bereits durch den aufrufenden Kontext, in Kraft ist ein [Improper_lock](improper-lock-class.md) Ausnahme ausgelöst.

##  <a name="lock_read"></a> lock_read

Ruft den Lese-/ Schreibsperre als Reader ab. Wenn Writer, müssen aktive Reader warten, bis sie fertig sind. Der Reader wird einfach registriert Interesse an der die Sperre und wartet, bis Writer sie freigeben.

```
void lock_read();
```

### <a name="remarks"></a>Hinweise

Häufig ist es sicherer, zu verwenden die [Scoped_lock_read](#scoped_lock_read_class) -Konstrukt zum Abrufen und Freigeben einer `reader_writer_lock` Objekts als ein Leser eine Ausnahme sichere Weise.

Wenn Writer auf die Sperre warten, wird der Reader warten, bis alle Schreiber in Zeile abgerufen und die Sperre aufgehoben haben. Diese Sperre ist unvoreingenommen gegenüber Writer und Leser unter einer fortlaufenden Last von Writern blockieren, kann.

##  <a name="ctor"></a> reader_writer_lock

Erstellt ein neues `reader_writer_lock`-Objekt.

```
reader_writer_lock();
```

##  <a name="dtor"></a> ~reader_writer_lock

Zerstört das `reader_writer_lock`-Objekt.

```
~reader_writer_lock();
```

### <a name="remarks"></a>Hinweise

Es wird erwartet, dass die Sperre nicht mehr verwendet wird, wenn der Destruktor ausgeführt wird. Ermöglicht der Writer eine Schreibsperre um mit dem Sperrtoken zerstört gespeichert noch Ergebnisse nicht definiertem Verhalten.

##  <a name="scoped_lock_class"></a>  reader_writer_lock:: scoped_lock-Klasse

Eine sichere RAII-Wrapper, die verwendet werden kann, zum Abrufen `reader_writer_lock` Sperren von Objekten als Autor.

```
class scoped_lock;
```

## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock

Erstellt eine `scoped_lock` Objekt, und ruft die `reader_writer_lock` Objekt übergeben, der `_Reader_writer_lock` Parameter als einen Writer. Wenn von einem anderen Thread die Sperre gehalten wird, wird dieser Aufruf blockiert.

```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

#### <a name="parameters"></a>Parameter

*_Reader_writer_lock*<br/>
Die `reader_writer_lock` Objekt, das als Autor abgerufen.

## <a name="scoped_lock_dtor"></a> scoped_lock::~scoped_lock

Zerstört eine `reader_writer_lock` Objekt aus, und hebt die Sperre, die in seinem Konstruktor angegeben.

```
~scoped_lock();
```

##  <a name="scoped_lock_read_class"></a>  reader_writer_lock:: scoped_lock_read-Klasse

Eine sichere RAII-Wrapper, die verwendet werden kann, zum Abrufen `reader_writer_lock` Sperren von Objekten als Reader.

```
class scoped_lock_read;
```

##  <a name="try_lock"></a> try_lock

Versucht, die Lese-/ Schreibsperre als Writer ohne Blockierung zu erhalten.

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read

Erstellt eine `scoped_lock_read` Objekt, und ruft die `reader_writer_lock` Objekt übergeben, der `_Reader_writer_lock` Parameter als Reader. Wenn die Sperre wird von einem anderen Thread als Autor oder Autoren stehen, wird dieser Aufruf blockiert.

```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

#### <a name="parameters"></a>Parameter

*_Reader_writer_lock*<br/>
Die `reader_writer_lock` Objekt, das als Reader abgerufen.

## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock:: scoped_lock_read:: ~ Scoped_lock_read-Destruktor

Zerstört eine `scoped_lock_read` Objekt aus, und hebt die Sperre, die in seinem Konstruktor angegeben.

```
~scoped_lock_read();
```

## <a name="try_lock"></a> try_lock

```
bool try_lock();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Sperre abgerufen wurde, den Wert **"true"** ist, andernfalls der Wert **"false"**.

##  <a name="try_lock_read"></a> try_lock_read

Versucht, die Lese-/ Schreibsperre als Reader ohne Blockierung zu erhalten.

```
bool try_lock_read();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Sperre abgerufen wurde, den Wert **"true"** ist, andernfalls der Wert **"false"**.

##  <a name="unlock"></a> Entsperren

Entsperrt den Lese-/ Schreibsperre, die basierend auf, die, Reader oder Writer gesperrt.

```
void unlock();
```

### <a name="remarks"></a>Hinweise

Wenn Writer auf die Sperre warten, geht die Aufhebung der Sperre immer in den nächsten Writer in FIFO-Reihenfolge. Diese Sperre ist unvoreingenommen gegenüber Writer und Leser unter einer fortlaufenden Last von Writern blockieren, kann.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[critical_section-Klasse](critical-section-class.md)
