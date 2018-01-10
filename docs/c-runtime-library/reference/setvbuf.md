---
title: setvbuf | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: setvbuf
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
f1_keywords: setvbuf
dev_langs: C++
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0855982627c60c51ec5753031ae932ffd430f024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setvbuf"></a>setvbuf
Steuert die Streampufferung und die Puffergröße.  
  
## <a name="syntax"></a>Syntax  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
 `buffer`  
 Vom Benutzer zugewiesener Puffer.  
  
 `mode`  
 Pufferungsmodus.  
  
 `size`  
 Puffergröße in Bytes. Zulässiger Bereich: 2 <= `size` <= INT_MAX (2147483647). Der für `size` angegebene Wert wird intern auf das nächste Vielfache von 2 abgerundet.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg 0 zurück.  
  
 Wenn `stream` `NULL` ist oder `mode` oder `size` nicht aus einem gültigen Bereich stammt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die Ausführung weiterhin zugelassen wird, gibt diese Funktion -1 zurück und legt `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `setvbuf`-Funktion ermöglicht dem Programm, die Pufferung und die Puffergröße für `stream` zu steuern. `stream` muss auf eine geöffnete Datei verweisen, die keinen E/A-Vorgang durchlaufen hat, seitdem sie geöffnet wurde. Das Array, auf das `buffer` zeigt, wird als Puffer verwendet, es sei denn, es ist `NULL`. In diesem Fall verwendet `setvbuf` einen automatisch zugewiesenen Puffer mit der Länge `size`/2 * 2 Bytes.  
  
 Der Modus muss `_IOFBF`, `_IOLBF` oder `_IONBF` sein. Wenn `mode` `_IOFBF` oder `_IOLBF`ist, wird `size` als die Größe des Puffers verwendet. Wenn `mode` `_IONBF` ist, wird die Pufferung des Datenstroms aufgehoben, und `size` und `buffer` werden ignoriert. Werte für `mode` und ihre Bedeutung sind:  
  
 `_IOFBF`  
 Vollständige Pufferung; d.h. `buffer` dient als Puffer und `size` wird als die Größe des Puffers verwendet. Wenn `buffer` `NULL` ist, wird ein automatisch zugewiesener Puffer, der `size` Bytes lang ist, verwendet.  
  
 `_IOLBF`  
 Für einige Systeme bietet dies Zeilenpufferung. Für Win32 ist das Verhalten jedoch mit `_IOFBF` – Vollständige Pufferung identisch.  
  
 `_IONBF`  
 Kein Puffer wird verwendet, unabhängig von `buffer` oder `size`.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`setvbuf`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
'stream1' now has a buffer of 1024 bytes  
'stream2' now has no buffer  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)