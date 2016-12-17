---
title: "MSBuild Error MSB3187"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.PlatformMismatch"
helpviewer_keywords: 
  - "MSB3187"
ms.assetid: c5e93c14-b099-4176-bf1b-dbecc47fb3fd
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3187
**MSB3187: Für die referenzierte '\<assembly\>'\-Assembly ist ein anderer Zielprozessor festgelegt als für die Anwendung.**  
  
 Diese Warnung wird generiert, wenn die Zielplattform \(Prozessorarchitektur\) der Anwendung auf neutral \(MSIL\) festgelegt ist und die Assembly, auf die verwiesen wird, nicht neutral ist, oder wenn die Architektur der Anwendung nicht neutral und die Abhängigkeit neutral ist.  Auch wenn die Plattform in beiden Fällen nicht neutral ist, müssen die Architekturen übereinstimmen.  Außerdem müssen die Architektur der Anwendung und der Einstiegspunktassembly immer übereinstimmen.  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Zielplattform \(Prozessorarchitektur\) der Anwendung mit der Architektur der Assemblys, auf die verwiesen wird, und der Architektur der Einstiegspunktassembly übereinstimmt.  
  
## Siehe auch  
 [Dialogfeld "Erweiterte Compilereinstellungen \(Visual Basic\)](../Topic/Advanced%20Compiler%20Settings%20Dialog%20Box%20\(Visual%20Basic\).md)   
 [Seite "Erstellen", Projekt\-Designer \(C\#\)](../Topic/Build%20Page,%20Project%20Designer%20\(C%23\).md)