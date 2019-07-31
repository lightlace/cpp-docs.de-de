---
title: Partielle Reihenfolge von Funktionsvorlagen (C++)
ms.date: 07/30/2019
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
ms.openlocfilehash: 0c4f11b4b3e02504c4786ea34441362b542959d6
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682428"
---
# <a name="partial-ordering-of-function-templates-c"></a>Partielle Reihenfolge von Funktionsvorlagen (C++)

Es können mehrere Funktionsvorlagen, die der Argumentliste eines Funktionsaufrufs entsprechen, verfügbar sein. C++ definiert eine partielle Reihenfolge von Funktionsvorlagen, um anzugeben, welche Funktion aufgerufen werden soll. Die Reihenfolge ist partiell, da es mehrere Vorlagen geben kann, die als genauso spezialisiert betrachtet werden.

Der Compiler wählt die speziellste Vorlagenfunktion aus, die aus den möglichen Übereinstimmungen verfügbar ist. Wenn z. b. eine Funktions Vorlage einen Typ `T` annimmt und eine andere Funktions Vorlage `T*` verfügbar ist, wird `T*` die Version als spezialisiertere Version bezeichnet. Sie wird gegenüber der generischen `T` Version bevorzugt, wenn das Argument ein Zeigertyp ist, obwohl beide zulässige Übereinstimmungen sind.

Verwenden Sie folgenden Prozess, um zu ermitteln, ob ein Funktionsvorlagenkandidat spezialisierter ist:

1. Berücksichtigen Sie zwei Funktionsvorlagen, T1 und T2.

1. Ersetzen Sie die Parameter in T1 durch einen hypothetischen eindeutigen Typ X.

1. Überprüfen Sie mit der Parameterliste in T1, ob T2 eine gültige Vorlage für diese Parameterliste ist. Ignorieren Sie alle impliziten Konvertierungen.

1. Wiederholen Sie den gleichen Prozess umgekehrt mit T1 und T2.

1. Wenn eine Vorlage eine gültige Vorlagen Argumentliste für die andere Vorlage ist, aber das Gegenteil nicht zutrifft, wird diese Vorlage als weniger spezialisiert angesehen als die andere Vorlage. Wenn Sie den vorherigen Schritt verwenden, bilden beide Vorlagen jeweils gültige Argumente, dann werden Sie als gleichermaßen spezialisiert betrachtet, und es werden Mehrdeutige Aufrufe erzielt, wenn Sie versuchen, Sie zu verwenden.

1. Mithilfe dieser Regeln können Sie:

   1. Eine Vorlagenspezialisierung für einen bestimmten Typ ist spezialisierter als eine, die ein generisches Typargument verwendet.

   1. Eine Vorlage `T`, die `T*` nur unternimmt, ist spezialisiertere, da ein `X*` hypothetischer Typ ein gültiges Argument `T` für ein Vorlagen Argument `X` ist, aber kein gültiges Argument für einen `T*`Vorlagen Argument.

   1. `const T`ist `T`spezialisiertere als `const X` , da ein gültiges Argument für `T` ein Vorlagen Argument ist `X` , aber kein gültiges Argument für ein `const T` Vorlagen Argument ist.

   1. `const T*`ist `T*`spezialisiertere als `const X*` , da ein gültiges Argument für `T*` ein Vorlagen Argument ist `X*` , aber kein gültiges Argument für ein `const T*` Vorlagen Argument ist.

## <a name="example"></a>Beispiel

Das folgende Beispiel funktioniert wie im Standard angegeben:

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

template <class T> void f(T) {
   printf_s("Less specialized function called\n");
}

template <class T> void f(T*) {
   printf_s("More specialized function called\n");
}

template <class T> void f(const T*) {
   printf_s("Even more specialized function for const T*\n");
}

int main() {
   int i =0;
   const int j = 0;
   int *pi = &i;
   const int *cpi = &j;

   f(i);   // Calls less specialized function.
   f(pi);  // Calls more specialized function.
   f(cpi); // Calls even more specialized function.
   // Without partial ordering, these calls would be ambiguous.
}
```

### <a name="output"></a>Ausgabe

```Output
Less specialized function called
More specialized function called
Even more specialized function for const T*
```

## <a name="see-also"></a>Siehe auch

[Funktionsvorlagen](../cpp/function-templates.md)
