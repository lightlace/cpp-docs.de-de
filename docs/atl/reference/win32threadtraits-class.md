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
ms.openlocfilehash: d086a42f5dcdf005d10c8853776da66b691a8e11
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495477"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits-Klasse

Diese Klasse stellt die Erstellungs Funktion für einen Windows-Thread bereit. Verwenden Sie diese Klasse, wenn der Thread keine CRT-Funktionen verwendet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class Win32ThreadTraits
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Win32ThreadTraits::CreateThread](#createthread)|Kum Rufen Sie diese Funktion auf, um einen Thread zu erstellen, der keine CRT-Funktionen verwenden soll.|

## <a name="remarks"></a>Hinweise

Thread Merkmale sind Klassen, die eine Erstellungs Funktion für einen bestimmten Typ von Thread bereitstellen. Die Erstellungs Funktion verfügt über dieselbe Signatur und Semantik wie die Windows-Funktion " [kreatethread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) ".

Thread Merkmale werden von den folgenden Klassen verwendet:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

Wenn der Thread CRT-Funktionen verwendet, verwenden Sie stattdessen [crtthreadmerkmalen](../../atl/reference/crtthreadtraits-class.md) .

## <a name="requirements"></a>Anforderungen

**Header:** atlbase. h

##  <a name="createthread"></a>Win32ThreadTraits:: kreatethread

Rufen Sie diese Funktion auf, um einen Thread zu erstellen, der keine CRT-Funktionen verwenden soll.

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
Die Sicherheits Attribute für den neuen Thread.

*dwStackSize*<br/>
Die Stapelgröße für den neuen Thread.

*pfnThreadProc*<br/>
Die Thread Prozedur des neuen Threads.

*pvParam*<br/>
Der Parameter, der an die Thread Prozedur übergeben werden soll.

*dwCreationFlags*<br/>
Die erstellungsflags (0 oder CREATE_SUSPENDED).

*pdwThreadId*<br/>
vorgenommen Adresse der DWORD-Variablen, die bei Erfolg die Thread-ID des neu erstellten Threads empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt das Handle für den neu erstellten Thread oder NULL bei einem Fehler zurück. [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufrufen, um erweiterte Fehlerinformationen abzurufen.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu den Parametern für diese Funktion finden Sie unter " [kreatethread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) ".

Diese Funktion ruft `CreateThread` auf, um den Thread zu erstellen.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
