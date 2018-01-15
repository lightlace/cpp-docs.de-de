---
title: fputc, fputwc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fputc
- fputwc
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
- fputc
- fputwc
- _fputtc
dev_langs: C++
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 06f9fb737ac57ad04a661eb0e8438b3d557c0e3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fputc-fputwc"></a>fputc, fputwc
Schreibt ein Zeichen in einen Stream.  
  
## <a name="syntax"></a>Syntax  
  
```  
int fputc(  
   int c,  
   FILE *stream   
);  
wint_t fputwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu schreibende Zeichen.  
  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt das geschriebene Zeichen zurück. Bei `fputc` gibt ein Rückgabewert von `EOF` einen Fehler an. Bei `fputwc` gibt ein Rückgabewert von `WEOF` einen Fehler an. Wenn `stream` `NULL` ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `EOF` zurückgegeben und `errno` auf `EINVAL` festgelegt.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen schreibt das einzelne Zeichen `c` an der Position, die durch die dazugehörige Dateipositionsanzeige (sofern definiert) angegeben ist, in eine Datei und versetzt die Anzeige entsprechend nach vorn. Im Fall von `fputc` und `fputwc`, die Datei zugeordnet ist `stream`. Wenn die Datei keine Positionierungsanforderungen unterstützt oder im Append-Modus geöffnet wurde, wird das Zeichen am Ende des Streams angefügt.  
  
 Die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. `fputc` unterstützt die Ausgabe in einen UNICODE-Stream augenblicklich nicht.  
  
 Die Versionen mit dem `_nolock`-Suffix sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter [_fputc_nolock, _fputwc_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md).  
  
 Es folgen routinespezifische Hinweise.  
  
|-Routine zurückgegebener Wert|Hinweise|  
|-------------|-------------|  
|`fputc`|Entspricht `putc`, wird jedoch anstelle einer Funktion und eines Makros nur als Funktion implementiert.|  
|`fputwc`|Breitzeichenversion von `fputc`. Schreibt `c` als Multibytezeichen oder Breitzeichen, je nachdem, ob `stream` im Textmodus oder im Binärdateimodus geöffnet ist.|  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fputc`|\<stdio.h>|  
|`fputwc`|\<stdio.h> oder \<wchar.h>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_fputc.c  
// This program uses fputc  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of fputc!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
```Output  
This is a test of fputc!!  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)