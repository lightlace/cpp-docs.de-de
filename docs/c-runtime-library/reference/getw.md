---
title: _getw | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _getw
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
f1_keywords: _getw
dev_langs: C++
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8850bd13d8aa1ed0412ae93843784cb560be4a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="getw"></a>_getw
Ruft eine Ganzzahl aus einem Stream ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _getw(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger auf die `FILE`-Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `_getw` gibt den gelesenen Wert in Form einer ganzen Zahl zurück. Ein Rückgabewert von `EOF` gibt einen Fehler oder ein Dateiende an. Da der `EOF`-Wert jedoch auch ein legitimer Wert einer Ganzzahl ist, verwenden Sie `feof` oder `ferror`, um eine Dateiendebedingung oder eine Fehlerbedingung zu prüfen. Wenn `stream` `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `EOF` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_getw`-Funktion liest den nächsten Binärwert des Typs `int` aus der Datei, die `stream` zugeordnet ist, und erhöht den zugeordneten Dateizeiger (sofern vorhanden), um zum nächsten ungelesenen Zeichen zu zeigen. `_getw` geht nicht von allen speziellen Elementausrichtungen im Stream aus. Probleme beim Portieren können mit `_getw` auftreten, da die Größe des `int`-Typs und die Anordnung der Bytes im `int`-Typ über Systeme hinweg unterschiedlich sind.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_getw`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_getw.c  
// This program uses _getw to read a word  
// from a stream, then performs an error check.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   int i;  
  
   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )  
      printf( "Couldn't open file\n" );  
   else  
   {  
      // Read a word from the stream:  
      i = _getw( stream );  
  
      // If there is an error...  
      if( ferror( stream ) )  
      {  
         printf( "_getw failed\n" );  
         clearerr_s( stream );  
      }  
      else  
         printf( "First data word in file: 0x%.4x\n", i );  
      fclose( stream );  
   }  
}  
```  
  
## <a name="input-crtgetwtxt"></a>Eingabe: crt_getw.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
First data word in file: 0x656e694c  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_putw](../../c-runtime-library/reference/putw.md)