---
title: strerror, _strerror, _wcserror, __wcserror | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
dev_langs:
- C++
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
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 91b2460019d437f91b17f7aabc8522da53f6a61a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Ruft eine systemfehlermeldungs-Zeichenfolge (**Strerror**, **_wcserror**) oder eine Benutzer bereitgestellte Fehlermeldungszeichenfolge-Formate (**_strerror**, **__wcserror**). Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

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

Die **Strerror** -Funktion ordnet *Errnum* auf eine Zeichenfolge der Fehlermeldung und gibt einen Zeiger auf die Zeichenfolge zurück. Weder **Strerror** noch **_strerror** die Meldung gedruckt: dazu müssen Sie eine Ausgabefunktion wie z. B. [Fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

Wenn *StrErrMsg* übergeben wird, als **NULL**, **_strerror** gibt einen Zeiger auf eine Zeichenfolge, die die Systemfehlermeldung zu dem letzten Bibliotheksaufruf enthält, die einen Fehler produziert hat. Die Fehlermeldungszeichenfolge wird durch das Zeilenumbruchzeichen ('\n') beendet. Wenn *StrErrMsg* stimmt nicht mit **NULL**, klicken Sie dann **_strerror** gibt einen Zeiger auf eine Zeichenfolge, die (in entsprechender Reihenfolge), die zeichenfolgenmeldung, einen Doppelpunkt, ein Leerzeichen, die Systemfehler enthält Meldung für die letzten Bibliotheksaufruf, die keinen Fehler, und ein Zeilenumbruchzeichen erzeugt. Die Zeichenfolgenmeldung darf höchstens 94 Zeichen lang sein.

Die tatsächliche Fehlernummer für **_strerror** ist in der Variablen gespeicherte [Errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Um vollständige Ergebnisse zu erzeugen, rufen **_strerror** sofort, nachdem eine Bibliotheksroutine einen Fehler zurückgibt. Andernfalls nachfolgende Aufrufe von **Strerror** oder **_strerror** können überschreiben die **Errno** Wert.

**_wcserror** und **__wcserror** sind Breitzeichenversionen von **Strerror** und **_strerror**zugeordnet.

**_strerror**, **_wcserror**, und **__wcserror** sind nicht Teil der ANSI-Definition. sie sind Microsoft-Erweiterungen und es wird empfohlen, dass Sie nicht zu verwenden, in dem Sie portablen Code möchten. Verwenden Sie für ANSI-Kompatibilität **Strerror** stattdessen.

Zum Abrufen von Fehlerzeichenfolgen sollten **Strerror** oder **_wcserror** anstelle der veralteten Makros [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) und [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) und der veralteten internen Funktionen **__sys_errlist** und **__sys_nerr**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
