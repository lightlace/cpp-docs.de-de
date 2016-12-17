---
title: "Compilerfehler CS0017"
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
  - "CS0017"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0017"
ms.assetid: 5e2a3eb3-6f6e-485d-8293-ceabea4d6905
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0017
Für das Programm „Ausgabedateiname“ sind mehrere Einstiegspunkte definiert. Kompilieren Sie mit „\/main“, um den Typ anzugeben, der den Einstiegspunkt enthält.  
  
 Ein Programm kann nur eine [Main](../Topic/Main\(\)%20and%20Command-Line%20Arguments%20\(C%23%20Programming%20Guide\).md)\-Methode besitzen.  
  
 Um diesen Fehler zu beheben, löschen Sie entweder alle Main\-Methoden im Code \(bis auf eine\), oder verwenden Sie die [\/main](../Topic/-main%20\(C%23%20Compiler%20Options\).md)\-Compileroption, um die zu verwendende Main\-Methode anzugeben.  
  
 Im folgenden Beispiel wird CS0017 generiert:  
  
```  
// CS0017.cs // compile with: /target:exe public class clx { static public void Main() { } } public class cly { public static void Main()   // CS0017, delete one Main or use /main { } }  
```