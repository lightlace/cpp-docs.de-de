---
title: "Compilerfehler CS0736"
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
  - "CS0736"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0736"
ms.assetid: 06b14feb-81d5-495f-ab2d-6dc3f5e7216f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0736
"Typname" implementiert den Schnittstellenmember "Membername" nicht. "Methodenname" ist statisch und kann daher keinen Schnittstellenmember implementieren.  
  
 Dieser Fehler wird generiert, wenn eine statische Methode implizit oder explizit als Implementierung eines Schnittstellenmembers deklariert wird.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den [statischen](../Topic/static%20\(C%23%20Reference\).md) Modifizierer aus der Methodendeklaration.  
  
-   Ändern Sie den Namen der Schnittstellenmethode.  
  
-   Definieren Sie den enthaltenden Typ neu, damit er nicht von der Schnittstelle erbt.  
  
## Beispiel  
 Durch den folgenden Code wird CS0736 generiert, weil `Program.testMethod` als statisch deklariert wird:  
  
```  
// cs0736.cs namespace CS0736 { interface ITest { int testMethod(int x); } class Program : ITest // CS0736 { public static int testMethod(int x) { return 0; } // Try the following line instead. // public int testMethod(int x) { return 0; } public static void Main() { } } }  
```  
  
## Siehe auch  
 [Schnittstellen](../Topic/Interfaces%20\(C%23%20Programming%20Guide\).md)