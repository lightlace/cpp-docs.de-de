---
title: _ecvt | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ecvt
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
f1_keywords:
- _ecvt
dev_langs:
- C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee37eb3623f27f4fb6883b2d16fc4c21c2a960c1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="ecvt"></a>_ecvt
Konvertiert eine `double`-Zahl in eine Zeichenfolge. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_ecvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `value`  
 Zu konvertierende Zahl.  
  
 `count`  
 Anzahl der gespeicherten Ziffern.  
  
 `dec`  
 Gespeicherte Position der Dezimalstelle.  
  
 `sign`  
 Vorzeichen der konvertierten Zahl.  
  
## <a name="return-value"></a>Rückgabewert  
 `_ecvt` gibt einen Zeiger auf die Ziffernfolge zurück; NULL, wenn ein Fehler aufgetreten ist.  
  
## <a name="remarks"></a>Hinweise  
 Mit der `_ecvt`-Funktion werden Gleitkommazahlen in Zeichenfolgen konvertiert. Der Parameter `value` ist die zu konvertierende Gleitkommazahl. Mit dieser Funktion werden bis zu `count` Ziffern von `value` als Zeichenfolge gespeichert und das Zeichen NULL ('\0') angefügt. Wenn in `value` mehr als `count` Zeichen vorhanden sind, wird die untere Ziffer gerundet. Wenn weniger als `count` Ziffern vorhanden sind, wird die Zeichenfolge mit Nullen aufgefüllt.  
  
 Die Gesamtanzahl der von `_ecvt` zurückgegebenen Ziffern ist nicht größer als `_CVTBUFSIZE`.  
  
 In der Zeichenfolge werden nur Ziffern gespeichert. Die Position der Dezimalstelle und das Vorzeichen von `value` können nach dem Aufruf aus `dec` und `sign` abgerufen werden. Der Parameter `dec` zeigt auf einen Integer-Wert, der die Position der Dezimalstelle im Verhältnis zum Zeichenfolgenanfang angibt. Der Wert 0 oder ein negativer Integer-Wert geben an, dass sich die Dezimalstelle links neben der ersten Ziffer befindet. Der Parameter `sign` zeigt auf einn Integer-Wert, der das Vorzeichen der konvertierten Zahl angibt. Wenn der Integer-Wert 0 ist, ist die Zahl positiv. Andernfalls ist die Zahl negativ.  
  
 `_ecvt` und `_fcvt` unterscheiden sich hinsichtlich der Interpretation des Parameters `count`. Von `_ecvt` wird `count` als die Gesamtanzahl der Ziffern in der Ausgabezeichenfolge interpretiert, während `count` von `_fcvt` als die Anzahl der Ziffern nach der Dezimalstelle interpretiert wird.  
  
 Für die Konvertierung wird von `_ecvt` und `_fcvt` ein einzelner, statisch zugewiesener Puffer verwendet. Bei jedem Aufruf dieser Routinen wird das Ergebnis des vorherigen Aufrufs zerstört.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `dec` oder `sign` NULL oder `count` 0 ist, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt, und NULL zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_ecvt`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)