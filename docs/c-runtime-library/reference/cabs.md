---
title: _cabs | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _cabs
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- cabsl
- _cabs
- _cabsl
dev_langs:
- C++
helpviewer_keywords:
- cabs function
- cabsl function
- absolute values
- _cabsl function
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
caps.latest.revision: 13
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
ms.openlocfilehash: 930ef18229737fee03d03308c45f5ffb3615cdcd
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="cabs"></a>_cabs
Berechnet den absoluten Wert einer komplexen Zahl.  
  
## <a name="syntax"></a>Syntax  
  
```  
double _cabs(   
   struct _complex z   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `z`  
 Komplexe Zahl.  
  
## <a name="return-value"></a>Rückgabewert  
 `_cabs` gibt im Erfolgsfall den absoluten Wert seines Arguments zurück. Bei einem Überlauf gibt `_cabs` `HUGE_VAL` aus und setzt `errno` auf `ERANGE`. Sie können die Fehlerbehandlung mit [_matherr](../../c-runtime-library/reference/matherr.md) ändern.  
  
## <a name="remarks"></a>Hinweise  
 Die `_cabs`-Funktion berechnet den absoluten Wert einer komplexen Zahl, die eine Struktur des Typs [_complex](../../c-runtime-library/standard-types.md) aufweisen muss. Die Struktur `z` besteht aus einer reellen Komponente `x` und einer imaginären Komponente `y`. Ein Aufruf von `_cabs` erzeugt den Wert des Ausdrucks gleich `sqrt( z.x * z.x + z.y * z.y )`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_cabs`|\<math.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_cabs.c  
/* Using _cabs, this program calculates  
 * the absolute value of a complex number.  
 */  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct _complex number = { 3.0, 4.0 };  
   double d;  
  
   d = _cabs( number );  
   printf( "The absolute value of %f + %fi is %f\n",  
           number.x, number.y, d );  
}  
```  
  
```Output  
The absolute value of 3.000000 + 4.000000i is 5.000000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [abs, labs, llabs, _abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
