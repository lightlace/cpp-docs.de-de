---
title: "C-Deklarationen und -Definitionen | Microsoft Docs"
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
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# C-Deklarationen und -Definitionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine "Deklaration" erstellt eine Zuordnung zwischen einer bestimmten Variable, einer Funktion oder einem Typ und den zugehörigen Attributen.  [Übersicht über Deklarationen](../c-language/overview-of-declarations.md) gibt die ANSI\-Syntax für das `declaration`\-Nichtterminal an.  Eine Deklaration gibt auch an, wo und wann auf einen Bezeichner zugegriffen werden kann \(die "Verknüpfung" eines Bezeichners\).  Weitere Informationen zu Verknüpfungen finden Sie unter [Lebensdauer, Bereich, Sichtbarkeit und Verknüpfung](../c-language/lifetime-scope-visibility-and-linkage.md).  
  
 Eine Definition einer Variablen erstellt die gleichen Zuordnungen wie eine Deklaration, bewirkt jedoch auch, dass Speicher für die Variable zugeordnet wird.  
  
 Beispielsweise werden `main`\-, `find`\- und `count`\-Funktionen sowie `var`\- und `val`\-Variablen in einer Quelldatei in dieser Reihenfolge definiert:  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 Die Variablen `var` und `val` können in den Funktionen `find` und `count` verwendet werden; weitere Deklarationen sind nicht erforderlich.  Diese Namen sind jedoch in `main` nicht sichtbar \(auf sie kann nicht zugegriffen werden\).  
  
## Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)