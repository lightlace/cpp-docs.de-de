---
title: clearerr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- clearerr
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
- clearerr
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 4f6f82645eba2fc2e1c78ba4dd88751943a62e76
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="clearerr"></a>clearerr
Setzt den Fehlerindikator für einen Stream zurück. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [clearerr_s](../../c-runtime-library/reference/clearerr-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
void clearerr(  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Die `clearerr`-Funktion setzt den Fehlerindikator und den Dateiende-Indikator für `stream` zurück. Fehlerindikatoren werden nicht automatisch gelöscht; sobald der Fehlerindikator für einen bestimmten Stream festgelegt wurde, geben Operationen in diesem Stream weiterhin einen Fehlerwert zurück, bis `clearerr`, `fseek`, `fsetpos` oder `rewind` aufgerufen wird.  
  
 Wenn `stream` `NULL` ist, wird der Handler für ungültige Parameter wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und kehrt dann zurück. Weitere Informationen über `errno` und andere Fehlercodes finden Sie unter [errno-Konstanten](../../c-runtime-library/errno-constants.md).  
  
 Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [clearerr_s](../../c-runtime-library/reference/clearerr-s.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`clearerr`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_clearerr.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      clearerr( stdin );  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      clearerr( stdin );  
   }  
   else  
      printf( "No read error\n" );  
}  
```  
  
```Output  
  
n  
  
```  
  
```Output  
  
      nWrite error: No error  
Will input cause an error? n  
No read error  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Error Handling (Fehlerbehandlung)](../../c-runtime-library/error-handling-crt.md)   
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)
