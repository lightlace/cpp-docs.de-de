---
title: _putc_nolock, _putwc_nolock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putc_nolock
- _putwc_nolock
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
- _puttc_nolock
- puttc_nolock
- putwc_nolock
- _putwc_nolock
- _putc_nolock
- putc_nolock
dev_langs:
- C++
helpviewer_keywords:
- puttc_nolock function
- putc_nolock function
- _putc_nolock function
- streams, writing characters to
- characters, writing
- putwc_nolock function
- _puttc_nolock function
- _putwc_nolock function
ms.assetid: 3cfc7f21-c9e8-4b7f-b0fb-af0d4d85e7e1
caps.latest.revision: 15
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
ms.openlocfilehash: a92fc2fe740d52c2040c8dc479e2ffaa8607989a
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="putcnolock-putwcnolock"></a>_putc_nolock, _putwc_nolock
Schreibt ein Zeichen in einen Stream, ohne den Thread zu sperren.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _putc_nolock(  
   int c,  
   FILE *stream   
);  
wint_t _putwc_nolock(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu schreibende Zeichen.  
  
 `stream`  
 Zeiger zur **FILE**-Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Siehe **putc, putwc**.  
  
## <a name="remarks"></a>Hinweise  
 `_putc_nolock` und `_putwc_nolock` sind identisch mit den Versionen ohne das **_nolock**-Suffix; allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Sie sind möglicherweise schneller, da kein Mehraufwand zur Sperrung anderer Threads erforderlich ist. Verwenden Sie diese Funktionen nur in threadsichere Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen der aufrufende Bereich die Threadisolation bereits handhabt.  
  
 `_putwc_nolock` ist die Breitzeichenversion von `_putc_nolock`; die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. `_putc_nolock` unterstützt derzeit die Ausgabe in einen UNICODE-Stream nicht.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_puttc_nolock`|`_putc_nolock`|`_putc_nolock`|**_putwc_nolock**|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_putc_nolock`|\<stdio.h>|  
|`_putwc_nolock`|\<stdio.h> oder \<wchar.h>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_putc_nolock.c  
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
      ch = _putc_nolock( *p, stream );  
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
