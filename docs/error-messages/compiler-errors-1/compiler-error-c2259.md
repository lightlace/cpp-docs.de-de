---
title: Compilerfehler C2259
ms.date: 11/04/2016
f1_keywords:
- C2259
helpviewer_keywords:
- C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
ms.openlocfilehash: 0310f20854185a6f8a5ccb0ce7b087c4d7c5f29d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440403"
---
# <a name="compiler-error-c2259"></a>Compilerfehler C2259

'class': abstrakte Klasse kann nicht instanziiert werden

Durch den Code wird eine Instanz einer abstrakten Klasse oder Struktur deklariert.

Eine Klasse oder Struktur mit einer oder mehreren rein virtuellen Funktionen kann nicht instanziiert werden. Damit Objekte einer abgeleiteten Klasse instanziiert werden können, muss jede rein virtuelle Funktion durch die abgeleitete Klasse überschrieben werden.

Weitere Informationen finden Sie unter [implizit abstrakte Klassen](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).

Im folgende Beispiel wird der Fehler C2259 generiert:

```
// C2259.cpp
// compile with: /c
class V {
public:
   void virtual func() = 0;
};
class A : public V {};
class B : public V {
public:
   void func();
};
V v;  // C2259, V is an abstract class
A a;  // C2259, A inherits func() as pure virtual
B b;  // OK, B defines func()
```

Immer wenn Sie von einer Schnittstelle ableiten und die Schnittstellenmethoden in der abgeleiteten Klasse mit anderen als öffentlichen Zugriffsberechtigungen implementieren, wird möglicherweise der Fehler C2259 ausgegeben.  Dieser Fehler tritt auf, weil der Compiler erwartet, dass die in der abgeleiteten Klasse definierten Schnittstellenmethoden öffentlichen Zugriff haben. Wenn Sie die Memberfunktionen für eine Schnittstelle mit beschränkteren Zugriffsberechtigungen implementieren, werden diese vom Compiler nicht als Implementierungen der in der Schnittstelle definierten Schnittstellenmethoden interpretiert, sodass die abgeleitete Klasse zu einer abstrakten Klasse wird.

Das Problem kann mit zwei Methoden umgangen werden:

- Definieren Sie die Zugriffsberechtigungen für die implementierten Methoden als öffentlich.

- Verwenden Sie den Bereichsauflösungsoperator für die in der abgeleiteten Klasse definierten Schnittstellenmethoden, um den Namen der implementierten Methode mit dem Namen der Schnittstelle zu kennzeichnen.

C2259 kann auch auftreten, infolge einer konformitätsverbesserung für die in Visual C++ 2005 war **/Zc: wchar_t** ist jetzt standardmäßig aktiviert. In diesem Fall kann der Fehler C2599 behoben, die entweder durch Kompilieren mit werden **/Zc:**, um das Verhalten zu erhalten, von früheren Versionen oder vorzugsweise, durch die Aktualisierung Ihrer Typen an, sodass diese kompatibel sind. Weitere Informationen finden Sie unter[/Zc:wchar_t (wchar_t ist der systemeigene Typ)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

Im folgende Beispiel wird der Fehler C2259 generiert:

```
// C2259b.cpp
// compile with: /c
#include <windows.h>

class MyClass {
public:
   // WCHAR now typedef'ed to wchar_t
   virtual void func(WCHAR*) = 0;
};

class MyClass2 : MyClass {
public:
   void func(unsigned short*);
};

MyClass2 x;   // C2259

// OK
class MyClass3 {
public:
   virtual void func(WCHAR*) = 0;
   virtual void func2(wchar_t*) = 0;
   virtual void func3(unsigned short*) = 0;
};

class MyClass4 : MyClass3 {
public:
   void func(WCHAR*) {}
   void func2(wchar_t*) {}
   void func3(unsigned short*) {}
};

MyClass4 y;
```

Im folgende Beispiel wird der Fehler C2259 generiert:

```
// C2259c.cpp
// compile with: /clr
interface class MyInterface {
   void MyMethod();
};

ref class MyDerivedClass: public MyInterface {
private:
   // Uncomment the following line to resolve.
   // public:
   void MyMethod(){}
   // or the following line
   // void MyInterface::MyMethod() {};
};

int main() {
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259
}
```
