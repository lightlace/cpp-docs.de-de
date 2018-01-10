---
title: getc, getwc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getwc
- getc
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
- _gettc
- getwc
- _gettchar
- getc
dev_langs: C++
helpviewer_keywords:
- characters, reading
- _gettc function
- getwchar function
- streams, reading characters from
- reading characters from streams
- getc function
- getwc function
- gettc function
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12ddc1fa68f1b27fa96ffb81ef24004fd1fb0a19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="getc-getwc"></a>getc, getwc
Liest ein Zeichen aus einem Stream.  
  
## <a name="syntax"></a>Syntax  
  
```  
int getc(   
   FILE *stream   
);  
wint_t getwc(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Eingabestream  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das gelesene Zeichen zurück. Zum Anzeigen eines Lesefehlers oder einer Dateiendebedingung gibt `getc` `EOF` zurück, und `getwc` gibt `WEOF` zurück. Verwenden Sie für `getc``ferror` oder `feof` zur Fehler- oder Dateiendeüberprüfung. Wenn `stream` `NULL` ist, rufen `getc` und `getwc` den ungültigen Parameterhandler, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, auf. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück `EOF` (oder `WEOF` für `getwc`), und legen `errno` auf `EINVAL`.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Jede Routine liest ein einzelnes Zeichen aus einer Datei an der aktuellen Position und erhöht den zugeordneten Dateizeiger (wenn definiert), um auf das nächste Zeichen zu zeigen. Die Datei ist `stream` zugeordnet.  
  
 Diese Funktionen sperren den aufrufenden Thread und sind daher threadsicher. Eine nicht sperrende Version finden Sie unter [_getc_nolock _getwc_nolock](../../c-runtime-library/reference/getc-nolock-getwc-nolock.md).  
  
 Es folgen routinespezifische Hinweise.  
  
|-Routine zurückgegebener Wert|Hinweise|  
|-------------|-------------|  
|`getc`|Genau so wie `fgetc`, jedoch als Funktion und Makro implementiert.|  
|`getwc`|Breitzeichenversion von `getc`. Liest ein Multibytezeichen oder Breitzeichen, je nachdem, ob `stream` im Textmodus oder im Binärdateimodus geöffnet ist.|  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_gettc`|`getc`|`getc`|`getwc`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`getc`|\<stdio.h>|  
|`getwc`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_getc.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc.txt".   
  
    fopen_s(&fp, "crt_getc.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc.txt.\n");  
       exit(1);  
    }  
  
    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
  
    fclose(fp);  
}  
```  
  
## <a name="input-crtgetctxt"></a>Eingabe: crt_getc.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
Input was: Line one.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)