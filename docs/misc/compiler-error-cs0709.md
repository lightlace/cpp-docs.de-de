---
title: "Compilerfehler CS0709"
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
  - "CS0709"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0709"
ms.assetid: 91040f55-a060-4cc3-b830-f6b771af28d7
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0709
'abgeleitete Klasse': die Ableitung aus einer statischen Klasse 'basisklasse' ist nicht möglich  
  
 Aus eine statischen Klasse kann keine Instanziierung oder Ableitung erfolgen. Das bedeutet, dass eine statische Klasse nicht die Basisklasse einer anderen Klasse bilden kann.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0709 generiert:  
  
```  
// CS0709.cs // compile with: /target:library public static class Base {} public class Derived : Base {}   // CS0709  
```