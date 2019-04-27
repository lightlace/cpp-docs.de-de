---
title: _endthread, _endthreadex
ms.date: 11/04/2016
apiname:
- _endthread
- _endthreadex
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
ms.openlocfilehash: 2f54ca9c4cd5e863ca960f1d9c3634b85e7896dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288822"
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex

Beendet einen Thread; **_endthread** beendet einen Thread, der erstellt wird **_beginthread** und **_endthreadex** beendet einen Thread, der erstellt wird **_beginthreadex**.

## <a name="syntax"></a>Syntax

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>Parameter

*retval*<br/>
Threadexitcode.

## <a name="remarks"></a>Hinweise

Rufen Sie **_endthread** oder **_endthreadex** explizit auf einen Thread zu beenden. allerdings **_endthread** oder **_endthreadex** aufgerufen wird automatisch, wenn der Thread von der Routine zurück als Parameter an übergeben **_beginthread** oder **_beginthreadex**. Beenden eines Threads durch einen Aufruf von **Endthread** oder **_endthreadex** stellt ordnungsgemäße Wiederherstellung der dem Thread zugeordneten Ressourcen sicher.

> [!NOTE]
> Rufen Sie für eine mit „Libcmt.lib“ verknüpfte ausführbare Datei die [ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread) -Win32-API nicht auf, damit das Laufzeitsystem nicht an der Freigabe von zugeordneten Ressourcen gehindert wird. **_endthread** und **_endthreadex** zugeordnete Threadressourcen, und rufen dann **ExitThread**.

**_endthread** schließt das Threadhandle automatisch. (Dieses Verhalten unterscheidet sich vom Win32- **ExitThread** API.) Aus diesem Grund bei Verwendung von **_beginthread** und **_endthread**, explizit schließen Sie nicht das Threadhandle durch Aufrufen der Win32- ["CloseHandle"](/windows/desktop/api/handleapi/nf-handleapi-closehandle) API.

Wie Sie die Win32 **ExitThread** -API, **_endthreadex** schließt das Threadhandle nicht. Aus diesem Grund bei Verwendung von **_beginthreadex** und **_endthreadex**, müssen Sie das Threadhandle durch Aufrufen der Win32-schließen **"CloseHandle"** API.

> [!NOTE]
> **_endthread** und **_endthreadex** dazu führen, dass C++ ausstehende Destruktoren im Thread nicht aufgerufen werden.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Multithread-Versionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [_beginthread](beginthread-beginthreadex.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
