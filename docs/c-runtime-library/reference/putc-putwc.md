---
title: putc, putwc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- putwc
- putc
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
- _puttc
- putwc
- putc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e7df1c7810719092874990286c1b22b7e7ec6faa
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="putc-putwc"></a>putc, putwc
Schreibt ein Zeichen in einen Stream.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int putc(  
   int c,  
   FILE *stream   
);  
wint_t putwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu schreibende Zeichen.  
  
 `stream`  
 Zeiger auf die **FILE**-Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das geschriebene Zeichen zurück. Um einen Fehler oder eine Dateienbedingung anzugeben, geben `putc` und `putchar` `EOF` zurück; `putwc` und `putwchar` geben **WEOF** zurück. Verwenden Sie bei allen vier Routinen [ferror](../../c-runtime-library/reference/ferror.md) oder [feof](../../c-runtime-library/reference/feof.md), um auf einen Fehler oder ein Dateiende zu prüfen. Wenn `stream` ein NULL-Zeiger ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EOF` oder **WEOF** zurück und stellen `errno` auf `EINVAL` ein.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `putc`-Routine schreibt das einzelne Zeichen `c` in die aktuelle Position der `stream`-Ausgabe. Jede beliebige ganze Zahl kann an `putc` übergeben werden, aber es werden nur die unteren 8 Bits geschrieben. Die `putchar`-Routine ist mit **putc(** `c`**, stdout )** identisch. Wenn ein Lesefehler auftritt, wird für jede Routine die Fehleranzeige für den Stream festgelegt. `putc` und `putchar` ähneln jeweils `fputc` und `_fputchar`, werden jedoch sowohl als Funktionen als auch als Makros implementiert (siehe [Auswählen zwischen Funktionen und Makros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). `putwc` und `putwchar` sind jeweils Breitzeichenversionen von `putc` und `putchar`. `putwc` und `putc` verhalten sich identisch, wenn der Stream in ANSI-Modus geöffnet ist. `putc` unterstützt derzeit die Ausgabe in einen UNICODE-Stream nicht.  
  
 Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter **_putc_nolock, _putwc_nolock**.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`putc`|\<stdio.h>|  
|`putwc`|\<stdio.h> oder \<wchar.h>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_putc.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
   /* Make standard out the stream and write to it. */  
   stream = stdout;  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putc( *p, stream );  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
This is the line of output  
```  
  
## <a name="see-also"></a>Siehe auch  
 [E/A-Stream](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)