---
title: "Compilerwarnung (Stufe 1) C4584 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4584"
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse1': Basisklasse 'Klasse2' ist bereits eine Basisklasse von 'Klasse3'  
  
 Die definierte Klasse erbt von zwei Klassen, die auch untereinander erben.  Beispiel:  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 In diesem Fall würde eine Warnung für Klasse C ausgegeben, da diese sowohl von Klasse A als auch von Klasse B erbt, wobei Klasse B auch von Klasse A erbt.  Diese Warnung weist Sie darauf hin, dass Sie die Verwendung von Membern, die aus diesen Basisklassen gebildet wurden, vollständig kennzeichnen müssen. Andernfalls tritt ein Compilerfehler auf, da nicht klar ist, auf welchen Klassenmember Sie sich beziehen.