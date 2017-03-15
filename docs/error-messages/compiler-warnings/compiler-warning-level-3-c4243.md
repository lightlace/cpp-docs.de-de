---
title: "Compilerwarnung (Stufe 3) C4243 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4243"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4243"
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 3) C4243
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konvertierungstyp'\-Konvertierung von 'Typ1' in 'Typ2' existiert, ist aber nicht verfügbar  
  
 Ein Zeiger auf eine abgeleitete Klasse wurde in einen Zeiger auf eine Basisklasse konvertiert, die abgeleitete Klasse erbt jedoch die Basisklasse mit dem Zugriff `private` oder `protected`.  
  
 Im folgenden Beispiel wird C4243 generiert:  
  
```  
// C4243.cpp  
// compile with: /W3  
// C4243 expected  
struct B {  
   int f() {  
      return 0;  
   };  
};  
  
struct D : private B {};  
struct E : public B {};  
  
int main() {  
   // Delete the following 2 lines to resolve.  
   int (D::* d)() = (int(D::*)()) &B::f;   
   d;  
  
   int (E::* e)() = (int(E::*)()) &B::f; // OK  
   e;  
}  
```