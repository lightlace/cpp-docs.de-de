---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
dev_langs: C++
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2733adb5cfc2328fdc0fb39650f6013c11960b3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s
Abrufen der Systemfehlermeldung (`strerror_s``_wcserror_s`) oder Drucken einer vom Benutzer angegebenen Fehlermeldung (`_strerror_s`, `__wcserror_s`). Dies sind Versionen von [strerror, _strerror, _wcserror, \__wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Puffer für die Fehlerzeichenfolge.  
  
 `numberOfElements`  
 Puffergröße.  
  
 `errnum`  
 Fehlernummer.  
  
 `strErrMsg`  
 Vom Benutzer angegebene Meldung.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
### <a name="error-condtions"></a>Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|`strErrMsg`|Inhalt von `buffer`|  
|--------------|------------------------|-----------------|--------------------------|  
|`NULL`|any|any|n/v|  
|any|0|any|nicht geändert|  
  
## <a name="remarks"></a>Hinweise  
 Die `strerror_s`-Funktion ordnet `errnum` einer Fehlermeldungszeichenfolge zu und gibt die Zeichenfolge in `buffer` zurück. `_strerror_s` verwendet nicht die Fehlernummer, sondern den aktuellen Wert von `errno`, um die entsprechende Meldung zu bestimmen. Die Meldung wird allerdings weder von `strerror_s` noch `_strerror_s` gedruckt: Dazu muss eine Ausgabefunktion wie [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) aufgerufen werden:  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 Wenn `strErrMsg``NULL` ist, gibt `_strerror_s` eine Zeichenfolge in `buffer` zurück, die die Systemfehlermeldung zu dem letzten Bibliotheksaufruf enthält, der einen Fehler erzeugt hat. Die Fehlermeldungszeichenfolge wird durch das Zeilenumbruchzeichen ('\n') beendet. Wenn `strErrMsg` nicht gleich `NULL` ist, gibt `_strerror_s` eine Zeichenfolge in `buffer` zurück, die folgende Elemente (in der angegebenen Reihenfolge) enthält: die Zeichenfolgenmeldung, einen Doppelpunkt, ein Leerzeichen, die Systemfehlermeldung zu dem letzten Bibliotheksaufruf, einen Fehler erzeugt hat, und ein Zeilenumbruchzeichen. Die Zeichenfolgenmeldung darf höchstens 94 Zeichen lang sein.  
  
 Diese Funktionen schneiden die Fehlermeldung ab, wenn die Länge `numberOfElements` – 1 überschreitet. Die resultierende Zeichenfolge in `buffer` endet immer mit NULL.  
  
 Die tatsächliche Fehlernummer für `_strerror_s` wird in der Variablen [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) gespeichert. Über die Variable [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird auf die Systemfehlermeldungen zugegriffen, die als Array von Meldungen nach Fehlernummern geordnet sind. `_strerror_s` greift auf die entsprechende Fehlermeldung zu, indem der `errno`-Wert als Index zur Variablen `_sys_errlist` verwendet wird. Der Wert der Variablen [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird als maximale Anzahl an Elementen im `_sys_errlist`-Array definiert. Um vollständige Ergebnisse zu erzeugen, rufen Sie umgehend `_strerror_s` auf, nachdem eine Bibliotheksroutine einen Fehler zurückgibt. Andernfalls können nachfolgende Aufrufe von `strerror_s` oder `_strerror_s` den `errno`-Wert überschreiben.  
  
 `_wcserror_s` und `__wcserror_s` sind jeweils Breitzeichenversionen von `strerror_s` und `_strerror_s`.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn der Puffer `NULL` oder der Größenparameter 0 ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `EINVAL` zurück und setzt `errno` auf `EINVAL`.  
  
 `_strerror_s`, `_wcserror_s`, und `__wcserror_s` sind nicht Teil der ANSI-Definition, sondern Microsoft-Erweiterungen für sie. Verwenden Sie sie nicht bei gewünschter Portabilität. Wenn Sie ANSI-Kompatibilität benötigen, verwenden Sie stattdessen `strerror_s`.  
  
 Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`strerror_s`, `_strerror_s`|\<string.h>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Betrachten Sie das Beispiel für [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)