---
title: "Compilerfehler C2575 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2575"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2575"
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2575
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Nur Memberfunktionen und Basisklasse können virtuell sein  
  
 Eine globale Funktion oder Klasse ist als `virtual` deklariert.  Dies ist nicht zulässig.  
  
 Im folgenden Beispiel wird C2575 generiert:  
  
```  
// C2575.cpp  
// compile with: /c  
virtual void func() {}   // C2575  
  
void func2() {}  
struct A {  
   virtual void func2(){}  
};  
```