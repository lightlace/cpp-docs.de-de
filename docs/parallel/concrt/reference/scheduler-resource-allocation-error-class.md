---
title: scheduler_resource_allocation_error-Klasse
ms.date: 11/04/2016
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
ms.openlocfilehash: 2955320b443fb61f26d9f07ca336a45c620e2aa9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143336"
---
# <a name="scheduler_resource_allocation_error-class"></a>scheduler_resource_allocation_error-Klasse

Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers ausgelöst wird, um in der Concurrency Runtime eine wichtige Ressource abzurufen.

## <a name="syntax"></a>Syntax

```cpp
class scheduler_resource_allocation_error : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[scheduler_resource_allocation_error](#ctor)|Ist überladen. Erstellt ein `scheduler_resource_allocation_error`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[get_error_code](#get_error_code)|Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.|

## <a name="remarks"></a>Bemerkungen

Diese Ausnahme wird normalerweise ausgelöst, wenn ein Systemaufrufe innerhalb des Concurrency Runtime fehlschlägt. Der Fehlercode, der normalerweise von einem aufgerufenen Win32-Methode zurückgegeben wird `GetLastError` wird in einen Wert vom Typ "`HRESULT`" konvertiert und kann mit der `get_error_code`-Methode abgerufen werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`scheduler_resource_allocation_error`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="get_error_code"></a>get_error_code

Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.

## <a name="ctor"></a>scheduler_resource_allocation_error

Erstellt ein `scheduler_resource_allocation_error`-Objekt.

```cpp
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

*_Hresult*<br/>
Der `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
