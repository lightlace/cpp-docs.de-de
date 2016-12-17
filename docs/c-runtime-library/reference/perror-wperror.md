---
title: "perror, _wperror"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_wperror"
  - "perror"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wperror"
  - "_tperror"
  - "perror"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tperror-Funktion"
  - "_wperror-Funktion"
  - "Fehlermeldungen, Drucken"
  - "perror-Funktion"
  - "Druckfehlermeldungen"
  - "tperror-Funktion"
  - "wperror-Funktion"
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# perror, _wperror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Drucken Sie eine Fehlermeldung.  
  
## Syntax  
  
```  
  
      void perror(  
   const char *string   
);  
void _wperror(  
   const wchar_t *string   
);  
```  
  
#### Parameter  
 `string`  
 Reihe Sie Meldung auf, um zu drucken.  
  
## Hinweise  
 Die `perror`\-Funktion gibt eine Fehlermeldung zu `stderr`.  `_wperror` ist eine Breitzeichen\-Version von **\_perror**; `string` das Argument für `_wperror` ist eine Zeichenfolge mit Breitzeichen.  `_wperror` und **\_perror** identisch verhalten sich andernfalls.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tperror`|`perror`|`perror`|`_wperror`|  
  
 `string` wird zuerst ausgegeben, gefolgt von einem Doppelpunkt, dann der Systemfehlermeldung für den letzten Bibliotheksaufruf, der den Fehler hat, und schließlich von einem Zeilenumbruchzeichen.  Wenn `string` ein NULL\-Zeiger oder ein Zeiger auf eine NULL\-Zeichenfolge ist, gibt `perror` nur die Systemfehlermeldung.  
  
 Die Fehlernummer wird in der Variablen [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) gespeichert \(in ERRNO.H\).  Über die Variable [\_sys\_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird auf die Systemfehlermeldungen zugegriffen, die als Array von Meldungen nach Fehlernummern geordnet sind.  `perror` gibt die entsprechende Fehlermeldung mit dem `errno`\-Wert als Index an `_sys_errlist`.  Der Wert der Variablen [\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird als maximale Anzahl an Elementen im `_sys_errlist`\-Array definiert.  
  
 Spezifische Ergebnisse kehrt Aufruf `perror` sofort nach einer Bibliotheksroutine mit einen Fehler zurück.  Andernfalls können nachfolgende Aufrufe den `errno`\-Wert überschreiben.  
  
 Im Windows\-Betriebssystem können einige `errno`\-Werte, die in ERRNO.H aufgeführt werden, nicht verwendet.  Diese Werte werden zum UNIX\-Betriebssystem reserviert.  [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) finden Sie Listen von `errno`\-Werten, die vom Windows\-Betriebssystem verwendet werden.  `perror` gibt eine leere Zeichenfolge für jeden `errno`\-Wert, der nicht durch diese Plattformen verwendet wird.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`perror`|\<stdio.h oder\> stdlib.h \<\>|  
|`_wperror`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
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
  
## Ausgabe  
  
```  
perror says open failed: No such file or directory  
strerror says open failed: No such file or directory  
_strerror says open failed: No such file or directory  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [strerror, \_strerror, \_wcserror, \_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)