---
title: strerror, _strerror, _wcserror, __wcserror | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85fee7ce2b3c4264e8593082640489aae01cb9e0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror
Ruft eine Systemfehlermeldungs-Zeichenfolge (`strerror`, `_wcserror`) ab oder formatiert eine vom Benutzer bereitgestellte Fehlermeldungszeichenfolge (`_strerror`, `__wcserror`). Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `errnum`  
 Fehlernummer.  
  
 `strErrMsg`  
 Vom Benutzer angegebene Meldung.  
  
## <a name="return-value"></a>Rückgabewert  
 All diese Funktionen geben einen Zeiger zur Fehlermeldungszeichenfolge zurück. Nachfolgende Aufrufe können die Zeichenfolge überschreiben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `strerror` ordnet `errnum` einer Fehlermeldungszeichenfolge zu und gibt einen Zeiger zur Zeichenfolge zurück. Die Meldung wird allerdings weder von `strerror` noch `_strerror` gedruckt: Dazu muss eine Ausgabefunktion wie [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) aufgerufen werden:  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 Wenn `strErrMsg` als `NULL` übergeben wird, gibt `_strerror` einen Zeiger auf eine Zeichenfolge zurück, die die Systemfehlermeldung für den letzten Bibliotheksaufruf enthält, die einen Fehler produziert hat. Die Fehlermeldungszeichenfolge wird durch das Zeilenumbruchzeichen ('\n') beendet. Wenn `strErrMsg` nicht gleich `NULL` ist, gibt `_strerror` einen Zeiger zu einer Zeichenfolge zurück, die folgende Elemente (in der angegebenen Reihenfolge) enthält: die Zeichenfolgenmeldung, einen Doppelpunkt, ein Leerzeichen, die Systemfehlermeldung zu dem letzten Bibliotheksaufruf, der einen Fehler erzeugt hat, und ein Zeilenumbruchzeichen. Die Zeichenfolgenmeldung darf höchstens 94 Zeichen lang sein.  
  
 Die tatsächliche Fehlernummer für `_strerror` wird in der Variablen [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) gespeichert. Um vollständige Ergebnisse zu erzeugen, rufen Sie umgehend `_strerror` auf, nachdem eine Bibliotheksroutine einen Fehler zurückgibt. Andernfalls können nachfolgende Aufrufe von `strerror` oder `_strerror` den `errno`-Wert überschreiben.  
  
 `_wcserror` und `__wcserror` sind jeweils Breitzeichenversionen von `strerror` und `_strerror`.  
  
 `_strerror`, `_wcserror` und `__wcserror` sind nicht Teil der ANSI-Definition, sondern Microsoft-Erweiterungen. Es wird empfohlen, diese nicht zu verwenden, wenn Sie portablen Code möchten. Verwenden Sie für ANSI-Kompatibilität stattdessen `strerror`.  
  
 Zum Abrufen von Fehlerzeichenfolgen wird `strerror` oder `_wcserror` anstelle der veralteten Makros [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) und [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) sowie der veralteten internen Funktionen `__sys_errlist` und `__sys_nerr` empfohlen.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`strerror`|\<string.h>|  
|`_strerror`|\<string.h>|  
|`_wcserror`, `__wcserror`|\<string.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Betrachten Sie das Beispiel für [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)