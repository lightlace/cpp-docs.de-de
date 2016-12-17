---
title: "Compilerfehler CS0227"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0227"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0227"
ms.assetid: b595a1c9-8204-4ff7-a1d0-258b0b1d6ff7
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0227
Unsicherer Code wird nur angezeigt, wenn mit \/unsafe kompiliert wird.  
  
 Wenn Quellcode das [unsafe](../Topic/unsafe%20\(C%23%20Reference\).md)\-Schlüsselwort enthält, muss die [\/unsafe](../Topic/-unsafe%20\(C%23%20Compiler%20Options\).md)\-Compileroption ebenfalls verwendet werden. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../Topic/Unsafe%20Code%20and%20Pointers%20\(C%23%20Programming%20Guide\).md).  
  
 Klicken Sie zum Festlegen der unsafe\-Option in [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] im Hauptmenü auf **Projekt**, wählen Sie den Bereich **Erstellen** aus, und aktivieren Sie das Kontrollkästchen „Unsicheren Code zulassen“.  
  
 Im folgenden Beispiel wird bei der Kompilierung ohne **\/unsafe** der Fehler CS0227 generiert:  
  
```  
// CS0227.cs public class MyClass { unsafe public static void Main()   // CS0227 { } }  
```  
  
## Siehe auch  
 [C\# Compiler Errors](../Topic/C%23%20Compiler%20Errors.md)