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
ms.openlocfilehash: 66e7485787606c22aba2970dbe481a7d29e66621
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337361"
---
# <a name="schedulerworkercreationerror-class"></a>scheduler_worker_creation_error-Klasse

Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers bei der Erstellung eines Workerausführungskontexts in der Concurrency Runtime ausgelöst wird.

## <a name="syntax"></a>Syntax

```
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[scheduler_worker_creation_error](#ctor)|Überladen. Erstellt ein `scheduler_worker_creation_error`-Objekt.|

## <a name="remarks"></a>Hinweise

Diese Ausnahme wird in der Regel ausgelöst, wenn ein Aufruf an das Betriebssystem zum Erstellen der Ausführungskontexte aus in der Concurrency Runtime fehlschlägt. Ausführungskontexte sind Threads, die Aufgaben in der Concurrency Runtime ausführen. Der Fehlercode, die normalerweise von einem Aufruf der Win32-Methode zurückgegeben werden sollen `GetLastError` wird in einen Wert vom Typ konvertiert `HRESULT` und können abgerufen werden, mithilfe der Methode der Basisklasse `get_error_code`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)

`scheduler_worker_creation_error`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> scheduler_worker_creation_error

Erstellt ein `scheduler_worker_creation_error`-Objekt.

```
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
Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
