---
title: "Compilerfehler C2255"
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
  - "C2255"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2255"
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2255
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Element": außerhalb einer Klassendefinition nicht zulässig.  
  
 Beispielsweise wird eine Funktion, die keine Memberfunktion ist, als `friend` deklariert.  
  
 Im folgenden Beispiel wird C2255 generiert:  
  
```  
// C2255.cpp // compile with: /c class A { private: void func1(); friend void func2(); }; friend void func1() {}   // C2255 void func2(){}  
```