---
title: "Compilerfehler CS0752"
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
  - "CS0752"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0752"
ms.assetid: f9a373d6-31ed-42db-8206-80cbe9b8c546
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0752
Eine partielle Methode darf keine out\-Parameter enthalten.  
  
 Eine partielle Methode darf keinen [out](../Topic/out%20\(C%23%20Reference\).md)\-Parameter enthalten. Out\-Parameter sind nicht zulässig, da es beim Entfernen der partiellen Methode durch den Compiler keine Garantie gibt, dass der out\-Parameter jemals zugewiesen wird.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie den out\-Modifizierer aus dem Parameter, und verwenden Sie stattdessen der Rückgabewert der Methode. Andernfalls entfernen Sie den partiellen Modifizierer aus der Methodendeklaration.  
  
## Beispiel  
 Durch den folgenden Code wird der Fehler CS0752 ausgelöst:  
  
```  
// cs0752.cs public partial class C { partial void Part(out int num); // CS0752 // try the following line instead // partial void Part(int num); public static int Main() { return 1; } }  
```  
  
## Siehe auch  
 [Partielle Klassen und Methoden](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md)