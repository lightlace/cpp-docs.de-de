---
title: "Compilerfehler C2550 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2550"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2550"
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2550
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Initialisiererlisten für Konstruktoren dürfen nur in Konstruktordefinition stehen  
  
 Die Initialisiererliste einer Basisklasse wurde für die Definition einer Funktion verwendet, die kein Konstruktor ist.  
  
 Im folgenden Beispiel wird C2550 generiert:  
  
```  
// C2550.cpp  
// compile with: /c  
class C {  
public:  
   C();  
};  
  
class D : public C {  
public:  
   D();  
   void func();  
};  
  
void D::func() : C() {}  // C2550  
D::D() : C() {}   // OK  
```