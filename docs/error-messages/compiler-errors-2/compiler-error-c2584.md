---
title: "Compilerfehler C2584 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2584"
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Kein Zugriff auf direkte Basisklasse 'Basis2', da diese bereits Basisklasse von 'Basis1' ist  
  
 `Class` ist bereits direkt von `Base1` abgeleitet.  `Base2` wird auch von `Base1` abgeleitet.  `Class` kann nicht von `Base2` abgeleitet werden, da dies ein erneutes \(indirektes\) Erben von `Base1` bedeuten würde. Dies ist nicht zulässig, da `Base1` bereits eine direkte Basisklasse ist.  
  
## Beispiel  
 Im folgenden Beispiel wird C2584 generiert.  
  
```  
// C2584.cpp  
// compile with: /c  
struct A1 {  
   virtual int MyFunction();  
};  
  
struct A2 {  
    virtual int MyFunction();  
};  
  
struct B1: public virtual A1, virtual A2 {  
    virtual int MyFunction();  
};  
  
struct B2: public virtual A2, virtual A1 {  
    virtual int MyFunction();  
};  
  
struct C: virtual B1, B2 {  
    virtual int MyFunction();  
};  
  
struct Z : virtual B2, virtual C {   // C2584  
// try the following line insted  
// struct Z : virtual C {  
    virtual int MyFunction();  
};  
```