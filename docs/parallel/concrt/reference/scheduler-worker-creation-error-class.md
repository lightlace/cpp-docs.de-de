---
title: scheduler_worker_creation_error-Klasse
ms.date: 11/04/2016
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
ms.openlocfilehash: e7f2763d7244be9e5e5b006b31b97c08e213a4f2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142765"
---
# <a name="scheduler_worker_creation_error-class"></a>scheduler_worker_creation_error-Klasse

Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers bei der Erstellung eines Workerausführungskontexts in der Concurrency Runtime ausgelöst wird.

## <a name="syntax"></a>Syntax

```cpp
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[scheduler_worker_creation_error](#ctor)|Ist überladen. Erstellt ein `scheduler_worker_creation_error`-Objekt.|

## <a name="remarks"></a>Bemerkungen

Diese Ausnahme wird normalerweise ausgelöst, wenn ein Systemaufrufe zum Erstellen von Ausführungs Kontexten innerhalb des Concurrency Runtime fehlschlägt. Ausführungs Kontexte sind Threads, die Tasks im Concurrency Runtime ausführen. Der Fehlercode, der normalerweise von einem aufgerufenen Win32-Methode zurückgegeben wird `GetLastError` wird in einen Wert vom Typ "`HRESULT`" konvertiert und kann mit der `get_error_code`der Basisklassen Methode abgerufen werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)

`scheduler_worker_creation_error`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>scheduler_worker_creation_error

Erstellt ein `scheduler_worker_creation_error`-Objekt.

```cpp
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

*_Hresult*<br/>
Der `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
