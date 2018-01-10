---
title: _gcvt | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _gcvt
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords: _gcvt
dev_langs: C++
helpviewer_keywords:
- _gcvt function
- _CVTBUFSIZE
- gcvt function
- floating-point functions, converting number to string
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22561495a972c7561f827c4b7f445bb3fa5c256f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="gcvt"></a>_gcvt
Konvertiert einen Gleitkommawert in eine Zeichenfolge, die in einem Puffer gespeichert wird. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_gcvt(   
   double value,  
   int digits,  
   char *buffer   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `value`  
 Zu konvertierender Wert.  
  
 `digits`  
 Anzahl der gespeicherten signifikanten Ziffern.  
  
 `buffer`  
 Speicherort für das Ergebnis.  
  
## <a name="return-value"></a>Rückgabewert  
 `_gcvt` gibt einen Zeiger zur Zeichenfolge der Ziffern zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_gcvt` Funktion konvertiert ein Gleitkomma `value` in eine Zeichenfolge (mit einem Dezimaltrennzeichen und ein mögliches Zeichen-Byte) und speichert die Zeichenfolge in `buffer`. Der `buffer` sollte groß genug für den konvertierten Wert und ein abschließendes Zeichen NULL sein, das automatisch angefügt wird. Wenn eine Puffergröße `digits` + 1 verwendet wird, überschreibt die Funktion das Pufferende. Dies geschieht, da die konvertierte Zeichenfolge ein Dezimaltrennzeichen enthält und Informationen über Zeichen und Exponenten enthalten kann. Es wird kein Überlauf bereitgestellt. `_gcvt` versucht `digits`-Ziffern im Dezimalformat zu erzeugen. Wenn es nicht möglich ist, erzeugt es `digits`-Ziffern im Exponentialformat. Bei der Konvertierung können Nachstellen von Nullen unterdrückt werden.  
  
 Ein `buffer` der Länge `_CVTBUFSIZE` reicht für alle Gleitkommawerte aus.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `buffer` `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `NULL` zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_gcvt`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_gcvt.c  
// compile with: /W3  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   char buffer[_CVTBUFSIZE];  
   double value = -1234567890.123;  
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );  
   _gcvt( value, 12, buffer ); // C4996  
   // Note: _gcvt is deprecated; consider using _gcvt_s instead  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
  
   printf( "\n" );  
   value = -12.34567890123;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
}  
```  
  
```Output  
The following numbers were converted by _gcvt(value,12,buffer):  
buffer: '-1234567890.12' (14 chars)  
buffer: '-12345678901.2' (14 chars)  
buffer: '-123456789012' (13 chars)  
buffer: '-1.23456789012e+012' (19 chars)  
  
buffer: '-12.3456789012' (14 chars)  
buffer: '-1.23456789012' (14 chars)  
buffer: '-0.123456789012' (15 chars)  
buffer: '-1.23456789012e-002' (19 chars)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)