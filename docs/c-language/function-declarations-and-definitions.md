---
title: "Funktionsdeklarationen und -definitionen"
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
  - "C"
helpviewer_keywords: 
  - "Deklarieren von Funktionen"
  - "Deklarieren von Funktionen, Funktionsdefinitionen"
  - "Externe Deklarationen"
  - "Externe Verknüpfung, Funktionsdeklarationen"
  - "Funktionsdefinitionen, Funktionsdeklarationen"
  - "Funktionsprototypen, Grundlagen"
  - "Interne Deklarationen"
  - "Lokale Deklarationen"
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionsdeklarationen und -definitionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Funktionsprototypen legen den Namen der Funktion, des Rückgabetyps und des Typs und der Anzahl von formalen Parametern fest.  Eine Funktionsdefinition enthält den Funktionsrumpf.  
  
## Hinweise  
 Funktions\- und Variablendeklarationen können innerhalb oder außerhalb einer Funktionsdefinition angezeigt werden.  Jede Deklaration innerhalb einer Funktionsdefinition wird auf "interner" oder "lokaler" Ebene angezeigt.  Eine Deklaration außerhalb aller Funktionsdefinitionen wird auf "externer", globaler" oder auf Ebene des "Dateigültigkeitsbereichs" angezeigt.  Variable Definitionen, wie Deklarationen, können auf der internen Ebene \(innerhalb einer Funktionsdefinition\) oder auf der externen Ebene angezeigt \(außerhalb aller Funktionsdefinitionen\) werden.  Funktionsdefinitionen treten immer auf der externen Ebene auf.  Funktionsdefinitionen werden unter [Funktionsdefinitionen](../c-language/c-function-definitions.md) näher erläutert.  Funktionsprototypen werden unter [Funktionsprototypen](../c-language/function-prototypes.md) behandelt.  
  
## Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)