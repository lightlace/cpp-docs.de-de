---
title: Compilerfehler Fehler C2668 | Microsoft Docs
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2668
dev_langs:
- C++
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 48af783aab38f7d314d0b8cf45d876e6a8682030
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2668"></a>Compilerfehler Fehler C2668
'Funktion': Mehrdeutiger Aufruf einer überladenen Funktion  
  
 Der Aufruf angegebenen überladenen Funktion konnte nicht aufgelöst werden. Sie möchten möglicherweise eine oder mehrere der tatsächliche Parameter explizit umgewandelt.  
  
 Sie erhalten diesen Fehler auch mithilfe der Vorlage. Wenn Sie in der gleichen Klasse Sie eine reguläre Memberfunktion und eine aus einer Vorlage gebildete Memberfunktion mit der gleichen Signatur verfügen, muss aus einer Vorlage gebildete eine erste stammen. Dies ist eine Einschränkung des die aktuelle Implementierung von Visual C++.  
  
 Finden Sie für partielle Reihenfolge von Funktionsvorlagen in der Knowledge Base-Artikel Q240869 für Weitere Informationen.  
  
 Wenn Sie eine ATL-Projekt, das ein COM-Objekt unterstützender enthält erstellen `ISupportErrorInfo`, finden Sie im Knowledge Base-Artikel Q243298.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2668 generiert:  
  
```  
// C2668.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
  
void func( X, X ){}  
void func( A, B ){}  
D d;  
int main() {  
   func( d, d );   // C2668 D has an A, B, and X   
   func( (X)d, (X)d );   // OK, uses func( X, X )  
}  
```  
  
## <a name="example"></a>Beispiel  
 Eine weitere Möglichkeit zum Beheben dieses Fehlers ist mit einem [using-Deklaration](../../cpp/using-declaration.md):  
  
```  
// C2668b.cpp  
// compile with: /EHsc /c  
// C2668 expected  
#include <iostream>  
class TypeA {  
public:  
   TypeA(int value) {}  
};  
  
class TypeB {  
   TypeB(int intValue);  
   TypeB(double dbValue);  
};  
  
class TestCase {  
public:  
   void AssertEqual(long expected, long actual, std::string  
                    conditionExpression = "");  
};  
  
class AppTestCase : public TestCase {  
public:  
   // Uncomment the following line to resolve.  
   // using TestCase::AssertEqual;  
   void AssertEqual(const TypeA expected, const TypeA actual,  
                    std::string conditionExpression = "");  
   void AssertEqual(const TypeB expected, const TypeB actual,  
                    std::string conditionExpression = "");  
};  
  
class MyTestCase : public AppTestCase {  
   void TestSomething() {  
      int actual = 0;  
      AssertEqual(0, actual, "Value");  
   }  
};  
```  
  
## <a name="example"></a>Beispiel  
 Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Visual Studio .NET 2003 durchgeführt wurde, die generiert werden: Mehrdeutige Konvertierung bei der Umwandlung von Konstanten 0.  
  
 Konvertierung in eine Umwandlung, die mit dem konstanten Wert 0 ist mehrdeutig, da Int eine Konvertierung sowohl in lang und Void * erfordert. Um diesen Fehler zu beheben, wandeln Sie 0, der genaue Typ des der Funktionsparameter, dem sie für die verwendet wird, damit keine Konvertierungen müssen ausgeführt werden (in diesem Code wird in der Visual Studio .NET 2003 und Visual Studio .NET Versionen von Visual C++ gültig sein).  
  
```  
// C2668c.cpp  
#include "stdio.h"  
void f(long) {  
   printf_s("in f(long)\n");  
}  
void f(void*) {  
   printf_s("in f(void*)\n");  
}  
int main() {  
   f((int)0);   // C2668  
  
   // OK  
   f((long)0);  
   f((void*)0);  
}  
```  
  
## <a name="example"></a>Beispiel  
 Dieser Fehler kann auftreten, da die CRT jetzt "float" und doppelte Forms alle mathematischen Funktionen verfügt.  
  
```  
// C2668d.cpp  
#include <math.h>  
int main() {  
   int i = 0;  
   float f;  
   f = cos(i);   // C2668  
   f = cos((float)i);   // OK  
}  
```  
  
## <a name="example"></a>Beispiel  
 Dieser Fehler kann auftreten, da die pow (Int, Int) aus math.h in der CRT entfernt wurde.  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```

## <a name="example"></a>Beispiel  
Dieser Code in Visual Studio 2015 ist erfolgreich, jedoch wird in Visual Studio 2017 und höher mit C2668 schlägt fehl. In Visual Studio 2015 behandelt der Compiler fälschlicherweise eine copy-list-Initialisierung auf die gleiche Weise wie eine Kopierinitialisierung. Er konvertiert nur die Konstruktoren für die Überladungsauflösung. 

```
C++
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```
