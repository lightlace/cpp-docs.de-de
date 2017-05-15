---
title: _putw| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putw
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
- _putw
- putw
dev_langs:
- C++
helpviewer_keywords:
- integers, writing to streams
- putw function
- streams, writing integers to
- _putw function
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
caps.latest.revision: 14
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
ms.openlocfilehash: 5e6cb1b57135502d7e75df7d0db7cb363a1fe003
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="putw"></a>_putw
Schreibt eine ganze Zahl in einen Stream.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _putw(  
   int binint,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *binint*  
 Binäre Ganzzahl wird ausgegeben.  
  
 `stream`  
 Zeiger auf die **FILE**-Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den geschriebenen Wert zurück. Ein Rückgabewert von `EOF` könnte einen Fehler anzeigen. Da `EOF` auch ein legitimer Ganzzahlwert ist, sollten Sie `ferror` verwenden, um Fehler zu überprüfen. Wenn `stream` ein NULL-Zeiger ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EOF` zurück.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_putw`-Funktion schreibt einen binären Wert vom Typ `int` an der aktuellen Position des *Stream.* `_putw` beeinflusst die Elementausrichtungen im Stream nicht und geht auch nicht von speziellen Ausrichtungen aus. `_putw` ist in erster Linie für die Kompatibilität mit früheren Bibliotheken verantwortlich. Portabilitätsprobleme können mit `_putw` auftreten, da die Größe von `int` und die Anordnung der Bytes in `int` über Systeme hinweg unterschiedlich sind.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_putw`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_putw.c  
/* This program uses _putw to write a  
 * word to a stream, then performs an error check.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   unsigned u;  
   if( fopen_s( &stream, "data.out", "wb" ) )  
      exit( 1 );  
   for( u = 0; u < 10; u++ )  
   {  
      _putw( u + 0x2132, stream );   /* Write word to stream. */  
      if( ferror( stream ) )         /* Make error check. */  
      {  
         printf( "_putw failed" );  
         clearerr_s( stream );  
         exit( 1 );  
      }  
   }  
   printf( "Wrote ten words\n" );  
   fclose( stream );  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
Wrote ten words  
```  
  
## <a name="see-also"></a>Siehe auch  
 [E/A-Stream](../../c-runtime-library/stream-i-o.md)   
 [_getw](../../c-runtime-library/reference/getw.md)
