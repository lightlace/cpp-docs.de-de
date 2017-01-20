---
title: "Wann sollte Quellcode vorkompiliert werden?"
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
  - "Vorkompilierte Headerdateien, Zeitpunkt der Vorkompilierung"
  - "Quellcode, Vorkompilieren"
ms.assetid: eb8ba193-fd87-40d3-9545-c75deabe37cb
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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