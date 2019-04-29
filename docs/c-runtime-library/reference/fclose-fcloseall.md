---
title: fclose, _fcloseall
ms.date: 11/04/2016
apiname:
- fclose
- _fcloseall
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 4713ffb7ecdf8da73e5f949bbef7be124dfaf28a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334878"
---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall

Schließt einen Stream (**Fclose**) oder schließt alle geöffneten Streams (**_fcloseall**).

## <a name="syntax"></a>Syntax

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**Fclose** gibt 0 zurück, wenn der Stream erfolgreich geschlossen wird. **_fcloseall** gibt die Gesamtzahl der geschlossenen Streams zurück. Beide Funktionen geben **EOF** einen Fehler an.

## <a name="remarks"></a>Hinweise

Die **Fclose** -Funktion schließt *Stream*. Wenn *Stream* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Fclose** legt **Errno** zu **EINVAL** und gibt **EOF**. Es wird empfohlen, die *Stream* Zeiger werden immer vor dem Aufrufen dieser Funktion geprüft.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Die **_fcloseall** -Funktion schließt alle offenen Streams außer **Stdin**, **"stdout"**, **"stderr"** (und in MS-DOS **_stdaux**  und **_stdprn**). Außerdem schließt und löscht alle temporären Dateien, die von erstellten **Tmpfile**. Bei beiden Funktionen werden alle Puffer, die dem Stream zugewiesen sind, vor dem Schließen geleert. Systemseitig angegebene Puffer werden freigegeben, wenn der Stream geschlossen wird. Vom Benutzer mit zugewiesenen Puffer **Setbuf** und **Setvbuf** werden nicht automatisch freigegeben.

**Hinweis**: Wenn diese Funktionen verwendet werden, um einen Stream zu schließen, werden die zugrunde liegenden Dateideskriptor und Betriebssystem-Dateihandle (oder Socket), sowie der Stream geschlossen. Daher wird die Datei ursprünglich geöffnet wurde als Dateihandle oder Dateideskriptor und geschlossen wird, mit **Fclose**, sind nicht gleichzeitig Aufruf **_close** auf den Dateideskriptor zu schließen, rufen Sie die Win32-Funktion nicht  **"CloseHandle"** um das Dateihandle zu schließen.

**Fclose** und **_fcloseall** enthält Code, der Schutz vor Störungen durch andere Threads. Für nicht sperrende Version von einem **Fclose**, finden Sie unter **_fclose_nolock**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fclose**|\<stdio.h>|
|**_fcloseall**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [open](fopen-wfopen.md).

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
