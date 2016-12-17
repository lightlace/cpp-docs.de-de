---
title: "Compilerfehler CS0754"
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
  - "CS0754"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0754"
ms.assetid: c83e04b5-6ab5-45c2-805e-0ba4f041d506
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0754
Eine partielle Methode darf Schnittstellenmethoden nicht explizit implementieren.  
  
 Eine partielle Methode kann nicht als explizite Implementierung einer in einer Schnittstelle definierten Methode deklariert werden.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die angegebene explizite Schnittstelle aus der Methodendeklaration.  
  
## Beispiel  
 Durch den folgenden Code wird der Fehler CS0754 ausgelöst:  
  
```  
// cs0754.cs using System; public interface IF { void Part(); } public partial class C : IF { partial void IF.Part(); //CS0754 public static int Main() { return 1; } }  
```  
  
## Siehe auch  
 [Explizite Schnittstellenimplementierung](../Topic/Explicit%20Interface%20Implementation%20\(C%23%20Programming%20Guide\).md)   
 [Partielle Klassen und Methoden](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md)