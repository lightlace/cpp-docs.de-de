---
title: _putchar_nolock, _putwchar_nolock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putchar_nolock
- _putwchar_nolock
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
apitype: DLLExport
f1_keywords:
- putwchar_nolock
- _puttchar_nolock
- _putchar_nolock
- _putwchar_nolock
- putchar_nolock
dev_langs: C++
helpviewer_keywords:
- _puttchar_nolock function
- putchar_nolock function
- characters, writing
- standard output, writing to
- putwchar_nolock function
- _putchar_nolock function
- _putwchar_nolock function
- puttchar_nolock function
ms.assetid: 9ac68092-bfc3-4352-b486-c3e780220575
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7140e1d72ad73f32ced5b6d91ab0a0c0029d8182
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="putcharnolock-putwcharnolock"></a>_putchar_nolock, _putwchar_nolock
Schreibt ein Zeichen in **stdout**, ohne den Thread zu sperren.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _putchar_nolock(  
   int c   
);  
wint_t _putwchar_nolock(  
   wchar_t c   
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu schreibende Zeichen.  
  
## <a name="return-value"></a>Rückgabewert  
 Siehe **putchar, putwchar**.  
  
## <a name="remarks"></a>Hinweise  
 **putchar_nolock** und `_putwchar_nolock` sind identisch mit den Versionen ohne das **_nolock**-Suffix; allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Sie sind möglicherweise schneller, da kein Mehraufwand zur Sperrung anderer Threads erforderlich ist. Verwenden Sie diese Funktionen nur in threadsichere Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen der aufrufende Bereich die Threadisolation bereits handhabt.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_puttchar_nolock`|`_putchar_nolock`|`_putchar_nolock`|`_putwchar_nolock`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_putchar_nolock`|\<stdio.h>|  
|`_putwchar_nolock`|\<stdio.h> oder \<wchar.h>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_putchar_nolock.c  
/* This program uses putchar to write buffer  
 * to stdout. If an error occurs, the program  
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
      ch = _putchar_nolock( *p );  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
This is the line of output  
```  
  
## <a name="see-also"></a>Siehe auch  
 [E/A-Stream](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)