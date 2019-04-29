---
title: deprecated (C/C++)
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 262b23e6e4813a5e22bc3f4e7c9a18efb9988a7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389293"
---
# <a name="deprecated-cc"></a>deprecated (C/C++)

Die **veraltet** Pragma ermöglicht es Ihnen anzugeben, dass eine Funktion, Typ oder einen anderen Bezeichner in einer zukünftigen nicht mehr unterstützt werden möglicherweise freigegeben oder nicht mehr verwendet werden soll.

> [!NOTE]
> Informationen zu den C ++ 14 `[[deprecated]]` -Attribut, und eine Anleitung für verwendet werden soll, wenn Vs Attribut, das "Microsoft" declspec "oder" Pragma, finden Sie unter [Standard C++-Attribute](../cpp/attributes.md) Attribut.

## <a name="syntax"></a>Syntax

```
#pragma deprecated( identifier1 [,identifier2, ...] )
```

## <a name="remarks"></a>Hinweise

Wenn der Compiler findet einen Bezeichner, die gemäß einer **veraltet** Pragma ausgestellten compilerwarnung [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).

Sie können Makronamen als veraltet deklarieren. Platzieren Sie den Makronamen in Anführungszeichen; andernfalls tritt eine Makroerweiterung auf.

Da die **veraltet** Pragma auf alle übereinstimmenden IDs funktioniert und werden nicht berücksichtigt Signaturen, nicht die beste Option für bestimmte Versionen von überladenen Funktionen als veraltet markiert. Jeder entsprechenden Funktionsnamen, der in den Gültigkeitsbereich eingebunden ist, wird die Warnung ausgelöst.

Es wird empfohlen, die C ++ 14 `[[deprecated]]` Attribut, wenn möglich, anstatt die **veraltet** Pragma. Der Microsoft-spezifische [__declspec(deprecated)](../cpp/deprecated-cpp.md) deklarationsmodifizierer ist die bessere Wahl in vielen Fällen als auch die **veraltet** Pragma. Die `[[deprecated]]` Attribut und `__declspec(deprecated)` Modifizierer ermöglichen es Ihnen, den veralteten Zustand von bestimmten Formen überladener Funktionen angeben. Die Diagnose Warnung nur für Verweise auf die bestimmten überladenen Funktion wird das Attribut angezeigt oder Modifizierer gilt.

## <a name="example"></a>Beispiel

```cpp
// pragma_directive_deprecated.cpp
// compile with: /W3
#include <stdio.h>
void func1(void) {
}

void func2(void) {
}

int main() {
   func1();
   func2();
   #pragma deprecated(func1, func2)
   func1();   // C4995
   func2();   // C4995
}
```

Das folgende Beispiel zeigt, wie Sie eine Klasse als veraltet deklarieren:

```cpp
// pragma_directive_deprecated2.cpp
// compile with: /W3
#pragma deprecated(X)
class X {  // C4995
public:
   void f(){}
};

int main() {
   X x;   // C4995
}
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)