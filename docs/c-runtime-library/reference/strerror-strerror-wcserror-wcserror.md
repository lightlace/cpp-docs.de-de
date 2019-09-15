---
title: strerror, _strerror, _wcserror, __wcserror
ms.date: 11/04/2016
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
ms.openlocfilehash: 0b4d70687bc2f428162d035c80d6bc8525a8fb9e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958147"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Ruft eine Fehlermeldungs-Zeichenfolge ("**strinerror**", " **_wcserror**") oder eine vom Benutzer bereitgestellte Fehlermeldungs Zeichenfolge ( **_strerror**, **__wcserror**) ab Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

## <a name="syntax"></a>Syntax

```C
char *strerror(
   int errnum
);
char *_strerror(
   const char *strErrMsg
);
wchar_t * _wcserror(
   int errnum
);
wchar_t * __wcserror(
   const wchar_t *strErrMsg
);
```

### <a name="parameters"></a>Parameter

*errnum*<br/>
Fehlernummer.

*strErrMsg*<br/>
Vom Benutzer angegebene Meldung.

## <a name="return-value"></a>Rückgabewert

All diese Funktionen geben einen Zeiger zur Fehlermeldungszeichenfolge zurück. Nachfolgende Aufrufe können die Zeichenfolge überschreiben.

## <a name="remarks"></a>Hinweise

Die " **strauerror** "-Funktion ordnet *errnum* einer Fehlermeldungs Zeichenfolge zu und gibt einen Zeiger auf die Zeichenfolge zurück. Weder " **strinerror** " noch " **_strerror** " druckt die Meldung: Dazu muss eine Ausgabefunktion wie z. [b. fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)aufgerufen werden:

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

Wenn " *stringermsg* " als **null**-Wert ausgegeben wird, gibt **_strerror** einen Zeiger auf eine Zeichenfolge zurück, die die System Fehlermeldung für den letzten Bibliotheks Befehl enthält, der einen Fehler verursacht hat. Die Fehlermeldungszeichenfolge wird durch das Zeilenumbruchzeichen ('\n') beendet. Wenn " *darerrmsg* " nicht gleich **null**ist, gibt **_strerror** einen Zeiger auf eine Zeichenfolge zurück, die (in der richtigen Reihenfolge) die Zeichen folgen Meldung, einen Doppelpunkt, ein Leerzeichen, die System Fehlermeldung für den letzten Bibliotheks Befehl, der einen Fehler erzeugt, und einen Zeilen Vorzug enthält. Art. Die Zeichenfolgenmeldung darf höchstens 94 Zeichen lang sein.

Die tatsächliche Fehlernummer für **_strerror** wird in der Variablen [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)gespeichert. Um genaue Ergebnisse zu erzielen, rufen Sie **_strerror** sofort auf, nachdem eine Bibliotheks Routine mit einem Fehler zurückgegeben wurde. Andernfalls können nachfolgende Aufrufe von " **strauerror** " oder " **_strerror** " den **errno** -Wert überschreiben.

**_wcserror** und **__wcserror** sind breit Zeichen Versionen von " **strauerror** " bzw. " **_strerror**".

**_strerror**, **_wcserror**und **__wcserror** sind nicht Teil der ANSI-Definition. Dabei handelt es sich um Microsoft-Erweiterungen. es wird empfohlen, Sie nicht zu verwenden, wenn Sie portablen Code verwenden möchten. Verwenden Sie für die ANSI-Kompatibilität stattdessen " **strauerror** ".

Zum erhalten von Fehler Zeichenfolgen empfehlen wir **strerror** oder **_wcserror** anstelle der veralteten Makros [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) und [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) und die veralteten internen Funktionen **__sys_errlist** und **__sys_nerr**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Betrachten Sie das Beispiel für [perror](perror-wperror.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
