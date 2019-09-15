---
title: __min
ms.date: 04/05/2018
api_name:
- __min
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __min
- min
- _min
helpviewer_keywords:
- __min macro
- min macro
- minimum macro
- _min macro
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
ms.openlocfilehash: 6b5cc6517c125f91337ca0d9b12b7a49bd7c1753
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951738"
---
# <a name="__min"></a>__min

Ein Präprozessormakro, das den kleineren von zwei-Werten zurückgibt.

## <a name="syntax"></a>Syntax

```C
#define __min(a,b) (((a) < (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parameter

*a*, *b*<br/>
Werte eines beliebigen Typs, mit **<** dem der Operator arbeitet.

## <a name="return-value"></a>Rückgabewert

Das kleinere der beiden Argumente.

## <a name="remarks"></a>Hinweise

Das **__min** -Makro vergleicht zwei Werte und gibt den Wert der kleineren Werte zurück. Die Argumente können von einen beliebigen Datentyp stammen, signed oder unsigned. Beide Argumente sowie der Rückgabewert müssen demselben Datentyp entsprechen.

Das zurückgegebene Argument wird zweimal durch das Makro ausgewertet. Dies kann zu unerwarteten Ergebnissen führen, wenn das Argument ein Ausdruck ist, der seinen Wert bei der Auswertung ändert, z `*p++`. b.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**__min**|\<stdlib.h>|

## <a name="example"></a>Beispiel

```C
// crt_minmax.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int a = 10;
   int b = 21;

   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );
}
```

```Output
The larger of 10 and 21 is 21
The smaller of 10 and 21 is 10
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[__max](max.md)<br/>
