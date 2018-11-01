---
title: function (C/C++)
ms.date: 11/04/2016
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
ms.openlocfilehash: 1c8c250e3ea28d56aec837f5c3353c3bb6515442
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611457"
---
# <a name="function-cc"></a>function (C/C++)
Gibt an, dass Funktionsaufrufe generiert werden, die in der Argumentliste des Pragmas angegeben sind.

## <a name="syntax"></a>Syntax

```
#pragma function( function1 [, function2, ...] )
```

## <a name="remarks"></a>Hinweise

Bei Verwendung der `intrinsic` Pragma (oder/Oi) um den Compiler anweisen, intrinsische Funktionen generieren (intrinsische Funktionen werden als Inlinecode und nicht als Funktionsaufrufe generiert), können Sie die **Funktion** Pragma, um explizit zu erzwingen einer Funktionsaufruf. Sobald ein function-Pragma angezeigt wird, tritt es mit der ersten Funktionsdefinition in Kraft, die eine bestimmte intrinsische Funktion enthält. Die Wirkung dauert bis an das Ende der Quelldatei oder bis zum Auftreten einer `intrinsic` Pragmas, die gleiche intrinsische Funktion angibt. Die **Funktion** Pragma kann nur außerhalb einer Funktion verwendet werden – auf globaler Ebene.

Die Funktionen mit systeminternen Formen finden Sie unter [#pragma intrinsic](../preprocessor/intrinsic.md).

## <a name="example"></a>Beispiel

```cpp
// pragma_directive_function.cpp
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// use intrinsic forms of memset and strlen
#pragma intrinsic(memset, strlen)

// Find first word break in string, and set remaining
// chars in string to specified char value.
char *set_str_after_word(char *string, char ch) {
   int i;
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */

   for(i = 0; i < len; i++) {
      if (isspace(*(string + i)))
         break;
   }

   for(; i < len; i++)
      *(string + i) = ch;

   return string;
}

// do not use strlen intrinsic
#pragma function(strlen)

// Set all chars in string to specified char value.
char *set_str(char *string, char ch) {
   // Uses intrinsic for memset, but calls strlen library function
   return (char *) memset(string, ch, strlen(string));
}

int main() {
   char *str = (char *) malloc(20 * sizeof(char));

   strcpy_s(str, sizeof("Now is the time"), "Now is the time");
   printf("str is '%s'\n", set_str_after_word(str, '*'));
   printf("str is '%s'\n", set_str(str, '!'));
}
```

```Output
str is 'Now************'
str is '!!!!!!!!!!!!!!!'
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)