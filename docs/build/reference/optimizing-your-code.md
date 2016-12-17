---
title: "Codeoptimierung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Leistung"
  - "Code, Optimieren"
  - "Optimierung"
  - "Optimierung, C++-Code"
  - "Leistung, Compiler"
  - "Leistung, Optimieren von Code"
ms.assetid: 4f33e6c7-9870-43b3-9c2f-d7e44f764971
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# Codeoptimierung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durch die Optimierung einer ausführbaren Datei können Sie sowohl von schneller Ausführungsgeschwindigkeit als auch von kleiner Codegröße profitieren.  In diesem Thema werden einige der Mechanismen erläutert, mit denen Sie in Visual C\+\+ Code optimieren können.  
  
## Sprachfeatures  
 In den folgenden Themen werden einige der Optimierungen in der Programmiersprache C\/C\+\+ beschrieben.  
  
 [Pragmas und Schlüsselwörter für die Optimierung](../../build/reference/optimization-pragmas-and-keywords.md)  
 Eine Liste von Schlüsselwörtern und Pragmas, die Sie im Code verwenden können, um die Leistung zu verbessern.  
  
 [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md)  
 Eine Liste von **\/O**\-Compileroptionen, die sich speziell auf Ausführungsgeschwindigkeit oder Codegröße auswirken.  
  
 [Rvalue\-Verweisdeklarator: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)  
 Rvalue\-Verweise unterstützen die Implementierung von *Verschiebesemantik*.  Wenn Verschiebesemantik zur Implementierung von Vorlagenbibliotheken verwendet wird, kann dadurch die Leistung von Anwendungen, die diese Vorlagen verwenden, bedeutend verbessert werden.  
  
### Das optimize\-Pragma  
 Wenn ein optimierter Codeabschnitt Fehler oder eine Verlangsamung verursacht, können Sie die Optimierung mit dem [optimize](../../preprocessor/optimize.md)\-Pragma für diesen Abschnitt deaktivieren.  
  
 Schließen Sie den Code folgendermaßen in zwei Pragmas ein:  
  
```  
#pragma optimize("", off)  
// some code here   
#pragma optimize("", on)  
```  
  
## Programmierempfehlungen  
 Möglicherweise werden auch zusätzliche Warnmeldungen angezeigt, wenn Sie Code mit implementierter Optimierung kompilieren.  Dieses Verhalten tritt erwartungsgemäß auf, da einige Warnungen sich nur auf optimierten Code beziehen.  Sie können viele Optimierungsprobleme vermeiden, indem Sie diese Warnungen beachten.  
  
 Paradoxerweise kann die Geschwindigkeitsoptimierung eines Programms zur langsameren Ausführung des Codes führen.  Dies ergibt sich aus der Verlängerung des Codes, die durch die Geschwindigkeitsoptimierungen verursacht wird.  Durch das Einbetten von Funktionen wird z. B. der Mehraufwand für Funktionsaufrufe vermieden.  Jedoch kann durch das Einbetten von zu viel Code das Programm derart vergrößert werden, dass die Anzahl der durch den virtuellen Arbeitsspeicher verursachten Seitenfehler zunimmt.  Die durch fehlende Funktionsaufrufe gewonnene Geschwindigkeit kann also durch Speicherauslagerungen wieder zunichte gemacht werden.  
  
 In den folgenden Themen werden bewährte Programmierstile erläutert.  
  
 [Tipps zum Verbessern von zeitkritischem Code](../../build/reference/tips-for-improving-time-critical-code.md)  
 Bessere Codierungstechniken können die Leistung verbessern.  In diesem Thema werden Codierungstechniken vorgestellt, die bei der Optimierung der zeitkritischen Teile des Codes helfen können.  
  
 [Empfohlene Vorgehensweisen für die Optimierung](../../build/reference/optimization-best-practices.md)  
 Stellt allgemeine Richtlinien zur Anwendungsoptimierung bereit.  
  
## Debuggen von optimiertem Code.  
 Da der vom Compiler erstellte Code durch die Optimierung geändert werden könnte, empfiehlt es sich, die Anwendung zu debuggen, die Leistung zu messen und dann den Code zu optimieren.  
  
 In den folgenden Themen finden Sie grundlegende Informationen zum Debuggen.  
  
-   [Debuggen in Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md)  
  
-   [Häufig auftretende Probleme beim Erstellen eines Releasebuilds](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
 In den folgenden Themen finden Sie weiterführende Informationen zum Debuggen.  
  
-   [Gewusst wie: Debuggen von optimiertem Code](../Topic/How%20to:%20Debug%20Optimized%20Code.md)  
  
-   [Warum Gleitkommazahlen an Genauigkeit verlieren können](../../build/reference/why-floating-point-numbers-may-lose-precision.md)  
  
 In den folgenden Themen finden Sie Informationen dazu, wie Sie das Erstellen, Laden und Ausführen des Codes optimieren können.  
  
-   [Erhöhen des Compilerdurchsatzes](../../build/reference/improving-compiler-throughput.md)  
  
-   [Bei Verwendung eines Funktionsnamens ohne "\(\)" wird kein Code generiert](../../build/reference/using-function-name-without-parens-produces-no-code.md)  
  
-   [Optimieren der Inlineassembly](../../assembler/inline/optimizing-inline-assembly.md)  
  
-   [Festlegen der Compileroptimierung für ein ATL\-Projekt](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)  
  
-   [Welche Optimierungstechniken sollten verwendet werden, um die Leistung der Clientanwendung beim Laden zu verbessern?](../../build/what-optimization-techniques-should-i-use.md)  
  
-   [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)], wie die Zeit reduziert, DLL\-Methoden zu laden, sehen "Load Time Performance\) "unter der Ladezeit" optimieren Spalte im "MSDN Magazine" auf der [MSDN Library](http://go.microsoft.com/fwlink/?linkid=556) Website.  
  
-   [!INCLUDE[crabout](../../build/reference/includes/crabout_md.md)], wie Paging in Anwendungen finden, "Laufzeitleistung mit dem Smooth Artikeln zum Verbessern" und "Laufzeitleistung mit dem Smooth Workingset\-Tool\-Teil verbessern 2 " in der Spalte "Bugslayer" im "MSDN Magazine" auf der [MSDN Library](http://go.microsoft.com/fwlink/?linkid=556) Website minimiert.  
  
## Siehe auch  
 [Referenz zur C\/C\+\+\-Erstellung](../../build/reference/c-cpp-building-reference.md)