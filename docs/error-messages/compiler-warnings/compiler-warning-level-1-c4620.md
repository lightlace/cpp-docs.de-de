---
title: "Compilerwarnung (Stufe 1) C4620"
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
  - "C4620"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4620"
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4620
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Keine Postfix\-Form von 'Operator \+\+' für den Typ 'Typ' gefunden, Präfix\-Form verwendet  
  
 Es ist kein Postfixinkrementoperator für den angegebenen Typ definiert. Der Compiler hat den überladenen Präfixoperator verwendet.  
  
 Diese Warnung kann vermieden werden, indem Sie einen Postfix\-`++`\-Operator definieren. Erstellen Sie eine Version des `++`\-Operators mit zwei Argumenten, wie hier gezeigt:  
  
```  
// C4620.cpp // compile with: /W1 class A { public: A(int nData) : m_nData(nData) { } A operator++() { m_nData -= 1; return *this; } // A operator++(int) // { //    A tmp = *this; //    m_nData -= 1; //    return tmp; // } private: int m_nData; }; int main() { A a(10); ++a; a++;   // C4620 }  
```