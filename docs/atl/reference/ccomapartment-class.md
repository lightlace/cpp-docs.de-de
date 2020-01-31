---
title: Ccomapartment-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: 5f4c7fc356e61210e9b99bf9989b1bb3f0abc98a
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821674"
---
# <a name="ccomapartment-class"></a>Ccomapartment-Klasse

Diese Klasse bietet Unterstützung für die Verwaltung eines Apartment in einem Modul mit einem Thread im Pool.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CComApartment
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|-Name|Beschreibung|
|----------|-----------------|
|[CComApartment::CComApartment](#ccomapartment)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|-Name|Beschreibung|
|----------|-----------------|
|[CComApartment::Apartment](#apartment)|Markiert die Anfangsadresse des Threads.|
|[CComApartment::GetLockCount](#getlockcount)|Gibt die aktuelle Sperrenanzahl des Threads zurück.|
|[CComApartment::Lock](#lock)|Erhöht die Sperrenanzahl des Threads.|
|[CComApartment::Unlock](#unlock)|Verringert die Sperrenanzahl des Threads.|

### <a name="public-data-members"></a>Öffentliche Datenelemente

|-Name|Beschreibung|
|----------|-----------------|
|[CComApartment::m_dwThreadID](#m_dwthreadid)|Enthält den Bezeichner des Threads.|
|[CComApartment::m_hThread](#m_hthread)|Enthält das Handle des Threads.|
|[CComApartment::m_nLockCnt](#m_nlockcnt)|Enthält die aktuelle Sperrenanzahl des Threads.|

## <a name="remarks"></a>Hinweise

`CComApartment` wird von [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) verwendet, um ein Apartment in einem Modul mit einem Thread im Pool zusammengefasst zu verwalten. `CComApartment` stellt Methoden zum Inkrementieren und Dekrementieren der Sperrenanzahl in einem Thread bereit.

## <a name="requirements"></a>-Anforderungen

**Header:** atlbase. h

##  <a name="apartment"></a>Ccomapartment:: Apartment

Markiert die Anfangsadresse des Threads.

```
DWORD Apartment();
```

### <a name="return-value"></a>Rückgabewert

Immer 0.

### <a name="remarks"></a>Hinweise

Wird automatisch während [CComAutoThreadModule:: init](../../atl/reference/ccomautothreadmodule-class.md#init)festgelegt.

##  <a name="ccomapartment"></a>Ccomapartment:: ccomapartment

Der Konstruktor.

```
CComApartment();
```

### <a name="remarks"></a>Hinweise

Initialisiert die `CComApartment` Datenmember [m_nLockCnt](#m_nlockcnt) und [m_hThread](#m_hthread).

##  <a name="getlockcount"></a>Ccomapartment:: GetLockCount

Gibt die aktuelle Sperrenanzahl des Threads zurück.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Rückgabewert

Die Sperrenanzahl für den Thread.

##  <a name="lock"></a>Ccomapartment:: Lock

Erhöht die Sperrenanzahl des Threads.

```
LONG Lock();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose oder das Testen nützlich sein kann.

### <a name="remarks"></a>Hinweise

Wird von [CComAutoThreadModule:: Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)aufgerufen.

Die Sperrenanzahl für den Thread wird für statistische Zwecke verwendet.

##  <a name="m_dwthreadid"></a>  CComApartment::m_dwThreadID

Enthält den Bezeichner des Threads.

```
DWORD m_dwThreadID;
```

##  <a name="m_hthread"></a>Ccomapartment:: m_hThread

Enthält das Handle des Threads.

```
HANDLE m_hThread;
```

##  <a name="m_nlockcnt"></a>Ccomapartment:: m_nLockCnt

Enthält die aktuelle Sperrenanzahl des Threads.

```
LONG m_nLockCnt;
```

##  <a name="unlock"></a>Ccomapartment:: Unlock

Verringert die Sperrenanzahl des Threads.

```
LONG Unlock();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der für die Diagnose oder das Testen nützlich sein kann.

### <a name="remarks"></a>Hinweise

Wird von [CComAutoThreadModule:: Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock)aufgerufen.

Die Sperrenanzahl für den Thread wird für statistische Zwecke verwendet.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
