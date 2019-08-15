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
ms.openlocfilehash: 5afbc907356d4c5b14b749de5de0c8d36280891e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499963"
---
# <a name="_endthread-_endthreadex"></a>_endthread, _endthreadex

Beendet einen Thread. **_endthread** beendet einen Thread, der von **_beginthread** erstellt wird, und **_endthreadex** beendet einen von **_beginthreadex**erstellten Thread.

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

Sie können **_endthread** oder **_endthreadex** explizit zum Beenden eines Threads aufruft. **_endthread** oder **_endthreadex** wird jedoch automatisch aufgerufen, wenn der Thread aus der als Parameter an **_beginthread** oder **_beginthreadex**übergebenen Routine zurückgegeben wird. Durch das Beenden eines Threads mit einem -Endpunkt oder **_endthreadex** wird sichergestellt, dass die für den Thread zugewiesenen Ressourcen ordnungsgemäß wieder hergestellt werden.

> [!NOTE]
> Rufen Sie für eine mit „Libcmt.lib“ verknüpfte ausführbare Datei die [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) -Win32-API nicht auf, damit das Laufzeitsystem nicht an der Freigabe von zugeordneten Ressourcen gehindert wird. **_endthread** und **_endthreadex** rufen zugeordnete Thread Ressourcen frei und rufen dann **ExitThread**auf.

**_endthread** schließt das Thread Handle automatisch. (Dieses Verhalten unterscheidet sich von der Win32- **ExitThread** -API.) Wenn Sie also **_beginthread** und **_endthread**verwenden, schließen Sie das Thread Handle nicht explizit, indem Sie die Win32- [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) -API aufrufen.

Wie bei der **ExitThread** -API von Win32 schließt **_endthreadex** nicht das Thread handle. Wenn Sie also **_beginthreadex** und **_endthreadex**verwenden, müssen Sie das Thread handle schließen, indem Sie die Win32- **CloseHandle** -API aufrufen.

> [!NOTE]
> **_endthread** und **_endthreadex** bewirken C++ , dass deerausstehende deerdektoren im Thread nicht aufgerufen werden.

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
