---
title: Partielle Reihenfolge von Funktionsvorlagen (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cddc0f1680a3354276a2135dd28c31a2037a8202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="partial-ordering-of-function-templates-c"></a>Partielle Reihenfolge von Funktionsvorlagen (C++)

Es können mehrere Funktionsvorlagen, die der Argumentliste eines Funktionsaufrufs entsprechen, verfügbar sein. C++ definiert eine partielle Reihenfolge von Funktionsvorlagen, um anzugeben, welche Funktion aufgerufen werden soll. Die Reihenfolge ist partiell, da es mehrere Vorlagen geben kann, die als genauso spezialisiert betrachtet werden.

Der Compiler wählt die speziellste Vorlagenfunktion aus, die aus den möglichen Übereinstimmungen verfügbar ist. Wenn eine Funktionsvorlage einen Typ akzeptiert z. B. __T__, und eine andere Funktionsvorlage __T\*__  verfügbar ist, die __T\*__  Version wird als spezialisiert und ist der generischen __T__ -Version vorzuziehen, wenn das Argument ein Zeigertyp ist, auch wenn beide Übereinstimmungen zulässig wären.

Verwenden Sie folgenden Prozess, um zu ermitteln, ob ein Funktionsvorlagenkandidat spezialisierter ist:

1. Berücksichtigen Sie zwei Funktionsvorlagen, T1 und T2.

2. Ersetzen Sie die Parameter in T1 durch einen hypothetischen eindeutigen Typ X.

3. Überprüfen Sie mit der Parameterliste in T1, ob T2 eine gültige Vorlage für diese Parameterliste ist. Ignorieren Sie alle impliziten Konvertierungen.

4. Wiederholen Sie den gleichen Prozess umgekehrt mit T1 und T2.

5. Wenn eine Vorlage eine gültige Vorlagenargumentliste für die andere Vorlage ist, das Gegenteil aber nicht zutrifft, wird die Vorlage als weniger spezialisiert angesehen als die andere Vorlage. Wenn beide Vorlagen mit dem vorherigen Schritt Formular gültige Argumente miteinander, Sie als werden genauso spezialisiert behandelt, und ein Mehrdeutiger Aufruf führt Wenn Sie versuchen zu verwenden.

6. Mithilfe dieser Regeln können Sie:

     1. Eine Vorlagenspezialisierung für einen bestimmten Typ ist spezialisierter als eine, die ein generisches Typargument verwendet.

     2. Eine Vorlage nur dauert __T\*__  ist spezialisierter als eine dauert __T__, da eine hypothetische geben __X\*__  ist ein gültiges Argument für eine __T__ Vorlagenarguments, aber __X__ ist kein gültiges Argument für eine __T\*__  Vorlagenargument.

     3. __const T__ ist spezialisierter als __T__, da __const X__ ist ein gültiges Argument für eine __T__ Vorlagenarguments, aber __X__ ist kein gültiges Argument für eine __const T__ Vorlagenargument.

     4. __const T\*__  ist spezialisierter als __T\*__, da __const X\*__  ist ein gültiges Argument für eine __T\*__  Vorlagenarguments, aber __X\*__  ist kein gültiges Argument für eine __const T\*__  Vorlagenargument.

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
  
### <a name="output"></a>Ausgabe  
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## <a name="see-also"></a>Siehe auch

[Funktionsvorlagen](../cpp/function-templates.md)
