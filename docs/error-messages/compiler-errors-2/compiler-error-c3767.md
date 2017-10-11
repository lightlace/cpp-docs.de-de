---
title: Compilerfehler C3767 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3767
dev_langs:
- C++
helpviewer_keywords:
- C3767
ms.assetid: 5247cdcd-639c-4527-bd37-37e74c4e8fab
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6ebbcbe30a0c9359116d259c36d702a968b333c9
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3767"></a>Compilerfehler C3767
'Funktion': Auf mögliche Funktion(en) kann nicht zugegriffen werden  
  
 Bei einer in einer Klasse definierten Friend-Funktion wird nicht davon ausgegangen, dass sie so behandelt wird, als wäre sie im globalen Gültigkeitsbereich des Namespaces definiert und deklariert worden. Sie kann jedoch mittels einer argumentbezogenen Suche gefunden werden.  
  
 C3767 kann auch von einer wichtigen Änderung verursacht worden sein: systemeigene Typen sind nun standardmäßig im privaten eine **"/ CLR"** -Kompilierung finden Sie unter [geben Sichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3767 generiert:  
  
```  
// C3767a.cpp  
// compile with: /clr  
using namespace System;  
public delegate void TestDel();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;  
};  
  
public ref class MyClass2 : public MyClass {  
public:  
   void Test() {  
      MyClass^ patient = gcnew MyClass;  
      patient->MyClass_Event();  
    }  
};  
  
int main() {  
   MyClass^ x = gcnew MyClass;  
   x->MyClass_Event();   // C3767  
  
   // OK  
   MyClass2^ y = gcnew MyClass2();  
   y->Test();  
};  
```  
  
 Im folgenden Beispiel wird C3767 generiert:  
  
```  
// C3767c.cpp  
// compile with: /clr /c  
  
ref class Base  {  
protected:  
   void Method() {  
      System::Console::WriteLine("protected");  
   }  
};  
  
ref class Der : public Base {  
   void Method() {  
      ((Base^)this)->Method();   // C3767  
      // try the following line instead  
      // Base::Method();  
   }  
};  
```  
  
 In Visual C++ .NET 2002 geändert der Compiler die Möglichkeit, die sie nach Symbolen gesucht. In einigen Fällen suchte der Compiler automatisch nach Symbolen in einem bestimmten Namespace. Nun wird die argumentbezogene Suche verwendet.  
  
 Im folgenden Beispiel wird C3767 generiert:  
  
```  
// C3767e.cpp  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3767 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
 Für Code, der in Visual C++ .NET 2003 und Visual C++ .NET 2002 gültig ist, die Friend-Funktion im Klassenbereich deklarieren und im Namespacebereich definieren:  
  
```  
// C3767f.cpp  
class MyClass {  
   int m_private;  
   friend void func();  
};  
  
void func() {  
   MyClass s;  
   s.m_private = 0;  
}  
  
int main() {  
   func();  
}  
```
