---
title: C++-Ausdrücke (konstant)
ms.date: 11/04/2016
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
ms.openlocfilehash: 97059066adadc3a7897cbd2c4c747e2a673e7201
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154671"
---
# <a name="c-constant-expressions"></a>C++-Ausdrücke (konstant)

Ein *Konstanten* Wert ist, die sich nicht ändert. C++ bietet zwei Schlüsselwörter, mit denen Sie den Zweck eines Objekts angeben können, der nicht dazu gedacht ist, geändert zu werden, und diese Absicht erzwingen soll.

C++ erfordert konstante Ausdrücke – Ausdrücke, die als Konstante ausgewertet werden – für Deklarationen von:

- Arraygrenzen

- Selektoren in case-Anweisungen

- Bitfeldlängenangabe

- Enumerationsinitialisierer

Die einzigen Operanden, die in konstanten Ausdrücken zulässig sind, lauten:

- Literale

- Enumerationskonstanten

- Werte, die als Konstanten deklariert sind und mit konstanten Ausdrücken initialisiert werden.

- **"sizeof"** Ausdrücke

Konstanten, die keine Ganzzahlen sind, müssen (entweder explizit oder implizit) in ganzzahlige Typen konvertiert werden, um in einem konstanten Ausdruck zulässig zu sein. Daher ist der folgende Code gültig:

```cpp
const double Size = 11.0;
char chArray[(int)Size];
```

Explizite Konvertierungen in ganzzahlige Typen sind in Konstanten Ausdrücken zulässig; Alle anderen Typen und abgeleiteten Typen sind nicht zulässig, außer bei Verwendung als Operanden für die **"sizeof"** Operator.

Der Kommaoperator sowie Zuweisungsoperatoren können nicht in konstanten Ausdrücken verwendet werden.

## <a name="see-also"></a>Siehe auch

[Ausdruckstypen](../cpp/types-of-expressions.md)