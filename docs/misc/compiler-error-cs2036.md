---
title: "Compilerfehler CS2036"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS2036"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2036"
ms.assetid: 44b73be4-b792-4735-bdbd-bd757ab22683
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS2036
Bei Verwendung der \/pdb\-Option muss auch die \/debug\-Option verwendet werden.  
  
 Programmdatenbankdateien werden nur für Debugbuilds generiert. Die **\/pdb**\-Option ist daher in einer Verkaufsversion bedeutungslos.  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie die **\/debug**\-Compileroption hinzu.  
  
-   Entfernen Sie die **\/pdb**\-Compileroption.  
  
## Beispiel  
 Im folgenden Beispiel wird CS2036 generiert, wenn die Kompilierung mit der **\/pdb**\-Option ohne die \/debug\-Option erfolgt:  
  
```  
// cs2036.cs // Compile with: /pdb // CS2036 class Test { public static int Main() { return 1; } }  
```  
  
## Siehe auch  
 [\/pdb \(Specify Debug Symbol File\)](../Topic/-pdb%20\(C%23%20Compiler%20Options\).md)   
 [\/debug \(Emit Debugging Information\)](../Topic/-debug%20\(C%23%20Compiler%20Options\).md)