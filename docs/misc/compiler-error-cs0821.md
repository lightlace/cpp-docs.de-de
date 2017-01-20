---
title: "Compilerfehler CS0821"
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
  - "CS0821"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0821"
ms.assetid: ef449115-93e8-4fa5-848a-d30dc7f68ddf
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0821
Implizit typisierte lokale Variablen können nicht als 'fixed' deklariert werden.  
  
 Implizit typisierte lokale Variablen und anonyme Typen werden im `fixed`\-Kontext nicht unterstützt.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie den `fixed`\-Modifizierer aus der Variablen, oder weisen Sie der Variablen einen expliziten Typ zu.  
  
## Beispiel  
 Mit dem folgenden Code wird der Fehler CS0821 generiert:  
  
```  
class A { static int x; public static int Main() { unsafe { fixed (var p = &x) { } } return -1; } }  
```  
  
## Siehe auch  
 [Implizit typisierte lokale Variablen](../Topic/Implicitly%20Typed%20Local%20Variables%20\(C%23%20Programming%20Guide\).md)