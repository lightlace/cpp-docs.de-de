---
title: "Schwerwiegender Fehler C1853 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1853"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1853"
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Schwerwiegender Fehler C1853
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die vorkompilierte Headerdatei 'Dateiname' stammt von einer früheren Version des Compilers, oder der vorkompilierte Header stammt von C\+\+, und Sie verwenden ihn von C \(oder umgekehrt\)  
  
 Mögliche Ursachen:  
  
-   Der vorkompilierte Header wurde mit einer älteren Compilerversion kompiliert.  Versuchen Sie, den Header mit dem aktuellen Compiler neu zu kompilieren.  
  
-   Der vorkompilierte Header basiert auf C\+\+, wird aber unter C verwendet.  Versuchen Sie, den Header für die Verwendung mit C neu zu kompilieren, und geben Sie dazu eine der [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)\-Compileroptionen an, oder ändern Sie das Suffix der Quelldatei in "c".  Weitere Informationen finden Sie unter [Zwei Methoden für das Vorkompilieren von Code](../../build/reference/two-choices-for-precompiling-code.md).