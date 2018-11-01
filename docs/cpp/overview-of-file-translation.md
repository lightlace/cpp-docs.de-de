---
title: Übersicht über die Dateiübersetzung
ms.date: 11/04/2016
helpviewer_keywords:
- file translation [C++], about file translation
- translation [C++]
- translation phases
- files [C++], translation
- programs [C++], lexical conventions of
- preprocessing translation phase
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
ms.openlocfilehash: cb8a8fea2411e4eb7de78545f70021f3617b0f52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442860"
---
# <a name="overview-of-file-translation"></a>Übersicht über die Dateiübersetzung

C++-Programme wie C-Programme bestehen aus mindestens einer Datei. Jede dieser Dateien wird in der folgenden konzeptionellen Reihenfolge übersetzt (die tatsächliche Reihenfolge folgt der "als ob"-Regel: Übersetzung muss so erfolgen, als wären diese Schritte befolgt worden):

1. Lexikalische Tokenisierung. Zeichenzuordnung und Trigraphverarbeitung, Splicing von Zeilen und Tokenisierung werden in dieser Übersetzungsphase ausgeführt.

1. Vorverarbeitung. Diese übersetzungsphase werden zusätzliche Quelldateien verweist `#include` Direktiven, kümmert sich um "Zeichenfolgen" und "eingebracht"-Direktiven und führt token eingefügt und Makros erweitert (finden Sie unter [Präprozessoranweisungen](../preprocessor/preprocessor-directives.md) in der *Präprozessorreferenz* Informationen). Das Ergebnis der Vorverarbeitungsphase ist eine Sequenz von Token, die zusammen eine "Übersetzungseinheit" definieren.

   Präprozessoranweisungen beginnen immer mit dem Nummernzeichen (**#**) Zeichen (d. h. das erste Zeichen für Zeichen in der Zeile muss ein Nummernzeichen sein). In einer angegebenen Zeile kann nur eine Präprozessoranweisung stehen. Zum Beispiel:

    ```cpp
    #include <iostream>  // Include text of iostream in
                         //  translation unit.
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty
                         //  text string).
    ```

1. Codegenerierung. Diese Übersetzungsphase verwendet die Token, die in der Vorverarbeitungsphase zum Generieren von Objektcode generiert wurden.

   Während dieser Phase wird die syntaktische und semantische Prüfung des Quellcodes ausgeführt.

Finden Sie unter [Phasen der Übersetzung](../preprocessor/phases-of-translation.md) in die *Präprozessorreferenz* für Weitere Informationen.

Der C++-Präprozessor ist eine strikte Obermenge des ANSI C-Präprozessors, aber der C++-Präprozessor unterscheidet sich in mehreren Instanzen. Die folgende Liste beschreibt mehrere Unterschiede zwischen den ANSI C- und den C++-Präprozessoren:

- Einzeilige Kommentare werden unterstützt. Finden Sie unter [Kommentare](../cpp/comments-cpp.md) für Weitere Informationen.

- Ein vordefiniertes Makro, `__cplusplus`, nur für C++ definiert ist. Finden Sie unter [Predefined Macros](../preprocessor/predefined-macros.md) in die *Präprozessorreferenz* für Weitere Informationen.

- Der C-Präprozessor erkennt die C++-Operatoren nicht: **.** <strong>\*</strong>, **->** <strong>\*</strong>, und **::**. Finden Sie unter [Operatoren](../cpp/cpp-built-in-operators-precedence-and-associativity.md) und [Ausdrücke](../cpp/expressions-cpp.md), Weitere Informationen zu Operatoren.

## <a name="see-also"></a>Siehe auch

[Lexikalische Konventionen](../cpp/lexical-conventions.md)
