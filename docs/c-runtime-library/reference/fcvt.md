---
title: _fcvt | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fcvt
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
- _fcvt
dev_langs:
- C++
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
caps.latest.revision: 24
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
ms.openlocfilehash: 0e2bad41f044046fd0f75a30989c1f39adb69560
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="fcvt"></a>_fcvt
Konvertiert eine Gleitkommazahl in eine Zeichenfolge. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_fcvt(   
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
 Anzahl der Ziffern nach dem Dezimaltrennzeichen.  
  
 `dec`  
 Zeiger auf die gespeicherte Position der Dezimalstelle.  
  
 `sign`  
 Zeiger auf den gespeicherten Zeichen-Indikator.  
  
## <a name="return-value"></a>Rückgabewert  
 `_fcvt` gibt einen Zeiger zur Zeichenfolge der Ziffern, und bei Fehler NULL zurück.  
  
## <a name="remarks"></a>Hinweise  
 Mit der `_fcvt`-Funktion werden Gleitkommazahlen in mit NULL endende Zeichenfolgen konvertiert. Der Parameter `value` ist die zu konvertierende Gleitkommazahl. `_fcvt` speichert die Ziffern von `value` als Zeichenfolge, und fügt das Zeichen NULL ('\0') an. Der `count`-Parameter gibt die Anzahl der zu speichernden Ziffern nach dem Dezimaltrennzeichen an. Überschüssige Ziffern werden auf `count` Stellen gerundet. Wenn weniger als `count` Dezimalstellen vorhanden sind, wird die Zeichenfolge mit Nullen aufgefüllt.  
  
 Die Gesamtanzahl der von `_fcvt` zurückgegebenen Ziffern ist nicht größer als `_CVTBUFSIZE`.  
  
 In der Zeichenfolge werden nur Ziffern gespeichert. Die Position der Dezimalstelle und das Vorzeichen von `value` können nach dem Aufruf aus `dec` abgerufen und signiert werden. Der Parameter `dec` zeigt auf einen ganzzahligen Wert; dieser ganzzahlige Wert gibt die Position der Dezimalstelle im Verhältnis zum Anfang der Zeichenfolge an. Der Wert null oder ein negativer ganzzahliger Wert geben an, dass sich die Dezimalstelle links neben der ersten Ziffer befindet. Der Parameter `sign` verweist auf eine ganze Zahl, die das Vorzeichen von `value` angibt. Die ganze Zahl ist auf 0 festgelegt, wenn `value` positiv ist, und ist auf eine Zahl ungleich null festgelegt, wenn `value` negativ ist.  
  
 `_ecvt` und `_fcvt` unterscheiden sich hinsichtlich der Interpretation des Parameters `count`. Von `_ecvt` wird `count` als die Gesamtanzahl der Ziffern in der Ausgabezeichenfolge interpretiert, während `count` von `_fcvt` als die Anzahl der Ziffern nach der Dezimalstelle interpretiert wird.  
  
 Für die Konvertierung wird von `_ecvt` und `_fcvt` ein einzelner, statisch zugewiesener Puffer verwendet. Jeder Aufruf einer dieser Routinen zerstört das Ergebnis des vorherigen Aufrufs.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `dec` oder `sign` NULL oder `count` 0 ist, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt, und NULL zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fcvt`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_fcvt.c  
// compile with: /W3  
// This program converts the constant  
// 3.1415926535 to a string and sets the pointer  
// buffer to point to that string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  decimal, sign;  
   char *buffer;  
   double source = 3.1415926535;  
  
   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996  
   // Note: _fcvt is deprecated; consider using _fcvt_s instead  
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",  
            source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)
