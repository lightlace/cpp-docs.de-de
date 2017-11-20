---
title: "Compiler Warning (level 1) C4669 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4669"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4669"
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compiler Warning (level 1) C4669
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Umwandlung" : Unsichere Konvertierung: "Klasse" ist ein verwaltetes Objekt oder ein Objekt mit dem Typ WinRT.  
  
 Eine Umwandlung beinhaltet eine Windows\-Runtime oder einen verwalteten Typ.  Der Compiler schließt die Umwandlung anhand einer bitweisen Kopie des einen Zeiger zu einem anderen ab, bietet jedoch keine weiteren Überprüfungen.  Um diese Warnung zu vermeiden, sollten Sie keine Klassen mit verwalteten Members oder Windows\-Runtime\-Typen umwandeln.  
  
 Im folgenden Beispiel wird C4669 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C4669.cpp  
// compile with: /clr /W1  
ref struct A {  
   int i;  
   Object ^ pObj;   // remove the managed member to fix the warning  
};  
  
ref struct B {  
   int j;  
};  
  
int main() {  
   A ^ a = gcnew A;  
   B ^ b = reinterpret_cast<B ^>(a);   // C4669  
}  
```