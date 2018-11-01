---
title: Win32ThreadTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
ms.openlocfilehash: 79d4d1a4fbbd5b2bddeafeaa9ea37b43d1b8c259
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574810"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits-Klasse

Diese Klasse stellt die Erstellungsfunktion für einen Windows-Thread. Verwenden Sie diese Klasse aus, wenn der Thread nicht CRT-Funktionen nutzen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class Win32ThreadTraits
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Win32ThreadTraits::CreateThread](#createthread)|(Statisch) Rufen Sie diese Funktion zur Erstellung eines Threads, das keine CRT-Funktionen verwenden sollten.|

## <a name="remarks"></a>Hinweise

Thread "traits" sind Klassen, die eine Funktion für einen bestimmten Typ des Threads zu ermöglichen. Die Erstellungsfunktion weist die gleiche Signatur und die gleiche Semantik wie die Windows [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) Funktion.

Thread "traits" werden die folgenden Klassen verwendet:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

Wenn der Thread CRT-Funktionen verwenden, verwenden Sie [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) stattdessen.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="createthread"></a>  Win32ThreadTraits::CreateThread

Rufen Sie diese Funktion zur Erstellung eines Threads, das keine CRT-Funktionen verwenden sollten.

```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```

### <a name="parameters"></a>Parameter

*lpsa*<br/>
Die Sicherheitsattribute für den neuen Thread.

*dwStackSize*<br/>
Die Stapelgröße für den neuen Thread.

*pfnThreadProc*<br/>
Die Threadprozedur des neuen Threads.

*pvParam*<br/>
Der Parameter an die Threadprozedur übergeben werden.

*"dwCreationFlags"*<br/>
Die Erstellung flags ("0" oder "CREATE_SUSPENDED").

*pdwThreadId*<br/>
[out] Adresse der DWORD-Variable, die bei Erfolg die Thread-ID des neu erstellten Threads empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt das Handle auf das neu erstellte Thread oder NULL bei einem Fehler zurück. Rufen Sie [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) um erweiterte Fehlerinformationen abzurufen.

### <a name="remarks"></a>Hinweise

Finden Sie unter [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) für Weitere Informationen zu den Parametern für diese Funktion.

Diese Funktion ruft `CreateThread` um den Thread erstellen.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
