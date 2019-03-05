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
ms.openlocfilehash: 7f7254306253aabc33f46694f3da16734e6efccf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276493"
---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error-Klasse

Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers ausgelöst wird, um in der Concurrency Runtime eine wichtige Ressource abzurufen.

## <a name="syntax"></a>Syntax

```
class scheduler_resource_allocation_error : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[scheduler_resource_allocation_error](#ctor)|Überladen. Erstellt ein `scheduler_resource_allocation_error`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[get_error_code](#get_error_code)|Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.|

## <a name="remarks"></a>Hinweise

Diese Ausnahme wird in der Regel ausgelöst, wenn ein Aufruf an das Betriebssystem aus, in der Concurrency Runtime fehlschlägt. Der Fehlercode, die normalerweise von einem Aufruf der Win32-Methode zurückgegeben werden würde `GetLastError` wird in einen Wert vom Typ konvertiert `HRESULT` und können abgerufen werden, mithilfe der `get_error_code` Methode.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`scheduler_resource_allocation_error`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="get_error_code"></a> get_error_code

Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.

```
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.

##  <a name="ctor"></a> scheduler_resource_allocation_error

Erstellt ein `scheduler_resource_allocation_error`-Objekt.

```
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
Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
