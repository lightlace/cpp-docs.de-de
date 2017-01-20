---
title: "Compilerfehler CS0505"
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
  - "CS0505"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0505"
ms.assetid: e3cb9e33-7338-4869-859b-81d7439f0d23
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0505
'Member1': Überschreiben nicht möglich; 'Member2' ist keine Funktion.  
  
 Eine Klassendeklaration hat versucht, eine Nichtmethode in einer Basisklasse zu überschreiben. Bei Überschreibungen muss der Membertyp übereinstimmen. Wenn eine Methode mit demselben Namen wie für eine Methode in einer Basisklasse benötigt wird, verwenden Sie [new](../Topic/new%20\(C%23%20Reference\).md) \(und nicht [override](../Topic/override%20\(C%23%20Reference\).md)\) für die Deklaration der Methode in der Basisklasse.  
  
 Im folgenden Beispiel wird CS0505 generiert:  
  
```  
// CS0505.cs // compile with: /target:library public class clx { public int i; } public class cly : clx { public override int i() { return 0; }   // CS0505 }  
```