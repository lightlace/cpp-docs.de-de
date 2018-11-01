---
title: Compilerfehler C2668
ms.date: 03/28/2017
f1_keywords:
- C2668
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
ms.openlocfilehash: 1920af8873578c63ab768dae4bcdf4d91fe7cd57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642221"
---
# <a name="compiler-error-c2668"></a>Compilerfehler C2668

'Funktion': Mehrdeutiger Aufruf einer überladenen Funktion

Der Aufruf angegebenen überladenen Funktion konnte nicht aufgelöst werden. Sie sollten mindestens eine der übergebenen Parameter explizit umgewandelt.

Sie können diesen Fehler auch mithilfe der Vorlage abrufen. Wenn Sie in der gleichen Klasse, Sie eine reguläre Memberfunktion und eine auf Vorlagen basierenden Memberfunktion mit der gleichen Signatur verfügen, muss die auf Vorlagen basierenden ein zuerst aufgeführt werden. Dies ist eine Einschränkung des die aktuelle Implementierung von Visual C++.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2668 generiert:

```cpp
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

```cpp
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

Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Compiler, die für Visual Studio .NET 2003 durchgeführt wurde, generiert werden: Mehrdeutige Konvertierung bei der Umwandlung von Konstanten 0.

Konvertierung bei der eine Umwandlung, die mit der Konstante 0 ist mehrdeutig, da Int eine Konvertierung sowohl zu lange und Void * erforderlich ist. Wandeln Sie 0 in den genauen Typ, der den Funktionsparameter, die, dem Sie für die verwendet wird, damit keine Konvertierungen müssen stattfinden (dieser Code wird in der Visual Studio .NET 2003 und Visual Studio .NET Versionen von Visual C++ gültig sein), um diesen Fehler zu beheben.

```cpp
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

Dieser Fehler kann auftreten, da die CRT jetzt "float" und doppelte Formen der alle mathematischen Funktionen verfügt.

```cpp
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

Dieser Fehler kann auftreten, da pow (Int, Int) aus "Math.h", in der CRT entfernt wurde.

```cpp
// C2668e.cpp
#include <math.h>
int main() {
   pow(9,9);   // C2668
   pow((double)9,9);   // OK
}
```

## <a name="example"></a>Beispiel

Dieser Code in Visual Studio 2015 ist erfolgreich, aber in Visual Studio 2017 und höher mit C2668 schlägt fehl. In Visual Studio 2015 behandelt der Compiler fälschlicherweise eine copy-list-Initialisierung auf die gleiche Weise wie eine Kopierinitialisierung. Er konvertiert nur die Konstruktoren für die Überladungsauflösung.

```cpp
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