---
title: "void (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "void"
  - "void_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionen [C++], void"
  - "Zeiger, void"
  - "void-Schlüsselwort [C++]"
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# void (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn es als Funktionsrückgabetyp verwendet wird, legt das `void`\-Schlüsselwort fest, dass die Funktion keinen Wert zurückgibt.  Wenn es für die Parameterliste einer Funktion verwendet wird, gibt "void" an, dass die Funktion keine Parameter akzeptiert.  Bei Verwendung in der Deklaration eines Zeigers gibt "void" an, dass der Zeiger "universal" ist.  
  
 Wenn der Typ eines Zeigers **void \*** ist, kann der Zeiger auf jede Variable verweisen, die nicht mit dem Schlüsselwort **const** oder `volatile` deklariert wird.  Ein void\-Zeiger kann nicht dereferenziert werden, es sei denn, er wird in einen anderen Typ umgewandelt.  Ein void\-Zeiger kann in jeden anderen Datenzeigertyp konvertiert werden.  
  
 Ein void\-Zeiger kann auf eine Funktion, jedoch nicht auf einen Klassenmember in C\+\+ zeigen.  
  
 Eine Variable vom Typ "void" kann nicht deklariert werden.  
  
## Beispiel  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Zeiger auf Typ "void"](../misc/pointers-to-type-void.md)   
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)