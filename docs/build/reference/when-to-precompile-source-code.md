---
title: "Wann sollte Quellcode vorkompiliert werden? | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vorkompilierte Headerdateien, Zeitpunkt der Vorkompilierung"
  - "Quellcode, Vorkompilieren"
ms.assetid: eb8ba193-fd87-40d3-9545-c75deabe37cb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Wann sollte Quellcode vorkompiliert werden?
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vorkompilierter Code trägt während des Entwicklungszyklus dazu bei, die Kompilierungszeit zu verringern. Dies gilt insbesondere in folgenden Fällen:  
  
-   Sie verwenden stets umfangreiche Codeabschnitte, die sich nur selten ändern.  
  
-   Das Programm besteht aus mehreren Modulen, die alle einen Standardsatz von Includedateien sowie dieselben Kompilierungsoptionen verwenden.  In dem Fall können alle Includedateien zu einem vorkompilierten Header vorkompiliert werden.  
  
 Die erste Kompilierung, durch die die vorkompilierte Headerdatei erstellt wird, benötigt etwas mehr Zeit als die nachfolgenden Kompilierungen.  Diese können dann schneller ablaufen, da vorkompilierter Code einbezogen wird.  
  
 Sie können C\- und C\+\+\-Programme vorkompilieren.  Bei der C\+\+\-Programmierung ist es üblich, klassenspezifische Schnittstelleninformationen in getrennte Headerdateien zu schreiben.  Diese Headerdateien können später in Programme einbezogen werden, die die Klasse verwenden.  Durch Vorkompilieren dieser Header können Sie die Zeit reduzieren, die für die Kompilierung eines Programms benötigt wird.  
  
> [!NOTE]
>  Obwohl nur eine vorkompilierte Headerdatei \(.pch\) pro Quelldatei zulässig ist, können Sie innerhalb eines Projekts mehrere PCH\-Dateien verwenden.  
  
## Siehe auch  
 [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)