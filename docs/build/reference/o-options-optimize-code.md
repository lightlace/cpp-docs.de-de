---
title: "/O-Optionen (Code optimieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.Optimization"
  - "/o"
  - "VC.Project.VCCLWCECompilerTool.Optimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Leistung"
  - "Leistung, cle.exe-Compiler"
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /O-Optionen (Code optimieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **\/O**\-Optionen steuern verschiedene Optimierungsprozesse, mit deren Hilfe Sie Code erstellen können, der möglichst schnell verarbeitet werden kann oder den kleinstmöglichen Umfang hat.  
  
-   [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) optimiert Code für minimale Größe.  
  
-   [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) optimiert Code für maximale Geschwindigkeit.  
  
-   [\/Ob](../../build/reference/ob-inline-function-expansion.md) steuert die Inlinefunktionserweiterung.  
  
-   [\/Od](../../build/reference/od-disable-debug.md) deaktiviert die Optimierung. Das Kompilieren wird dadurch beschleunigt, und das Debuggen wird erleichtert.  
  
-   [\/Og](../../build/reference/og-global-optimizations.md) aktiviert globale Optimierungen.  
  
-   [\/Oi](../../build/reference/oi-generate-intrinsic-functions.md) erstellt systeminterne Funktionen für entsprechende Funktionsaufrufe.  
  
-   [\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) veranlasst den Compiler, Optimierungen der Größe den Optimierungen der Geschwindigkeit vorzuziehen.  
  
-   [\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) \(eine Standardeinstellung\) veranlasst den Compiler, Optimierungen der Geschwindigkeit den Optimierungen der Größe vorzuziehen.  
  
-   [\/Ox](../../build/reference/ox-full-optimization.md) aktiviert sämtliche Optimierungen.  
  
-   [\/Oy](../../build/reference/oy-frame-pointer-omission.md) unterdrückt das Erstellen von Framezeigern in der Aufrufliste für schnellere Funktionsaufrufe.  
  
## Hinweise  
 Sie können auch mehrere **\/O**\-Optionen in einer einzigen option\-Anweisung kombinieren.  Beispielsweise ist `/Odi` dasselbe wie `/Od /Oi`.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)