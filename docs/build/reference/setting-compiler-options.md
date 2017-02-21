---
title: "Festlegen von Compileroptionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Festlegen von Optionen"
  - "Compileroptionen, Festlegen"
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Festlegen von Compileroptionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\- und C\+\+\-Compileroptionen können entweder in der Entwicklungsumgebung oder über die Befehlszeile festgelegt werden.  
  
## In der Entwicklungsumgebung  
 Sie können für jedes Projekt Compileroptionen in dem entsprechenden **Eigenschaftenseiten** festlegen.  Wählen Sie im linken Bereich **Konfigurationseigenschaften**, **C\/C\+\+** aus, und wählen Sie anschließend die Kategorie für die Compileroption aus.  In den Themen zu den einzelnen Compileroptionen wird erläutert, wo die jeweilige Option in der Entwicklungsumgebung zu finden ist und wie sie eingestellt werden kann.  Eine vollständige Liste finden Sie im Abschnitt [Compileroptionen](../../build/reference/compiler-options.md).  
  
## Außerhalb der Entwicklungsumgebung  
 Sie können die Optionen für den Compiler \(CL.exe\) an folgenden Stellen festlegen:  
  
-   [Über die Befehlszeile](../../build/reference/compiler-command-line-syntax.md)  
  
-   [In Befehlsdateien](../../build/reference/cl-command-files.md)  
  
-   [In der CL\-Umgebungsvariablen](../../build/reference/cl-environment-variables.md)  
  
 Die in der CL\-Umgebungsvariablen festgelegten Optionen werden bei jedem Aufrufen von CL.EXE verwendet.  Wenn eine Befehlsdatei in der CL\-Umgebungsvariablen oder in der Befehlszeile angegeben wird, werden die in der Befehlsdatei festgelegten Optionen verwendet.  Anders als in der Befehlszeile oder in der CL\-Umgebungsvariablen können Sie in einer Befehlsdatei mehrzeilige Optionen und Dateinamen verwenden.  
  
 Compileroptionen werden "von links nach rechts" verarbeitet. Wird ein Konflikt erkannt, überwiegt die letzte Option \(ganz rechts\).  Die CL\-Umgebungsvariable wird vor der Befehlszeile verarbeitet. Sollte es also zu Konflikten zwischen CL und der Befehlszeile kommen, so hat die Befehlszeile Vorrang.  
  
## Weitere Themen zum Compiler  
  
-   [Schnelle Kompilierung](../../build/reference/fast-compilation.md)  
  
-   [CL: Starten des Linkers](../../build/reference/cl-invokes-the-linker.md)  
  
## Siehe auch  
 [Referenz zur C\/C\+\+\-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)