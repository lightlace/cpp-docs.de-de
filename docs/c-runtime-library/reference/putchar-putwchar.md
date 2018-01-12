---
title: putchar, putwchar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- putchar
- putwchar
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
- putchar
- putwchar
- _puttchar
dev_langs: C++
helpviewer_keywords:
- putchar function
- _puttchar function
- characters, writing
- standard output, writing to
- putwchar function
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3320f40f822c9559b411144ecc621824eedbd3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="putchar-putwchar"></a>putchar, putwchar
Schreibt ein Zeichen in **stdout**.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int putchar(  
   int c   
);  
wint_t putwchar(  
   wchar_t c   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu schreibende Zeichen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das geschriebene Zeichen zurück. Um einen Fehler oder eine Dateienbedingung anzugeben, geben `putc` und `putchar` `EOF` zurück; `putwc` und `putwchar` geben **WEOF** zurück. Verwenden Sie bei allen vier Routinen [ferror](../../c-runtime-library/reference/ferror.md) oder [feof](../../c-runtime-library/reference/feof.md), um auf einen Fehler oder ein Dateiende zu prüfen. Wenn `stream` ein NULL-Zeiger ist, generieren diese Funktionen eine Ausnahme für einen ungültigen Parameter, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `EOF` oder **WEOF** zurückgegeben und `errno` auf `EINVAL` festgelegt.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `putc`-Routine schreibt das einzelne Zeichen `c` in die aktuelle Position der `stream`-Ausgabe. Jede beliebige ganze Zahl kann an `putc` übergeben werden, aber es werden nur die unteren 8 Bits geschrieben. Die `putchar`-Routine ist mit **putc(** `c`**, stdout )** identisch. Wenn ein Lesefehler auftritt, wird für jede Routine die Fehleranzeige für den Stream festgelegt. `putc` und `putchar` ähneln jeweils `fputc` und `_fputchar`, werden jedoch sowohl als Funktionen als auch als Makros implementiert (siehe [Auswählen zwischen Funktionen und Makros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). `putwc` und `putwchar` sind jeweils Breitzeichenversionen von `putc` und `putchar`.  
  
 Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Sie sind möglicherweise schneller, da kein Mehraufwand zur Sperrung anderer Threads erforderlich ist. Verwenden Sie diese Funktionen nur in threadsicheren Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen der aufrufende Bereich die Threadisolation bereits handhabt.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_puttchar`|`putchar`|`putchar`|**putwchar**|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`putchar`|\<stdio.h>|  
|`putwchar`|\<stdio.h> oder \<wchar.h>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_putchar.c  
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
  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putchar( *p );  
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