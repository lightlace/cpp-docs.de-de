---
title: Crtthreadtrait-Klasse
ms.date: 11/04/2016
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
ms.openlocfilehash: 9e12e64041e38b8fa014815870132a75885014bf
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496565"
---
# <a name="crtthreadtraits-class"></a>Crtthreadtrait-Klasse

Diese Klasse stellt die Erstellungs Funktion für einen CRT-Thread bereit. Verwenden Sie diese Klasse, wenn der Thread CRT-Funktionen verwendet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CRTThreadTraits
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRTThreadTraits::CreateThread](#createthread)|Kum Rufen Sie diese Funktion auf, um einen Thread zu erstellen, der CRT-Funktionen verwenden kann.|

## <a name="remarks"></a>Hinweise

Thread Merkmale sind Klassen, die eine Erstellungs Funktion für einen bestimmten Typ von Thread bereitstellen. Die Erstellungs Funktion verfügt über dieselbe Signatur und Semantik wie die Windows-Funktion " [kreatethread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) ".

Thread Merkmale werden von den folgenden Klassen verwendet:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

Wenn der Thread keine CRT-Funktionen verwendet, verwenden Sie stattdessen [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) .

## <a name="requirements"></a>Anforderungen

**Header:** atlbase. h

##  <a name="createthread"></a>Crtthreadtrait:: kreatethread

Rufen Sie diese Funktion auf, um einen Thread zu erstellen, der CRT-Funktionen verwenden kann.

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

Diese Funktion ruft [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) auf, um den Thread zu erstellen.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
