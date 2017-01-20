---
title: "Compilerwarnung (Stufe 1) CS3000"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS3000"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3000"
ms.assetid: 37cdd3dc-8481-4e29-b78c-281baeca2d64
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 1) CS3000
Methoden mit Variablenargumenten sind nicht CLS\-kompatibel.  
  
 Die in der Methode verwendeten Argumente machen Features verfügbar, die nicht in der Common Language Specification \(CLS\) enthalten sind. Weitere Informationen zur CLS\-Kompatibilität finden Sie unter [Schreiben von CLS\-kompatiblem Code](assetId:///4c705105-69a2-4e5e-b24e-0633bc32c7f3).  
  
 Im folgenden Beispiel wird die Warnung CS3000 generiert.  
  
```  
// CS3000.cs // compile with: /target:library // CS3000 expected [assembly:System.CLSCompliant(true)] public class Test { public void AddABunchOfInts( __arglist ) {}   // CS3000 }  
```