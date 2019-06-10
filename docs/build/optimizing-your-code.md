---
title: Codeoptimierung
ms.date: 05/06/2019
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: f44fb734c8441e10b656c5326c8df4bf6879499a
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220175"
---
# <a name="optimizing-your-code"></a>Optimieren des Codes

Durch Optimieren der eine ausführbare Datei, können Sie ein Gleichgewicht zwischen schnelle Ausführung der Geschwindigkeit und Größe von kompakten Code erreichen. Dieses Thema behandelt einige der die Mechanismen, die Visual Studio bietet, um den Code optimieren können.

## <a name="language-features"></a>Sprachfunktionen

In den folgenden Themen werden einige der Optimierungen in der C/C++-Sprache beschrieben.

[Optimierung mit Pragmas und Schlüsselwörter](optimization-pragmas-and-keywords.md) \
Eine Liste der Schlüsselwörter und Pragmas, dass Sie in Ihrem Code verwenden können, um die Leistung zu verbessern.

[Compileroptionen nach Kategorien sortiert](reference/compiler-options-listed-by-category.md) \
Eine Liste der **/o** Compileroptionen, die speziell Ausführung Geschwindigkeit oder Code Größe beeinflussen.

[Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md) \
Rvalue-Verweise unterstützen die Implementierung der *move-Semantik*. Wenn die Verschiebung, die Semantik verwendet wird, um Vorlagenbibliotheken, die Leistung von Anwendungen zu implementieren, verwenden diese Vorlagen, erheblich verbessern kann.

### <a name="the-optimize-pragma"></a>Das optimierungspragma

Wenn ein optimierte Codeabschnitt Fehler oder eine Verlangsamung verursacht, können Sie mithilfe der [optimieren](../preprocessor/optimize.md) Pragma, um die Optimierung für diesen Abschnitt zu deaktivieren.

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

[Tipps zum Verbessern von zeitkritischem Code](tips-for-improving-time-critical-code.md) \
Bessere Codierung Techniken kann eine bessere Leistung erzielt werden. In diesem Thema schlägt vor, Programmiertechniken, mit denen Sie sicherstellen, dass die zeitkritischen Teile Ihres Codes eine zufriedenstellende Leistung erbringen können.

[Bewährte Vorgehensweisen für die Optimierung](optimization-best-practices.md) \
Enthält allgemeine Richtlinien zur optimalen Anwendungsleistung zu optimieren.

## <a name="debugging-optimized-code"></a>Debuggen von optimiertem code

Da die Optimierung den vom Compiler erstellten Code ändern kann, empfehlen wir, dass Sie der Anwendung debuggen und die Leistung zu messen, und klicken Sie dann den Code zu optimieren.

Die folgenden Themen enthalten Informationen zum Debuggen von Release-Builds.

- [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)

- [Vorgehensweise: Debuggen von optimiertem Code](/visualstudio/debugger/how-to-debug-optimized-code)

- [Warum Gleitkommazahlen an Genauigkeit verlieren können](why-floating-point-numbers-may-lose-precision.md)


In den folgenden Themen bieten Informationen zum Erstellen, laden und Ausführen des Codes zu optimieren.

- [Erhöhen des Compilerdurchsatzes](improving-compiler-throughput.md)

- [Bei Verwendung eines Funktionsnamens ohne „()“ wird kein Code generiert](using-function-name-without-parens-produces-no-code.md)

- [Optimieren der Inlineassembly](../assembler/inline/optimizing-inline-assembly.md)

- [Festlegen der Compileroptimierung für ein ATL-Projekt](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [Welche Optimierungstechniken sollte ich zur leistungsverbesserung beim Laden der Anwendung verwenden?](../build/dll-frequently-asked-questions.md#mfc_optimization)


## <a name="in-this-section"></a>In diesem Abschnitt

[Optimierung mit Pragmas und Schlüsselwörter](optimization-pragmas-and-keywords.md) \
[Erhöhen des Compilerdurchsatzes](improving-compiler-throughput.md) \
[Warum Gleitkommazahlen an Genauigkeit verlieren können](why-floating-point-numbers-may-lose-precision.md) \
[IEEE-Gleitkommadarstellung](ieee-floating-point-representation.md) \
[Tipps zum Verbessern von zeitkritischem Code](tips-for-improving-time-critical-code.md) \
[Verwendung eines Funktionsnamens ohne () wird kein Code generiert.](using-function-name-without-parens-produces-no-code.md) \
[Bewährte Vorgehensweisen für die Optimierung](optimization-best-practices.md) \
[Profilgesteuerte Optimierungen](profile-guided-optimizations.md) \
[Umgebungsvariablen für Profilgesteuerte Optimierungen](environment-variables-for-profile-guided-optimizations.md) \
[PgoAutoSweep](pgoautosweep.md) \
[pgomgr](pgomgr.md) \
[pgosweep](pgosweep.md) \
[Vorgehensweise: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](reference/c-cpp-building-reference.md)
