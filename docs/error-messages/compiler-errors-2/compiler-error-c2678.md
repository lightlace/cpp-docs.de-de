---
title: Compilerfehler Fehler C2678 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2678
dev_langs:
- C++
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fb294e567f759225a2899d39f2adaa7211d8d93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2678"></a>Compilerfehler Fehler C2678
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
