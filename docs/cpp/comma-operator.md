---
title: Kommaoperator:, | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '%2C'
dev_langs:
- C++
helpviewer_keywords:
- comma operator
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 626243da557362626b5d17ed01a8023e36704f54
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114786"
---
# <a name="comma-operator-"></a>Kommaoperator: ,

Ermöglicht das Gruppieren von zwei Anweisungen, wo eine erwartet wird.

## <a name="syntax"></a>Syntax

```
expression , expression
```

## <a name="remarks"></a>Hinweise

Der Operator Komma weist eine Assoziativität von links nach rechts auf. Zwei Ausdrücke, die durch ein Komma getrennt werden, werden von links nach rechts ausgewertet. Der linke Operand wird immer ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor der rechte Operand ausgewertet wird.

Kommas können in einigen Kontexten, z. B. Funktionsargumentlisten, als Trennzeichen verwendet werden. Verwechseln Sie die Verwendung des Kommas als Trennzeichen nicht mit seiner Verwendung als Operator. Die beiden Anwendungsmöglichkeiten sind vollkommen unterschiedlich.

Betrachten Sie den Ausdruck `e1, e2`. Typ und Wert des Ausdrucks entsprechen Typ und Wert des *e2*; das Ergebnis der Auswertung *e1* wird verworfen. Dieses Ergebnis ist ein L-Wert, wenn der rechte Operand ein L-Wert ist.

Während das Komma normalerweise als Trennzeichen verwendet wird (z. B. in tatsächlichen Argumenten für Funktionen oder Aggregatinitialisierer), müssen der Komma-Operator und seine Operanden in Klammern eingeschlossen werden. Zum Beispiel:

```cpp
func_one( x, y + 2, z );
func_two( (x--, y + 2), z );
```

Im obigen Funktionsaufruf an `func_one` werden drei durch Trennzeichen getrennte Argumente übergeben: `x`, `y + 2` und `z`. Im Funktionsaufruf an `func_two` zwingen Klammern den Compiler, das erste Komma als Operator für sequenzielle Auswertung zu interpretieren. Dieser Funktionsaufruf übergibt zwei Argumente an `func_two`. Das erste Argument ist das Ergebnis der Sequentialauswertungsoperation `(x--, y + 2)`, welche den Wert und den Typ des Ausdrucks `y + 2` hat; das zweite Argument ist `z`.

## <a name="example"></a>Beispiel

```cpp
// cpp_comma_operator.cpp
#include <stdio.h>
int main () {
   int i = 10, b = 20, c= 30;
   i = b, c;
   printf("%i\n", i);

   i = (b, c);
   printf("%i\n", i);
}
```

```Output
20
30
```

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Operator für sequenzielle Auswertungen](../c-language/sequential-evaluation-operator.md)