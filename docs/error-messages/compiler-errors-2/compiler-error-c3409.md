---
title: Compilerfehler C3409 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3409
dev_langs:
- C++
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 338a98adb45ee9fc8eb392853a5693d10a171940
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058834"
---
# <a name="compiler-error-c3409"></a>Compilerfehler C3409

ein leerer Attributblock ist nicht zulässig.

Die eckigen Klammern wurden vom Compiler als interpretiert eine [Attribut](../../windows/cpp-attributes-reference.md) blockieren, aber keine Attribute gefunden wurden.

Der Compiler kann diesen Fehler generieren, bei der Verwendung von eckigen Klammern als Teil der Definition eines Lambda-Ausdrucks. Dieser Fehler tritt auf, wenn der Compiler nicht ermitteln kann, ob die eckigen Klammern Teil der Definition eines Lambda-Ausdrucks oder ein Attributblock sind. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../cpp/lambda-expressions-in-cpp.md).

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Wenn die eckigen Klammern ein Attributblock gehören:

   1. Geben Sie einen oder mehrere Attribute in dem Attributblock.

   1. Entfernen Sie den Attributblock.

1. Wenn die eckigen Klammern Teil eines Lambda-Ausdrucks sind:

   1. Stellen Sie sicher, dass der Lambda-Ausdruck gültiger Syntaxregeln befolgt.

         Weitere Informationen zu Lambda-Ausdruckssyntax, finden Sie unter [Lambda-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md).

    2.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3409 generiert.

```
// C3409.cpp
// compile with: /c
#include <windows.h>
[]   // C3409
class a {};

// OK
[object, uuid("00000000-0000-0000-0000-000000000000")]
__interface x {};

[coclass, uuid("00000000-0000-0000-0000-000000000001")]
class b : public x {};
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C3409 generiert, da ein Lambda-Ausdruck verwendet die `mutable` -Spezifikation, aber keine Parameterliste bereitstellt. Der Compiler kann nicht bestimmen, ob die eckigen Klammern Teil der Definition eines Lambda-Ausdrucks oder ein Attributblock sind.

```
// C3409b.cpp

int main()
{
   [] mutable {}();
}
```

## <a name="see-also"></a>Siehe auch

[Attribut](../../windows/cpp-attributes-reference.md)<br/>
[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)<br/>
[Lambdaausdruckssyntax](../../cpp/lambda-expression-syntax.md)