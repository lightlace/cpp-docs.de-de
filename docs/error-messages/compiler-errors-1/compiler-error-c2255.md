---
title: "Compilerfehler C2255 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2255"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2255"
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2255
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Element": außerhalb einer Klassendefinition nicht zulässig.  
  
 Beispielsweise wird eine Funktion, die keine Memberfunktion ist, als `friend` deklariert.  
  
 Im folgenden Beispiel wird C2255 generiert:  
  
```  
// C2255.cpp // compile with: /c class A { private: void func1(); friend void func2(); }; friend void func1() {}   // C2255 void func2(){}  
```