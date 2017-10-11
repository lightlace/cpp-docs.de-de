---
title: Compilerfehler C2676 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2676
dev_langs:
- C++
helpviewer_keywords:
- C2676
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ed21b76da0834ff4a2aaa8af647d791fdaac075a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2676"></a>Compilerfehler C2676
Binärer 'Operator': 'Typ' definiert diesen Operator oder eine Konvertierung in einen für den vordefinierten Operator geeigneten Typ nicht  
  
 Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2676 generiert.  
  
```  
// C2676.cpp  
// C2676 expected  
struct C {  
   C();  
} c;  
  
struct D {  
   D();  
   D operator >>( C& ){return * new D;}  
   D operator <<( C& ){return * new D;}  
} d;  
  
struct E {  
   // operator int();  
};  
  
int main() {  
   d >> c;  
   d << c;  
   E e1, e2;  
   e1 == e2;   // uncomment operator int in class E, then  
               // it is OK even though neither E::operator==(E) nor   
               // operator==(E, E) defined. Uses the conversion to int   
               // and then the builtin-operator==(int, int)  
}  
```  
  
## <a name="example"></a>Beispiel  
 C2676 kann auch bei dem Versuch auftreten, im `this`-Zeiger eines Referenztyps eine Zeigerarithmetik auszuführen.  
  
 Der `this`-Zeiger tritt in einem Referenztyp als Handletyp auf. Weitere Informationen finden Sie unter [Semantik dieses Zeigers](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 Im folgenden Beispiel wird C2676 generiert.  
  
```  
// C2676_a.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct A {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
  
   A() {  
      Console::WriteLine("{0}", this + 3.3);   // C2676  
      Console::WriteLine("{0}", this[3.3]);   // OK  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
}  
```
