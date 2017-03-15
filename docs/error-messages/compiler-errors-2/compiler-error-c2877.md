---
title: "Compilerfehler C2877 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2877"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2877"
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2877
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf 'Symbol' kann von 'Klasse' aus nicht zugegriffen werden  
  
 Auf alle Member, die von einer Basisklasse abgeleitet wurden, muss in der abgeleiteten Klasse zugegriffen werden können.  
  
 Im folgenden Beispiel wird C2877 generiert:  
  
```  
// C2877.cpp  
// compile with: /c  
class A {  
private:  
   int a;  
};  
  
class B : public A {  
   using A::a;   // C2877  
};  
```