---
title: "Erstellen vorkompilierter Headerdateien"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch-Dateien, Erstellen"
  - "cl.exe-Compiler, Vorkompilieren von Code"
  - "PCH-Dateien, Erstellen"
  - "Vorkompilierte Headerdateien, Erstellen"
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Erstellen vorkompilierter Headerdateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Microsoft C\- und C\+\+\-Compiler stellen Optionen für das Vorkompilieren von beliebigem C\- oder C\+\+\-Code bereit, einschließlich Inlinecode.  Mithilfe dieser leistungsstarken Funktion können Sie einen stabilen Codeabschnitt kompilieren, den Code im kompilierten Zustand in einer Datei speichern und bei nachfolgenden Kompilierungen den vorkompilierten Code mit dem noch in Entwicklung befindlichen Code kombinieren.  So können nachfolgende Kompilierungen beschleunigt werden, da der bereits stabile Code nicht neu kompiliert werden muss.  
  
 Dieser Abschnitt behandelt folgende Themen zu vorkompilierten Headerdateien:  
  
-   [Wann sollte Quellcode vorkompiliert werden?](../../build/reference/when-to-precompile-source-code.md)  
  
-   [Zwei Methoden für das Vorkompilieren von Code](../../build/reference/two-choices-for-precompiling-code.md)  
  
-   [Konsistenzregeln für vorkompilierte Header](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [Verwenden von vorkompilierten Headern in einem Projekt](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 Referenzinformationen zu den Compileroptionen für vorkompilierte Header finden Sie unter [\/Y \(Vorkompilierte Header\)](../../build/reference/y-precompiled-headers.md).  
  
## Siehe auch  
 [Referenz zur C\/C\+\+\-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)