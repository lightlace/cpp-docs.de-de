---
title: "Compilerfehler CS0316"
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
  - "CS0316"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0316"
ms.assetid: 8b70abbe-dd4f-473f-8dfe-f8309abef276
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0316
Der Parametername "Name" verursacht einen Konflikt mit einem automatisch generierten Parameternamen.  
  
 Reservierte Wörter können nicht als Parameternamen verwendet werden. Im folgenden Beispiel ist `value` ist ein reserviertes Wort im Kontext einer standardmäßigen Eigenschaft bzw. eines Indexeraccessors.  
  
### So beheben Sie diesen Fehler  
  
1.  Ändern Sie den Namen des Parameters.  
  
## Beispiel  
 Der folgende Code generiert CS0316:  
  
```  
// cs0316.cs // Compile with: /target:library public class Test { public int this[int value] // CS0316 { get { return 1; } set { } } }  
```  
  
## Siehe auch  
 [Indexer](../Topic/Indexers%20\(C%23%20Programming%20Guide\).md)   
 [C\#\-Schlüsselwörter](../Topic/C%23%20Keywords.md)