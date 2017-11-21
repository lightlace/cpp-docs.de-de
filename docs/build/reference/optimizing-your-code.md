---
title: Codeoptimierung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.assetid: 4f33e6c7-9870-43b3-9c2f-d7e44f764971
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3da29e9a0269c4748f10d9e8ba926103305239e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="optimizing-your-code"></a>Codeoptimierung
Optimieren Sie eine ausführbare Datei, können Sie ein Gleichgewicht zwischen schnelle ausführungsgeschwindigkeit und kleine Codegröße erzielen. In diesem Artikel werden einige der Mechanismen, die Visual C++ bietet, um Code optimieren können.  
  
## <a name="language-features"></a>Sprachfunktionen  
 In den folgenden Themen werden einige der Funktionen zur Optimierung in der C/C++-Sprache beschrieben.  
  
 [Pragmas und Schlüsselwörter für die Optimierung](../../build/reference/optimization-pragmas-and-keywords.md)  
 Eine Liste der Schlüsselwörter und Pragmas, die Sie in Ihrem Code verwenden können, um die Leistung zu verbessern.  
  
 [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md)  
 Eine Liste der **/o** Compileroptionen, die speziell Ausführung Geschwindigkeit oder Code Größe auswirken.  
  
 [Rvalue-Verweisdeklarator: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)  
 Rvalue-Verweise unterstützen die Implementierung der *Verschiebesemantik*. Wenn Move Semantik verwendet werden, um Vorlagenbibliotheken, die Leistung der Anwendung zu implementieren, verwenden diese Vorlagen deutlich verbessert werden kann.  
  
### <a name="the-optimize-pragma"></a>Optimize-Pragmas  
 Wenn ein optimierte Codeabschnitt Fehler oder eine Verlangsamung verursacht, können Sie mithilfe der [optimieren](../../preprocessor/optimize.md) Pragma verwenden, um die Optimierung für diesen Abschnitt zu deaktivieren.  
  
 Schließen Sie den Code zwischen den zwei Pragmas, wie folgt.  
  
```  
#pragma optimize("", off)  
// some code here   
#pragma optimize("", on)  
```  
  
## <a name="programming-practices"></a>Programmierung-Methoden  
 Sie möglicherweise zusätzliche Warnmeldungen beim Kompilieren von Code mit der Optimierung fest. Dieses Verhalten wird erwartet, da einige Warnungen nur mit optimiertem Code in Zusammenhang stehen. Viele Probleme bei der Optimierung können vermieden werden, wenn Sie diese Hinweise zu beachten.  
  
 Ein Programm für Geschwindigkeit optimieren kann Paradoxerweise Code langsamer ausgeführt verursachen. Dies ist, da einige Optimierungen für Geschwindigkeit Codegröße erhöhen. Beispielsweise inlining Funktionen beseitigt den Mehraufwand der Funktionsaufrufe. Allerdings inlining zu viel Code kann, das Programm so groß, dass die Anzahl der virtuellen Speicherseite zunimmt Seitenfehler. Aus diesem Grund kann die Geschwindigkeit Erkenntnissen eliminieren Funktionsaufrufe zum Austauschen von Arbeitsspeicher verloren.  
  
 In den folgenden Themen werden bewährte Programmierverfahren erläutert.  
  
 [Tipps zum Verbessern von zeitkritischem Code](../../build/reference/tips-for-improving-time-critical-code.md)  
 Bessere Codierungstechniken kann eine bessere Leistung ergeben. In diesem Thema wird vorgeschlagen, Codierungstechniken, mit denen Sie sicherstellen, dass die zeitkritischen Teile Ihres Codes eine zufriedenstellende Leistung erbringen können.  
  
 [Empfohlene Vorgehensweisen für die Optimierung](../../build/reference/optimization-best-practices.md)  
 Bietet allgemeine Richtlinien zur optimalen Anwendungsleistung zu optimieren.  
  
## <a name="debugging-optimized-code"></a>Debuggen von optimiertem Code  
 Da die Optimierung den vom Compiler erstellten Code geändert werden kann, wird empfohlen, dass Sie Ihre Anwendung debuggen und die Leistung zu messen und den Code zu optimieren.  
  
 In den folgenden Themen bieten grundlegende Informationen zum Debuggen.  
  
-   [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)  
  
-   [Häufig auftretende Probleme beim Erstellen eines Releasebuilds](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
 Die folgenden Themen enthalten weitere Informationen zum Debuggen.  
  
-   [Gewusst wie: Debuggen von optimiertem Code](/visualstudio/debugger/how-to-debug-optimized-code)  
  
-   [Warum Gleitkommazahlen an Genauigkeit verlieren können](../../build/reference/why-floating-point-numbers-may-lose-precision.md)  
  
 Die folgenden Themen finden Informationen zum Erstellen, laden und Ausführen von Code zu optimieren.  
  
-   [Erhöhen des Compilerdurchsatzes](../../build/reference/improving-compiler-throughput.md)  
  
-   [Bei Verwendung eines Funktionsnamens ohne „()“ wird kein Code generiert](../../build/reference/using-function-name-without-parens-produces-no-code.md)  
  
-   [Optimieren der Inlineassembly](../../assembler/inline/optimizing-inline-assembly.md)  
  
-   [Festlegen der Compileroptimierung für ein ATL-Projekt](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)  
  
-   [Welche Optimierungstechniken sollten werden verwendet, um die Leistung der Clientanwendung beim Laden zu verbessern?](../../build/dll-frequently-asked-questions.md#mfc_optimization)  
  
-   [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)]Gewusst wie: reduzieren die Zeit zum Laden der DLL-Methoden finden Sie unter "Optimizing DLL laden Zeit Performance" in der Spalte "Details" im "MSDN Magazin" auf die [MSDN Library](http://go.microsoft.com/fwlink/?linkid=556) Website.  
  
-   [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)]zum Minimieren der Auslagerung in Anwendungen finden Sie unter "Verbessern der Laufzeit mit der Smooth arbeiten festgelegt Leistungstool" und "Improving Leistung zur Laufzeit mit der Smooth Set-Tool – Teil 2" in der Spalte "Bugslayer" im "MSDN Magazin" auf die [MSDN Bibliothek](http://go.microsoft.com/fwlink/?linkid=556) Website.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)