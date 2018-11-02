---
title: __min
ms.date: 04/05/2018
apiname:
- __min
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
apitype: DLLExport
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
ms.openlocfilehash: f9e867cd1f3e3519e440c91895e61e317d9688a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617814"
---
# <a name="min"></a>__min

Ein Präprozessormakro, die die kleinere von zwei Werten zurückgibt.

## <a name="syntax"></a>Syntax

```C
#define __min(a,b) (((a) < (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parameter

*eine*, *b*<br/>
Geben Sie Werte bei, die die **<** Operator funktioniert.

## <a name="return-value"></a>Rückgabewert

Das kleinere der beiden Argumente.

## <a name="remarks"></a>Hinweise

Die **__min** -Makro vergleicht zwei Werte und gibt den Wert des kleineren zurück. Die Argumente können von einen beliebigen Datentyp stammen, signed oder unsigned. Beide Argumente sowie der Rückgabewert müssen demselben Datentyp entsprechen.

Das Argument, das zurückgegeben wird durch das Makro zweimal ausgewertet. Dies kann zu unerwarteten Ergebnissen führen, wenn das Argument einen Ausdruck, der seinen Wert ändert, wenn er, wie z. B. ausgewertet wird `*p++`.

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
