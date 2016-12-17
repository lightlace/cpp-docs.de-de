---
title: "Compilerfehler CS0243"
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
  - "CS0243"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0243"
ms.assetid: 2506e4cb-dc26-46b4-a58c-ab6bf1601144
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0243
Das Conditional\-Attribut ist für 'Methode' nicht gültig, da es eine Überschreibungsmethode ist.  
  
 Das [Conditional](assetId:///e1c4913b-74d0-421a-8a6d-c14b3f0e68fb)\-Attribut für für Methoden nicht zulässig, die mit dem [override](../Topic/override%20\(C%23%20Reference\).md)\-Schlüsselwort gekennzeichnet sind. Weitere Informationen finden Sie unter [Wann müssen die Schlüsselwörter "override" und "new" verwendet werden?](../Topic/Knowing%20When%20to%20Use%20Override%20and%20New%20Keywords%20\(C%23%20Programming%20Guide\).md).  
  
 Der Compiler bindet niemals Überschreibungsmethoden. Er bindet nur die Basismethode und die Common Language Runtime ruft dann die Überschreibung entsprechend auf.  
  
 Im folgenden Beispiel wird CS0243 generiert:  
  
```  
// CS0243.cs // compile with: /target:library public class MyClass { public virtual void M() {} } public class MyClass2 : MyClass { [System.Diagnostics.ConditionalAttribute("MySymbol")]   // CS0243 // remove Conditional attribute or remove override keyword public override void M() {} }  
```