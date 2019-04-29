---
title: Übersicht über C++-Anweisungen
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
ms.openlocfilehash: 9493860087331ee2d8ff05a5c0bd59c7a46ad51a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325558"
---
# <a name="overview-of-c-statements"></a>Übersicht über C++-Anweisungen

C++-Anweisungen werden nacheinander ausgeführt, außer wenn diese Sequenz von einer Ausdrucksanweisung, einer Selektionsanweisung, einer Iterationsanweisung oder einer Sprunganweisung speziell geändert wird.

Anweisungen können folgende Typen aufweisen:

```
labeled-statement
expression-statement
compound-statement
selection-statement
iteration-statement
jump-statement
declaration-statement
try-throw-catch
```

In den meisten Fällen ist die Syntax der C++-Anweisung identisch mit der ANSI C. Der Hauptunterschied zwischen den beiden, die in C ist, Deklarationen nur am Anfang eines Blocks zulässig. C++ fügt die *deklarationsanweisung*, wodurch effektiv diese Einschränkung entfernt. Dadurch können Sie Variablen an einem Punkt im Programm einführen, an dem ein vorausberechneter Initialisierungswert berechnet werden kann.

Das Deklarieren von Variablen innerhalb von Blöcken ermöglicht Ihnen auch die genaue Steuerung des Gültigkeitsbereichs und der Lebensdauer dieser Variablen.

Die Anweisungsthemen beschreiben die folgenden C++-Schlüsselwörter:

|||||
|-|-|-|-|
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||

## <a name="see-also"></a>Siehe auch

[Anweisungen](../cpp/statements-cpp.md)