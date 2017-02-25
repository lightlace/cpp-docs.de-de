---
title: "/Q-Optionen (Operationen auf niedriger Ebene) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/q"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Q (Compileroption) [C++]"
  - "-Q (Compileroption) [C++]"
  - "/Q (Compileroption) [C++]"
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# /Q-Optionen (Operationen auf niedriger Ebene)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können die **\/Q**\-Compileroptionen zur Durchführung der folgenden Compilervorgänge auf niedriger Ebene verwenden:  
  
-   [\/Qfast\_transcendentals \(Erzwingen von schnellen Transzendenten\)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): Generiert schnelle Transzendente.  
  
-   [\/QIfist \(\_ftol unterdrücken\)](../../build/reference/qifist-suppress-ftol.md): Unterdrückt `_ftol`, wenn eine Konvertierung von einem Gleitkommatyp in einem ganzzahligen Typ erforderlich ist \(nur x86\).  
  
-   [\/Qimprecise\_fwaits \(Entfernen von fwaits in Try\-Blöcken\)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Entfernt `fwait`\-Befehle in `try`\-Blöcken.  
  
-   [\/Qpar \(Automatische Parallelisierung\)](../../build/reference/qpar-auto-parallelizer.md): Ermöglicht automatische Parallelisierung von Schleifen, die mit der [\#pragma loop\(\)](../../preprocessor/loop.md)\-Direktive gekennzeichnet sind.  
  
-   [\/Qpar\-report \(Auto\-Parallelizer\-Berichtsebene\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): Aktiviert die Berichterstellungsebenen für die automatische Parallelisierung.  
  
-   [\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md): Unterdrückt Optimierungen beim Laden von Gleitkommaregistern und für Verschiebungen zwischen Arbeitsspeicher und MMX\-Registern.  
  
-   [\/Qvec\-report \(Auto\-Vectorizer\-Berichtsebene\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): Aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)