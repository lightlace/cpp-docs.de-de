---
title: "Compilerfehler CS0315"
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
  - "CS0315"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0315"
ms.assetid: 9bb1cab3-1dca-4467-978b-1ab310901a70
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0315
Der Typ "Werttyp" kann nicht als Typparameter "T" im generischen Typ oder in der generischen Methode "Typ oder Methode\<T\>" verwendet werden. Es gibt keine Boxing\-Konvertierung von "Werttyp" in "Verweistyp".  
  
 Dieser Fehler tritt auf, wenn Sie einen generischen Typ auf eine bestimmte Klasse beschränken und versuchen, eine Instanz dieser Klasse mithilfe eines Werttyps zu erstellen, der nicht implizit darin geschachtelt werden kann.  
  
### So beheben Sie diesen Fehler  
  
1.  Eine Lösung besteht darin, die Struktur als Klasse neu zu definieren.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0315 generiert:  
  
```  
// cs0315.cs public class ClassConstraint { } public struct ViolateClassConstraint { } public class Gen<T> where T : ClassConstraint { } public class Test { public static int Main() { Gen<ViolateClassConstraint> g = new Gen<ViolateClassConstraint>(); //CS0315 return 1; } }  
```  
  
## Siehe auch  
 [Einschränkungen für Typparameter](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md)   
 [Boxing und Unboxing](../Topic/Boxing%20and%20Unboxing%20\(C%23%20Programming%20Guide\).md)