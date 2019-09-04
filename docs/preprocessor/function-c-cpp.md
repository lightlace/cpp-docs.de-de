---
title: function-Pragma
ms.date: 08/29/2019
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
ms.openlocfilehash: f99f3c878789a6c47fdb0d48e0a8690d65fa8062
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220141"
---
# <a name="function-pragma"></a>function-Pragma

Weist den Compiler an, Aufrufe an Funktionen zu generieren, die in der Argumentliste des Pragmas angegeben sind, anstatt Sie zu Inlining.

## <a name="syntax"></a>Syntax

> **#pragma-Funktion (** *Funktion1* [ **,** *Funktion2* ...] **)**

## <a name="remarks"></a>Hinweise

Intrinsische Funktionen werden normalerweise als Inline Code und nicht als Funktionsaufrufe generiert. Wenn Sie das [intrinsische Pragma](intrinsic.md) oder die [/Oi](../build/reference/oi-generate-intrinsic-functions.md) -Compileroption verwenden, um dem Compiler mitzuteilen, dass intrinsische Funktionen generiert werden, können Sie das funktionspragma verwenden, um einen Funktions aufrufexplizit zu erzwingen. Sobald ein funktionspragma angezeigt wird, tritt es in der ersten Funktionsdefinition in Kraft, die eine angegebene intrinsische Funktion enthält. Der Effekt wird bis zum Ende der Quelldatei oder bis zum Aussehen eines `intrinsic` Pragmas fortgesetzt, das die gleiche intrinsische Funktion angibt. Sie können das **Function** -Pragma nur auf globaler Ebene außerhalb einer Funktion verwenden.

Listen der Funktionen, die über intrinsische Formulare verfügen, finden Sie unter System internes [pragma](intrinsic.md).

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
