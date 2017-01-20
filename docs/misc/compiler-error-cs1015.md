---
title: "Compilerfehler CS1015"
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
  - "CS1015"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1015"
ms.assetid: 53179feb-e8be-41e0-bb0b-f7879e9fa613
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1015
Objekt, Zeichenfolge oder Klassentyp erwartet.  
  
 Es wurde versucht, einen vordefinierten Datentyp in einen [catch](../Topic/try-catch%20\(C%23%20Reference\).md)\-Block zu übergeben. An einen <xref:System.Exception?displayProperty=fullName>\-Block können nur Datentypen übergeben werden, die von `catch` abgeleitet wurden. Weitere Informationen zu Ausnahmen finden Sie unter [Ausnahmebehandlungsanweisungen](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS1015 generiert:  
  
```  
// CS1015.cs class Sample { static void Main() { try { } catch(int)   // CS1015, int is not derived from System.Exception { } } }  
```