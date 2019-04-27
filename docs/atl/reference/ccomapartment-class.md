---
title: CComApartment-Klasse
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
ms.openlocfilehash: 92db42a45a0863f8b43f7c46da9624e424d1e488
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246777"
---
# <a name="ccomapartment-class"></a>CComApartment-Klasse

Diese Klasse bietet Unterstützung für die Verwaltung einer Appartementnummer in einem Thread Pooling-EXE-Modul.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CComApartment
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComApartment::CComApartment](#ccomapartment)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComApartment::Apartment](#apartment)|Markiert die Startadresse des Threads.|
|[CComApartment::GetLockCount](#getlockcount)|Gibt die Anzahl von aktuellen Sperren des Threads zurück.|
|[CComApartment::Lock](#lock)|Erhöht die Sperrenanzahl des Threads.|
|[CComApartment::Unlock](#unlock)|Verringert die Sperrenanzahl des Threads.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComApartment::m_dwThreadID](#m_dwthreadid)|Enthält den Threadbezeichner des.|
|[CComApartment::m_hThread](#m_hthread)|Enthält das Handle des Threads.|
|[CComApartment::m_nLockCnt](#m_nlockcnt)|Enthält die Anzahl von aktuellen Sperren des Threads.|

## <a name="remarks"></a>Hinweise

`CComApartment` Dient der [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) eine Wohnung in einem Thread Pooling-EXE-Modul zu verwalten. `CComApartment` bietet Methoden zum Inkrementieren und Dekrementieren die Sperre für einen Thread zählen.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="apartment"></a>  CComApartment::Apartment

Markiert die Startadresse des Threads.

```
DWORD Apartment();
```

### <a name="return-value"></a>Rückgabewert

Always 0.

### <a name="remarks"></a>Hinweise

Automatisch festgelegt, während der [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).

##  <a name="ccomapartment"></a>  CComApartment::CComApartment

Der Konstruktor.

```
CComApartment();
```

### <a name="remarks"></a>Hinweise

Initialisiert die `CComApartment` Datenmember [M_nLockCnt](#m_nlockcnt) und [M_hThread](#m_hthread).

##  <a name="getlockcount"></a>  CComApartment::GetLockCount

Gibt die Anzahl von aktuellen Sperren des Threads zurück.

```
LONG GetLockCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Sperren für den Thread.

##  <a name="lock"></a>  CComApartment::Lock

Erhöht die Sperrenanzahl des Threads.

```
LONG Lock();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.

### <a name="remarks"></a>Hinweise

Wird aufgerufen, indem [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Die Anzahl der Sperren für den Thread wird für statistische Zwecke verwendet.

##  <a name="m_dwthreadid"></a>  CComApartment::m_dwThreadID

Enthält den Threadbezeichner des.

```
DWORD m_dwThreadID;
```

##  <a name="m_hthread"></a>  CComApartment::m_hThread

Enthält das Handle des Threads.

```
HANDLE m_hThread;
```

##  <a name="m_nlockcnt"></a>  CComApartment::m_nLockCnt

Enthält die Anzahl von aktuellen Sperren des Threads.

```
LONG m_nLockCnt;
```

##  <a name="unlock"></a>  CComApartment::Unlock

Verringert die Sperrenanzahl des Threads.

```
LONG Unlock();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.

### <a name="remarks"></a>Hinweise

Wird aufgerufen, indem [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).

Die Anzahl der Sperren für den Thread wird für statistische Zwecke verwendet.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
