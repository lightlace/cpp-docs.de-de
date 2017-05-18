---
title: perror _wperror | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wperror
- perror
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
- _wperror
- _tperror
- perror
dev_langs:
- C++
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f263a40a56c7f94e022a8410724a7b2f3379e5d0
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="perror-wperror"></a>perror, _wperror
Druckt eine Fehlermeldung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void perror(  
   const char *string   
);  
void _wperror(  
   const wchar_t *string   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `string`  
 Zu druckende Zeichenfolgennachricht.  
  
## <a name="remarks"></a>Hinweise  
 Die `perror`-Funktion druckt eine Fehlermeldung für `stderr`. `_wperror` ist eine Breitzeichenversion von **_perror**. Das `string`-Argument für `_wperror` ist eine Breitzeichenfolge. Andernfalls verhalten sich `_wperror` und **_perror** identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tperror`|`perror`|`perror`|`_wperror`|  
  
 `string` wird zuerst gedruckt, gefolgt von einem Doppelpunkt und dann von einer Systemfehlermeldung für den letzten Bibliotheksaufruf, der den Fehler verursacht hat, und schließlich von einem Zeilenumbruchzeichen. Wenn `string` ein NULL-Zeiger oder ein Zeiger auf eine NULL-Zeichenfolge ist, druckt `perror` nur die System-Fehlermeldung.  
  
 Die Fehlernummer wird in der Variablen [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) (in ERRNO.H definiert) gespeichert. Über die Variable [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird auf die Systemfehlermeldungen zugegriffen, die als Array von Meldungen nach Fehlernummern geordnet sind. `perror` druckt die entsprechende Fehlermeldung, indem der `errno`-Wert als Index zu `_sys_errlist` verwendet wird. Der Wert der Variablen [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird als maximale Anzahl an Elementen im `_sys_errlist`-Array definiert.  
  
 Um vollständige Ergebnisse zu erzeugen, rufen Sie umgehend `perror` auf, nachdem eine Bibliotheksroutine einen Fehler zurückgibt. Andernfalls können nachfolgende Aufrufe den `errno`-Wert überschreiben.  
  
 Im Windows-Betriebssystem werden einige `errno`-Werte, die in ERRNO.H aufgelistet sind, nicht verwendet. Diese Werte sind für die Verwendung des UNIX-Betriebssystems reserviert. Siehe [_doserrno, errno, _sys_errlist, und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) für eine Liste der `errno`-Werte, die vom Windows-Betriebssystem verwendet werden. `perror` druckt eine leere Zeichenfolge für jeden `errno`-Wert, der nicht von diesen Plattformen verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`perror`|\<stdio.h > oder \<stdlib.h >|  
|`_wperror`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_perror.c  
// compile with: /W3  
/* This program attempts to open a file named  
 * NOSUCHF.ILE. Because this file probably doesn't exist,  
 * an error message is displayed. The same message is  
 * created using perror, strerror, and _strerror.  
 */  
  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <share.h>  
  
int main( void )  
{  
   int  fh;  
  
   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )  
   {  
      /* Three ways to create error message: */  
      perror( "perror says open failed" );  
      printf( "strerror says open failed: %s\n",  
         strerror( errno ) ); // C4996  
      printf( _strerror( "_strerror says open failed" ) ); // C4996  
      // Note: strerror and _strerror are deprecated; consider  
      // using strerror_s and _strerror_s instead.  
   }  
   else  
   {  
      printf( "open succeeded on input file\n" );  
      _close( fh );  
   }  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
perror says open failed: No such file or directory  
strerror says open failed: No such file or directory  
_strerror says open failed: No such file or directory  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [strerror, _strerror, _wcserror, \__wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)
