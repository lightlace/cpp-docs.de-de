---
title: _ungetc_nolock, _ungetwc_nolock
ms.date: 11/04/2016
apiname:
- _ungetwc_nolock
- _ungetc_nolock
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
- _ungettc_nolock
- ungetwc_nolock
- ungetc_nolock
- _ungetc_nolock
- _ungetwc_nolock
helpviewer_keywords:
- _ungettc_nolock function
- _ungetwc_nolock function
- characters, pushing back onto stream
- _ungetc_nolock function
- ungetwc_nolock function
- ungettc_nolock function
- ungetc_nolock function
ms.assetid: aa02d5c2-1be1-46d2-a8c4-b61269e9d465
ms.openlocfilehash: 17fadee825aff7b691db74eaaa7b695ba5a49a42
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482861"
---
# <a name="ungetcnolock-ungetwcnolock"></a>_ungetc_nolock, _ungetwc_nolock

Schiebt ein Zeichen zurück auf den Stream.

## <a name="syntax"></a>Syntax

```C
int _ungetc_nolock(
   int c,
   FILE *stream
);
wint_t _ungetwc_nolock(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu verschiebendes Zeichen.

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, jede dieser Funktionen das Zeichenargument zurückgibt *c*. Wenn *c* nicht zurückgeschoben werden oder wenn kein Zeichen gelesen wurde, der Eingabestream unverändert und **_ungetc_nolock** gibt ** EOF`; **_ungetwc_nolock` gibt **WEOF**. Wenn *Stream* ist **NULL**, **EOF** oder **WEOF** zurückgegeben und **Errno** nastaven NA hodnotu  **EINVAL**.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Diese Funktionen sind nicht sperrende Versionen von **Ungetc** und **Ungetwc**. Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Sie sind möglicherweise schneller, da kein Mehraufwand zur Sperrung anderer Threads erforderlich ist. Verwenden Sie diese Funktionen nur in threadsicheren Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen der aufrufende Bereich die Threadisolation bereits handhabt.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc_nolock**|**_ungetc_nolock**|**_ungetc_nolock**|**_ungetwc_nolock**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_ungetc_nolock**|\<stdio.h>|
|**_ungetwc_nolock**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
