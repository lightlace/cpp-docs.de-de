---
title: "Compilerfehler C2583 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2583"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2583"
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2583
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': 'const\/volatile' 'this'\-Zeiger ist ungültig für Konstruktoren\/Destruktoren  
  
 Ein Konstruktor oder Destruktor ist als `const` oder `volatile` deklariert.  Dies ist nicht zulässig.  
  
 Im folgenden Beispiel wird C2583 generiert:  
  
```  
// C2583.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
   A() const;   // C2583  
  
   // try the following line instead  
   // A();  
};  
```