---
title: feof | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: feof
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
f1_keywords: feof
dev_langs: C++
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef20a9653263a87e0818450b1d6d0b1241f91b8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="feof"></a>feof
Test für das Dateiende (End-of-File) in einem Stream.  
  
## <a name="syntax"></a>Syntax  
  
```  
int feof(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Die `feof`-Funktion gibt einen Wert ungleich null zurück, wenn bei einem Lesevorgang versucht wurde, über das Ende der Datei hinaus zu lesen; andernfalls wird 0 zurückgegeben. Wenn der Streamzeiger `NULL` ist, ruft die Funktion den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt, und `feof` gibt 0 zurück.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `feof`-Routine (die sowohl als Funktion als auch als Makro implementiert ist) bestimmt, ob das Ende von `stream` überschritten wurde. Wenn das Dateiende überschritten wird, wird von Lesevorgängen ein Indikator des Dateiendes zurückgegeben, bis der Stream geschlossen wird, oder bis `rewind`, `fsetpos`, `fseek` oder `clearerr` dagegen aufgerufen wird.  
  
 Wenn eine Datei z.B. 10 Bytes enthält, und Sie 10 Bytes aus der Datei lesen, wird `feof` 0 zurückgeben, da Sie nicht versucht haben, über das Ende hinaus zu lesen, obwohl sich der Dateizeiger am Ende der Datei befindet. Nur wenn Sie versuchen, ein elftes Byte zu lesen, wird von `feof` ein Wert ungleich null zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`feof`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_feof.c  
// This program uses feof to indicate when  
// it reaches the end of the file CRT_FEOF.TXT. It also  
// checks for errors with ferror.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int  count, total = 0;  
   char buffer[100];  
   FILE *stream;  
  
   fopen_s( &stream, "crt_feof.txt", "r" );  
   if( stream == NULL )  
      exit( 1 );  
  
   // Cycle until end of file reached:  
   while( !feof( stream ) )  
   {  
      // Attempt to read in 100 bytes:  
      count = fread( buffer, sizeof( char ), 100, stream );  
      if( ferror( stream ) )      {  
         perror( "Read error" );  
         break;  
      }  
  
      // Total up actual bytes read  
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfeoftxt"></a>Eingabe: crt_feof.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
Number of bytes read = 19  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Error Handling (Fehlerbehandlung)](../../c-runtime-library/error-handling-crt.md)   
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)