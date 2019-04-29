---
title: _STATIC_ASSERT-Makro
ms.date: 11/04/2016
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
- _STATIC_ASSERT
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
ms.openlocfilehash: 5d3aa1d9665b48a0690d8eb62353fc98c5a550f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354692"
---
# <a name="staticassert-macro"></a>_STATIC_ASSERT-Makro

Auswerten eines Ausdrucks zur Kompilierzeit und ein Fehler generiert, wenn das Ergebnis ist **"false"**.

## <a name="syntax"></a>Syntax

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>Parameter

*booleanExpression*<br/>
Ausdruck (einschließlich Zeiger), der zu ungleich null ergibt (**"true"**) oder 0 (**"false"**).

## <a name="remarks"></a>Hinweise

Dieses Makro ähnelt den [_ASSERT "und" _ASSERTE-Makros](assert-asserte-assert-expr-macros.md), außer dass *boolescher Ausdruck* wird zur Kompilierzeit statt zur Laufzeit ausgewertet. Wenn *boolescher Ausdruck* ergibt **"false"** (0), [Compilerfehler C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) wird generiert.

## <a name="example"></a>Beispiel

In diesem Beispiel überprüfen wir, ob die ["sizeof"](../../c-language/sizeof-operator-c.md) ein **Int** ist größer als oder gleich 2 Bytes und gibt an, ob die ["sizeof"](../../c-language/sizeof-operator-c.md) eine **lange** 1 Byte. Das Programm wird nicht kompiliert und generiert [Compilerfehler C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) da eine **lange** ist größer als 1 Byte.

```C
// crt__static_assert.c

#include <crtdbg.h>
#include <stdio.h>

_STATIC_ASSERT(sizeof(int) >= 2);
_STATIC_ASSERT(sizeof(long) == 1);  // C2466

int main()
{
    printf("I am sure that sizeof(int) will be >= 2: %d\n",
        sizeof(int));
    printf("I am not so sure that sizeof(long) == 1: %d\n",
        sizeof(long));
}
```

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-----------|---------------------|
|**_STATIC_ASSERT**|\<crtdbg.h>|

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Macros](assert-asserte-assert-expr-macros.md)<br/>
