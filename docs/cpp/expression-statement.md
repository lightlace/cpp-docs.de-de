---
title: Ausdrucksanweisung
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
ms.openlocfilehash: 2973c3e0a1cd59edfc7ef1e771454b780da23cf9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400603"
---
# <a name="expression-statement"></a>Ausdrucksanweisung

Ausdrucksanweisungen bewirken die Auswertung von Ausdrücken. Keine Übertragung der Steuerung oder Iteration tritt infolge einer Ausdrucksanweisung auf.

Die Syntax für die Ausdrucksanweisung ist einfach

## <a name="syntax"></a>Syntax

```
[expression ] ;
```

## <a name="remarks"></a>Hinweise

Alle Ausdrücke in einer Ausdrucksanweisung werden ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die nächste Anweisung ausgeführt wird. Die häufigsten Ausdrucksanweisungen sind Zuweisungen und Funktionsaufrufe.  Da der Ausdruck optional ist, wird ein Semikolon allein als eine leere Ausdrucksanweisung, um genannte betrachtet die [null](../cpp/null-statement.md) Anweisung.

## <a name="see-also"></a>Siehe auch

[Übersicht über C++-Anweisungen](../cpp/overview-of-cpp-statements.md)