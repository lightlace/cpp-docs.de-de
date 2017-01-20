---
title: "Compilerfehler C3217"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3217"
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"param": Der generische Parameter kann in dieser Deklaration nicht eingeschränkt werden.  
  
 Eine Einschränkung war falsch formatiert. Der generische Einschränkungsparameter muss mit dem generischen Klassenvorlagenparameter übereinstimmen.  
  
 Im folgenden Beispiel wird C3217 generiert:  
  
```  
// C3217.cpp // compile with: /clr interface struct A {}; generic <class T> ref class C { generic <class T1> where T : A   // C3217 void f(); };  
```  
  
 Das folgende Beispiel zeigt eine mögliche Lösung:  
  
```  
// C3217b.cpp // compile with: /clr /c interface struct A {}; generic <class T> ref class C { generic <class T1> where T1 : A void f(); };  
```