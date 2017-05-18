---
title: Compiler-Fehler C2678 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2678
dev_langs:
- C++
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ce8ee4a0b211bb90ed8f04184f2ac96962032436
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2678"></a>Compiler-Fehler C2678
Binärer „operator“: Es wurde kein Operator definiert, der einen linksseitigen Operanden vom Typ „type“ akzeptiert (oder keine geeignete Konvertierung möglich)  
  
 Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.  
  
## <a name="example"></a>Beispiel  
 C2678 kann auftreten, wenn der linke Operand konstant qualifiziert ist, der Operator jedoch definiert ist, ein nicht konstantes Argument zu verwenden.  
  
 Im folgenden Beispiel wird C2678 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2678a.cpp  
// Compile by using: cl /EHsc /W4 C2678a.cpp  
struct Combo {  
   int number;  
   char letter;  
};  
  
inline Combo& operator+=(Combo& lhs, int rhs) {  
   lhs.number += rhs;  
   return lhs;  
}  
  
int main() {  
   Combo const combo1{ 42, 'X' };  
   Combo combo2{ 13, 'Z' };  
  
   combo1 += 6; // C2678  
   combo2 += 9; // OK - operator+= matches non-const Combo  
}  
```  
  
## <a name="example"></a>Beispiel  
 C2678 kann auch auftreten, wenn Sie ein systemeigenes Member nicht verankern, bevor Sie eine Memberfunktion dafür aufrufen.  
  
 Im folgenden Beispiel wird C2678 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2678.cpp  
// compile with: /clr /c  
struct S { int _a; };  
  
ref class C {  
public:  
   void M( S param ) {  
      test = param;   // C2678  
  
      // OK  
      pin_ptr<S> ptest = &test;  
      *ptest = param;  
   }  
   S test;  
};  
```  

