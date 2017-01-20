---
title: "Compilerfehler CS0540"
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
  - "CS0540"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0540"
ms.assetid: 2da2cd4a-0ff1-45ea-bb72-ea078bc95dea
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0540
'Schnittstellenmember': Der enthaltende Typ implementiert die 'Schnittstelle'\-Schnittstelle nicht.  
  
 Sie haben versucht, einen Schnittstellenmember in einer [Klasse](../Topic/class%20\(C%23%20Reference\).md) zu implementieren, die nicht von der [Schnittstelle](../Topic/interface%20\(C%23%20Reference\).md) abgeleitet ist. Sie sollten die Implementierung des Schnittstellenmembers löschen oder die Schnittstelle der Basisklassenliste der Klasse hinzufügen.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0540 generiert:  
  
```  
// CS0540.cs interface I { void m(); } public class Clx { void I.m() {}   // CS0540 } // OK public class Cly : I { void I.m() {} public static void Main() {} }  
```  
  
## Beispiel  
 Im folgenden Beispiel wird CS0540 generiert:  
  
```  
// CS0540_b.cs using System; class C { void IDisposable.Dispose() {}   // CS0540 } class D : IDisposable { void IDisposable.Dispose() {} public void Dispose() {} static void Main() { using (D d = new D()) {} } }  
```