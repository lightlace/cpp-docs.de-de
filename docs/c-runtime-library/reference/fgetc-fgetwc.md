---
title: fgetc, fgetwc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgetwc
- fgetc
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
- _fgettc
- fgetwc
- fgetc
dev_langs: C++
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de0b211c15077f62ecd3af0f774125e91f53017a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc
Liest ein Zeichen aus einem Stream  
  
## <a name="syntax"></a>Syntax  
  
```  
int fgetc(   
   FILE *stream   
);  
wint_t fgetwc(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `fgetc` gibt das gelesene Zeichen als `int` zurück oder gibt `EOF` zurück, um einen Fehler oder ein Dateiende anzugeben. `fgetwc` gibt das dem gelesenen Zeichen entsprechende Breitzeichen [wint_t](../../c-runtime-library/standard-types.md) zurück oder gibt `WEOF` zurück, um einen Fehler oder ein Dateiende anzugeben. Verwenden Sie für beide Funktionen `feof` oder `ferror`, um zwischen einem Fehler und einer Dateiendebedingung zu unterscheiden. Wenn ein Lesefehler auftritt, wird der Fehlerindikator für den Stream festgelegt. Wenn `stream` `NULL` ist, rufen `fgetc` und `fgetwc` den ungültigen Parameterhandler wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben auf. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EOF` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen liest ein einzelnes Zeichen aus der aktuellen Position der `stream` zugeordneten Datei. Die Funktion erhöht dann den zugeordneten Dateizeiger (sofern definiert), um auf das nächste Zeichen zu zeigen. Wenn der Stream am Dateiende ist, wird der Dateiende-Indikator für den Stream festgelegt.  
  
 `fgetc` entspricht `getc`, wird jedoch ausschließlich als Funktion, und nicht als Funktion und Makro implementiert.  
  
 `fgetwc` ist das Breitzeichen von `fgetc`. Es liest `c` als Multibytezeichen oder Breitzeichen, je nachdem, ob `stream` im Textmodus oder im Binärdateimodus geöffnet ist.  
  
 Die Versionen mit dem `_nolock`-Suffix sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt.  
  
 Weitere Informationen zur Verarbeitung von Breitzeichen und Multibytezeichen im Text- und Binärmodus finden Sie unter [Unicodestream-E/A im Text- und Binärmodus](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fgettc`|`fgetc`|`fgetc`|`fgetwc`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fgetc`|\<stdio.h>|  
|`fgetwc`|\<stdio.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_fgetc.c  
// This program uses getc to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   char buffer[81];  
   int  i, ch;  
  
   // Open file to read line from:  
   fopen_s( &stream, "crt_fgetc.txt", "r" );  
   if( stream == NULL )  
      exit( 0 );  
  
   // Read in first 80 characters and place them in "buffer":   
   ch = fgetc( stream );  
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = fgetc( stream );  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfgetctxt"></a>Eingabe: crt_fgetc.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [E/A-Stream](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)