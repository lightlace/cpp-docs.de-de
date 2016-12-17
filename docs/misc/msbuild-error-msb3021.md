---
title: "MSBuild Error MSB3021"
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.Copy.Error"
helpviewer_keywords: 
  - "MSB3021"
ms.assetid: 8cb3a860-6916-4406-b5c7-b1106b44b92a
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3021
**Datei \<Datei\> kann nicht in \<Datei\> kopiert werden. '  \<Fehler\>'**  
  
 Die `Copy`\-Aufgabe kann die angegebene Datei nicht kopieren.  
  
### So beheben Sie diesen Fehler  
  
-   Überprüfen Sie, ob die Zieldatei durch eine andere Anwendung gesperrt \(in Gebrauch\) ist.  Stellen Sie sicher, dass Sie die Berechtigung haben, die Quelldatei zu lesen und die Zieldatei in den Zielordner zu schreiben.  Wenn der Zieldateipfad sehr lang ist, müssen Sie möglicherweise an einen anderen Speicherort kopieren.  
  
## Siehe auch  
 [Copy Task](../Topic/Copy%20Task.md)   
 [Tasks](../Topic/MSBuild%20Tasks.md)