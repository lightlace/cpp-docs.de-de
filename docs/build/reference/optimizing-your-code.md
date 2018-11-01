---
title: Codeoptimierung
ms.date: 12/28/2017
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: d490bd704c53a160ee36dea0fd24a52211bfdc37
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525514"
---
# <a name="optimizing-your-code"></a>Optimieren des Codes

Durch Optimieren der eine ausführbare Datei, können Sie ein Gleichgewicht zwischen schnelle Ausführung der Geschwindigkeit und Größe von kompakten Code erreichen. Dieses Thema behandelt einige der die Mechanismen, die Visual C++ bietet, um den Code optimieren können.

## <a name="language-features"></a>Sprachfunktionen

In den folgenden Themen werden einige der Optimierungen in der C/C++-Sprache beschrieben.

[Pragmas und Schlüsselwörter für die Optimierung](../../build/reference/optimization-pragmas-and-keywords.md)<br/>
Eine Liste der Schlüsselwörter und Pragmas, dass Sie in Ihrem Code verwenden können, um die Leistung zu verbessern.

[Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md)<br/>
Eine Liste der **/o** Compileroptionen, die speziell Ausführung Geschwindigkeit oder Code Größe beeinflussen.

[Rvalue-Verweisdeklarator: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)<br/>
Rvalue-Verweise unterstützen die Implementierung der *move-Semantik*. Wenn die Verschiebung, die Semantik verwendet wird, um Vorlagenbibliotheken, die Leistung von Anwendungen zu implementieren, verwenden diese Vorlagen, erheblich verbessern kann.

### <a name="the-optimize-pragma"></a>Das optimierungspragma

Wenn ein optimierte Codeabschnitt Fehler oder eine Verlangsamung verursacht, können Sie mithilfe der [optimieren](../../preprocessor/optimize.md) Pragma, um die Optimierung für diesen Abschnitt zu deaktivieren.

Schließen Sie den Code zwei Pragmas, wie hier gezeigt:

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>Methoden für die Programmierung

Zusätzlicher Warnmeldungen feststellen beim Kompilieren von Code bei Verwendung der Optimierung verwendet werden. Dieses Verhalten wird erwartet, da einige Warnungen nur für optimierten Code verknüpfen. Sie können vielen Optimierungsproblemen vermeiden, wenn Sie diese Warnungen beachten.

Paradoxerweise kann ein Programm für Geschwindigkeit optimieren Code langsamer ausgeführt führen. Dies ist, da einige Optimierungen auf Geschwindigkeit Codegröße erhöhen. Beispielsweise ist es möglich, inlining Funktionen beseitigt den Mehraufwand der Funktionsaufrufe. Allerdings inlining zu viel Code kann, das Programm so groß, dass die Anzahl der virtuellen Arbeitsspeicher zunimmt Seitenfehler. Aus diesem Grund kann die Geschwindigkeit, beseitigen Funktionsaufrufe gewonnen wurden zum Austauschen von Speicher verloren.

Die folgenden Themen werden bewährte Programmierverfahren erläutert.

[Tipps zum Verbessern von zeitkritischem Code](../../build/reference/tips-for-improving-time-critical-code.md)<br/>
Bessere Codierung Techniken kann eine bessere Leistung erzielt werden. In diesem Thema schlägt vor, Programmiertechniken, mit denen Sie sicherstellen, dass die zeitkritischen Teile Ihres Codes eine zufriedenstellende Leistung erbringen können.

[Empfohlene Vorgehensweisen für die Optimierung](../../build/reference/optimization-best-practices.md)<br/>
Enthält allgemeine Richtlinien zur optimalen Anwendungsleistung zu optimieren.

## <a name="debugging-optimized-code"></a>Debuggen von optimiertem code

Da die Optimierung den vom Compiler erstellten Code ändern kann, empfehlen wir, dass Sie der Anwendung debuggen und die Leistung zu messen, und klicken Sie dann den Code zu optimieren.

In den folgenden Themen bieten grundlegende Informationen zum Debuggen.

- [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)

- [Häufig auftretende Probleme beim Erstellen eines Releasebuilds](../../build/reference/common-problems-when-creating-a-release-build.md)

In den folgenden Themen bieten erweiterte Informationen zum Debuggen.

- [Gewusst wie: Debuggen von optimiertem Code](/visualstudio/debugger/how-to-debug-optimized-code)

- [Warum Gleitkommazahlen an Genauigkeit verlieren können](../../build/reference/why-floating-point-numbers-may-lose-precision.md)

In den folgenden Themen bieten Informationen zum Erstellen, laden und Ausführen des Codes zu optimieren.

- [Erhöhen des Compilerdurchsatzes](../../build/reference/improving-compiler-throughput.md)

- [Bei Verwendung eines Funktionsnamens ohne „()“ wird kein Code generiert](../../build/reference/using-function-name-without-parens-produces-no-code.md)

- [Optimieren der Inlineassembly](../../assembler/inline/optimizing-inline-assembly.md)

- [Festlegen der Compileroptimierung für ein ATL-Projekt](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [Welche Optimierungstechniken sollte ich zur leistungsverbesserung beim Laden der Anwendung verwenden?](../../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)
