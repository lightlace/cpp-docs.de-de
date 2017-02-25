---
title: "Compilerwarnung (Stufe 4) C4510 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4510"
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Standardkonstruktor konnte nicht generiert werden  
  
 Der Compiler kann keinen Standardkonstruktor für die angegebene Klasse generieren, und es wurde kein benutzerdefinierter Konstruktor erstellt.  Sie haben keine Möglichkeit, Objekte dieses Typs zu erstellen.  
  
 Es gibt mehrere Situationen, in denen der Compiler keinen Standardkonstruktor generieren kann, z. B. wenn Folgendes gegeben ist:  
  
-   Ein Datenmember vom Typ `const`.  
  
-   Ein Datenmember, der ein Verweis ist.  
  
 Sie müssen für die Klasse, durch die diese Member initialisiert werden, einen benutzerdefinierten Standardkonstruktor erstellen.  
  
 Im folgenden Beispiel wird C4510 generiert:  
  
```  
// C4510.cpp  
// compile with: /W4  
struct A {  
   const int i;  
   int &j;  
   A& operator=( const A& ); // C4510 expected  
   // uncomment the following line to resolve this C4510  
   // A(int ii, int &jj) : i(ii), j(jj) {}  
};   // C4510  
  
int main() {  
}  
```