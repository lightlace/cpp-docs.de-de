---
title: Compilerwarnung (Stufe 4) C4062
ms.date: 04/05/2019
f1_keywords:
- C4062
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
ms.openlocfilehash: 79658afc31565b708cdbd8a88f49b887cdd10cf3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59237184"
---
# <a name="compiler-warning-level-4-c4062"></a>Compilerwarnung (Stufe 4) C4062

> Enumerator '*Bezeichner*"im Schalter der Enumeration'*Enumeration*" wird nicht verarbeitet

Der Enumerator *Bezeichner* verfügt über kein zugeordnetes `case` Ereignishandler in einem `switch` -Anweisung, und es gibt keine `default` Bezeichnung, die abgefangen werden kann. Die fehlende Case-Anweisung ist möglicherweise ein Flüchtigkeitsfehler, und es ist ein potenzieller Fehler in Ihrem Code. Für eine verwandte Warnung für nicht verwendete Enumeratoren in `switch` -Anweisungen, die über eine `default` Groß-/Kleinschreibung, finden Sie unter [C4061](compiler-warning-level-4-c4061.md).

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen dazu, wie Sie Warnungen zu aktivieren, die standardmäßig deaktiviert sind, finden Sie unter [Compiler Warnungen, die standardmäßig deaktivierte](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4062 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4062.cpp
// compile with: /EHsc /W4
#pragma warning(default : 4062)
enum E { a, b, c };
void func ( E e ) {
   switch(e) {
      case a:
      case b:
   // case c:  // to fix, uncomment this line
      break;   // no default label
   }   // C4062, enumerator 'c' not handled
}

int main() {
}
```

## <a name="see-also"></a>Siehe auch

[Compilerwarnung (Ebene 4) C4061](compiler-warning-level-4-c4061.md)
