---
title: Compilerfehler Fehler C2027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be3c85d2ffbd3fffe4e1e6ce6dafc615f199c00a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167443"
---
# <a name="compiler-error-c2027"></a>Compilerfehler Fehler C2027
Verwenden eines undefinierten Typs 'Typ'  
  
 Ein Typ kann nicht verwendet werden, bis er definiert ist. Um den Fehler zu beheben, achten Sie darauf, dass der Typ vollständig definiert ist, bevor auf Sie verwiesen wird.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2027 generiert.  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## <a name="example"></a>Beispiel  
 Es ist möglich, deklarieren Sie einen Zeiger auf einen Typ deklariert, aber nicht definiert.  Visual C++, nicht jedoch einen Verweis auf einen undefinierten Typ.  
  
 Im folgende Beispiel wird C2027 generiert.  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```