---
title: getchar, getwchar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getchar
- getwchar
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
- getwchar
- GetChar
dev_langs: C++
helpviewer_keywords:
- gettchar function
- characters, reading
- getwchar function
- _gettchar function
- standard input, reading from
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b82e9debd0ebb5084bb730a6ad06a0b8cba42df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="getchar-getwchar"></a>getchar, getwchar
Liest ein Zeichen aus der Standardeingabe.  
  
## <a name="syntax"></a>Syntax  
  
```  
int getchar();  
wint_t getwchar();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das gelesene Zeichen zurück. Zum Anzeigen eines Lesefehlers oder einer Dateiendebedingung gibt `getchar` `EOF` zurück, und `getwchar` gibt `WEOF` zurück. Verwenden Sie für `getchar``ferror` oder `feof` zur Fehler- oder Dateiendeüberprüfung.  
  
## <a name="remarks"></a>Hinweise  
 Jede Routine liest ein einzelnes Zeichen aus `stdin` und erhöht den zugeordneten Dateizeiger, um auf das nächste Zeichen zu zeigen. `getchar` entspricht [_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md), ist jedoch als Funktion und Makro implementiert.  
  
 Diese Funktionen sperren den aufrufenden Thread und sind daher threadsicher. Eine nicht sperrende Version finden Sie unter [_getc_nolock _getwc_nolock](../../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_gettchar`|`getchar`|`getchar`|`getwchar`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`getchar`|\<stdio.h>|  
|`getwchar`|\<stdio.h> oder \<wchar.h>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_getchar.c  
// Use getchar to read a line from stdin.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
  
    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
}  
```  
  
```Output  
  
This textInput was: This text  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)