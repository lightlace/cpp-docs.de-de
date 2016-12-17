---
title: "Lvalues und Rvalues"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "L-Werte"
  - "R-Werte"
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Lvalues und Rvalues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jeder C\+\+\-Ausdruck ist entweder ein lvalue oder einen rvalue.  Ein lvalue verweist auf ein Objekt an, das über einen einzelnen Ausdruck hinaus beibehalten wird.  Sie können sich einen lvalue als ein Objekt vorstellen, das über einen Namen verfügt.  Alle Variablen, einschließlich nicht veränderbarer \(`const`\) Variablen, sind lvalues.  Ein rvalue ist ein temporärer Wert, der nicht über den Ausdruck hinaus beibehalten wird, der diesen nutzt.  Das folgende Beispiel soll den Unterschied zwischen lvalues und rvalues verdeutlichen:  
  
```  
// lvalues_and_rvalues1.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main()  
{  
   int x = 3 + 4;  
   cout << x << endl;  
}  
```  
  
 In diesem Beispiel ist `x` ein lvalue, da er über den Ausdruck hinaus beibehalten wird, der ihn definiert.  Der Ausdruck `3 + 4` ist ein rvalue, weil er zu einem temporären Wert auswertet, der nicht über den Ausdruck hinaus beibehalten wird, der ihn definiert.  
  
 Das folgende Beispiel zeigt mehrere korrekte und falsche Verwendungen von lvalues und rvalues:  
  
```  
// lvalues_and_rvalues2.cpp  
int main()  
{  
   int i, j, *p;  
  
   // Correct usage: the variable i is an lvalue.  
   i = 7;  
  
   // Incorrect usage: The left operand must be an lvalue (C2106).  
   7 = i; // C2106  
   j * 4 = 7; // C2106  
  
   // Correct usage: the dereferenced pointer is an lvalue.  
   *p = i;   
  
   const int ci = 7;  
   // Incorrect usage: the variable is a non-modifiable lvalue (C3892).  
   ci = 9; // C3892  
  
   // Correct usage: the conditional operator returns an lvalue.  
   ((i < 3) ? i : j) = 7;  
}  
```  
  
> [!NOTE]
>  Die Beispiele zu diesem Thema veranschaulichen die korrekte und falsche Verwendung, wenn Operatoren nicht überladen werden.  Indem Sie Operatoren überladen, können Sie aus einem Ausdruck wie `j * 4` einen lvalue machen.  
  
 Die Begriffe *lvalue* und *rvalue* werden häufig in Bezug auf Objektverweise verwendet.  Weitere Informationen über Verweise finden Sie unter [Lvalue\-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md) und [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Siehe auch  
 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)   
 [Lvalue\-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md)