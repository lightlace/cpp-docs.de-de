---
title: _cabs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 345130fe72b7dd1ee416209c5702d877a036561c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="cabs"></a>_cabs

Berechnet den absoluten Wert einer komplexen Zahl.

## <a name="syntax"></a>Syntax

```C
double _cabs(
   struct _complex z
);
```

### <a name="parameters"></a>Parameter

*z*<br/>
Komplexe Zahl.

## <a name="return-value"></a>Rückgabewert

**_cabs** gibt im Erfolgsfall den absoluten Wert des Arguments zurück. Bei einem Überlauf **_cabs** gibt **HUGE_VAL** und legt **Errno** auf **ERANGE**. Sie können die Fehlerbehandlung mit [_matherr](matherr.md) ändern.

## <a name="remarks"></a>Hinweise

Die **_cabs** -Funktion berechnet den absoluten Wert einer komplexen Zahl, die eine Struktur des Typs sein muss [_complex](../../c-runtime-library/standard-types.md). Die Struktur *z* besteht aus einer reellen Komponente *x* und einer imaginären Komponente *y*. Ein Aufruf von **_cabs** erzeugt den Wert des Ausdrucks gleich `sqrt( z.x * z.x + z.y * z.y )`.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_cabs**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_cabs.c
// Using _cabs, this program calculates
// the absolute value of a complex number.

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

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)   