---
title: imaxdiv | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: imaxdiv
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: imaxdiv
dev_langs: C++
helpviewer_keywords: imaxdiv function
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65c7b71030bff65a2806d20690554a9828871268
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="imaxdiv"></a>imaxdiv
Berechnet den Quotienten und den Rest von zwei ganzzahligen Werten beliebiger Größe als einzelnen Vorgang.  
  
## <a name="syntax"></a>Syntax  
  
```  
imaxdiv_t imaxdiv(   
   intmax_t numer,  
   intmax_t denom   
);   
```  
  
#### <a name="parameters"></a>Parameter  
 `numer`  
 Der Zähler.  
  
 `denom`  
 Der Nenner.  
  
## <a name="return-value"></a>Rückgabewert  
 `imaxdiv`, welches mithilfe von Argumenten des Typs [intmax_t](../../c-runtime-library/standard-types.md) aufgerufen wurde, gibt eine Struktur des Typs [imaxdiv_t](../../c-runtime-library/standard-types.md) zurück, die den Quotienten und den Rest enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `imaxdiv`-Funktion teilt `numer` durch `denom` und berechnet dadurch den Quotienten und den Rest. Die `imaxdiv_t` -Struktur enthält den Quotienten `intmax_t quot` und den Rest `intmax_t rem`. Das Zeichen des Quotienten entspricht dem Zeichen des mathematischen Quotienten. Der absolute Wert ist die größte ganze Zahl, die kleiner ist als der absolute Wert des mathematischen Quotienten. Wenn der Nenner 0 ist, wird das Programm mit einer Fehlermeldung beendet.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`imaxdiv`|\<inttypes.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_imaxdiv.c  
// Build using: cl /W3 /Tc crt_imaxdiv.c  
// This example takes two integers as command-line  
// arguments and calls imaxdiv to divide the first   
// argument by the second, then displays the results.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <inttypes.h>  
  
int main(int argc, char *argv[])  
{  
   intmax_t x,y;  
   imaxdiv_t div_result;  
  
   x = atoll(argv[1]);  
   y = atoll(argv[2]);  
  
   printf("The call to imaxdiv(%lld, %lld)\n", x, y);  
   div_result = imaxdiv(x, y);  
   printf("results in a quotient of %lld, and a remainder of %lld\n\n",  
          div_result.quot, div_result.rem);  
}  
```  
  
 Wenn der Code mit den Befehlszeilenparametern von `9460730470000000 8766` erstellt und anschließend aufgerufen wird, wird diese Ausgabe generiert:  
  
```Output  
The call to imaxdiv(9460730470000000, 8766)  
results in a quotient of 1079252848505, and a remainder of 5170  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)