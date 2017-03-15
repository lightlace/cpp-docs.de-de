---
title: "Compilerfehler C2668 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2668"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2668"
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Compilerfehler C2668
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Mehrdeutiger Aufruf einer überladenen Funktion  
  
 Der angegebene Aufruf der überladenen Funktion lässt sich nicht auflösen.  Sie können eine explizite Typumwandlung für einen oder mehrere der übergebenen Parameter durchführen.  
  
 Dieser Fehler kann auch durch die Verwendung von Vorlagen hervorgerufen werden.  Wenn in einer Klasse eine reguläre Memberfunktion und eine aus einer Vorlage gebildete Memberfunktion mit derselben Signatur enthalten ist, muss letztere zuerst genannt werden.  Diese Beschränkung gilt für die aktuelle Implementierung von Visual C\+\+.  
  
 Weitere Informationen zur teilweisen Anordnung von Funktionsvorlagen finden Sie im Knowledge Base\-Artikel Q240869.  
  
 Informationen zum Erstellen eines ATL\-Projekts mit einem COM\-Objekt, das `ISupportErrorInfo` unterstützt, finden Sie im Knowledge Base\-Artikel Q243298 \(nur auf Englisch verfügbar\).  
  
## Beispiel  
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
  
## Beispiel  
 Eine weitere Möglichkeit zur Behebung dieses Fehlers besteht in der Verwendung einer [using\-Deklaration](../../cpp/using-declaration.md):  
  
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
  
## Beispiel  
 Dieser Fehler kann auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben werden: mehrdeutige Konvertierung bei Typumwandlung der Konstanten 0.  
  
 Die Konvertierung für eine Typumwandlung mittels der Konstanten 0 ist mehrdeutig, da `int` eine Konvertierung sowohl in **long** als auch in **void\*** erfordert.  Um diesen Fehler zu beheben, wandeln Sie 0 in den exakten Typ des Funktionsparameters um, für den die Konstante verwendet wird. Folglich müssen keine Konvertierungen erfolgen \(dieser Code ist in der Visual Studio .NET 2003\-Version und der Visual Studio .NET\-Version von Visual C\+\+ zulässig\).  
  
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
  
## Beispiel  
 Dieser Fehler auch auftreten, weil die CRT jetzt für alle mathematischen Funktionen die Varianten "float" und "double" bereitstellt.  
  
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
  
## Beispiel  
 Dieser Fehler kann auftreten, da pow\(int, int\) in der CRT aus "math.h" entfernt wurde.  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```