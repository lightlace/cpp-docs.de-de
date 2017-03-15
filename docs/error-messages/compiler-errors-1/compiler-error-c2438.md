---
title: "Compilerfehler C2438 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2438"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2438"
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2438
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Initialisierung statischer Klassendaten über Konstruktor nicht möglich  
  
 Ein Konstruktor wurde verwendet, um einen statischen Member einer Klasse zu initialisieren.  Statische Member sollten in einer Definition außerhalb der Klassendeklaration initialisiert werden.  
  
 Im folgenden Beispiel wird C2438 generiert:  
  
```  
// C2438.cpp  
struct X {  
   X(int i) : j(i) {}   // C2438  
   static int j;  
};  
  
int X::j;  
  
int main() {  
   X::j = 1;  
}  
```