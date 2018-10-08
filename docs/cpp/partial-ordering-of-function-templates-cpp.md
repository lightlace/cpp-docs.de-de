---
title: Partielle Reihenfolge von Funktionsvorlagen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 048589ecab367a3762764b627de11d72160c4602
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861303"
---
# <a name="partial-ordering-of-function-templates-c"></a>Partielle Reihenfolge von Funktionsvorlagen (C++)

Es können mehrere Funktionsvorlagen, die der Argumentliste eines Funktionsaufrufs entsprechen, verfügbar sein. C++ definiert eine partielle Reihenfolge von Funktionsvorlagen, um anzugeben, welche Funktion aufgerufen werden soll. Die Reihenfolge ist partiell, da es mehrere Vorlagen geben kann, die als genauso spezialisiert betrachtet werden.

Der Compiler wählt die speziellste Vorlagenfunktion aus, die aus den möglichen Übereinstimmungen verfügbar ist. Wenn eine Funktionsvorlage einen Typ akzeptiert z. B. __T__, und eine andere Funktionsvorlage __T\*__  verfügbar ist, die __T\*__  Version wird als bezeichnet. Weitere spezialisierte und wird bevorzugt die generische __T__ Version, wenn das Argument ein Zeigertyp ist, auch wenn beide Übereinstimmungen zulässig wären.

Verwenden Sie folgenden Prozess, um zu ermitteln, ob ein Funktionsvorlagenkandidat spezialisierter ist:

1. Berücksichtigen Sie zwei Funktionsvorlagen, T1 und T2.

1. Ersetzen Sie die Parameter in T1 durch einen hypothetischen eindeutigen Typ X.

1. Überprüfen Sie mit der Parameterliste in T1, ob T2 eine gültige Vorlage für diese Parameterliste ist. Ignorieren Sie alle impliziten Konvertierungen.

1. Wiederholen Sie den gleichen Prozess umgekehrt mit T1 und T2.

1. Wenn eine Vorlage eine gültige Vorlagenargumentliste für die andere Vorlage ist, das Gegenteil aber nicht zutrifft, wird die Vorlage als weniger spezialisiert angesehen als die andere Vorlage. Wenn beide Vorlagen, die mit den vorherigen Schritt Formular gültige Argumente füreinander wird, klicken Sie dann diese werden als einheitlich spezialisiert behandelt werden, und ein Mehrdeutiger Aufruf führt versuchen, bei deren Verwendung.

1. Mithilfe dieser Regeln können Sie:

   1. Eine Vorlagenspezialisierung für einen bestimmten Typ ist spezialisierter als eine, die ein generisches Typargument verwendet.

   1. Eine Vorlage aus, nur dass __T\*__  ist spezialisierter als eine dauert nur __T__, da es sich bei einem hypothetischen geben __X\*__  ist ein gültiges Argument für eine __T__ Template-Argument, aber __X__ ist kein gültiges Argument für eine __T\*__  Template-Argument.

   1. __const T__ ist spezialisierter als __T__, da __const X__ ist ein gültiges Argument für eine __T__ Template-Argument, aber __X__ ist kein gültiges Argument für eine __const T__ Template-Argument.

   1. __const T\*__  ist spezialisierter als __T\*__, da __const X\*__  ist ein gültiges Argument für eine __T\*__  Template-Argument, aber __X\*__  ist kein gültiges Argument für eine __const T\*__  Template-Argument.

## <a name="example"></a>Beispiel

Das folgende Beispiel funktioniert wie im Standard angegeben:

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

extern "C" int printf(const char*,...);
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

### <a name="output"></a>Output

```Output
Less specialized function called
More specialized function called
Even more specialized function for const T*
```

## <a name="see-also"></a>Siehe auch

[Funktionsvorlagen](../cpp/function-templates.md)
