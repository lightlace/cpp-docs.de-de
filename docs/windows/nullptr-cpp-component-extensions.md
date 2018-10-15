---
title: "\"nullptr\" (C++ / CLI und C++ / CX) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 46a68e3ab7119dfb2c99578f299b9d38cbc5736d
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328492"
---
# <a name="nullptr--ccli-and-ccx"></a>"nullptr" (C++ / CLI und C++ / CX)

Die **"nullptr"** Schlüsselwort stellt einen *null-Zeigerwert*. Verwenden Sie einen null-Zeiger-Wert, um anzugeben, dass ein Objekthandle, innerer Zeiger oder systemeigener Zeiger-Typ nicht auf ein Objekt verweist.

Verwendung **"nullptr"** mit verwaltetem oder systemeigenem Code. Der Compiler gibt geeignete sind, aber unterschiedliche Anweisungen für verwalteten und systemeigenen null-Zeiger-Werte. Informationen zur Verwendung der ISO standard C++-Version dieses Schlüsselworts finden Sie unter ["nullptr"](../cpp/nullptr.md).

Die **__nullptr** -Schlüsselwort ist ein Microsoft-spezifische Schlüsselwort, die die gleiche Bedeutung wie **"nullptr"**, aber nur systemeigenen Code gilt. Bei Verwendung von **"nullptr"** mit systemeigenen C/C++-code, und kompilieren Sie mit der ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption verwenden, die der Compiler nicht ermitteln, ob **"nullptr"** gibt ein systemeigenes oder verwaltet die null-Zeigerwert. Verwenden, um dem Compiler machen Ihre Absicht **"nullptr"** einen verwalteten Wert angeben oder **__nullptr** einen systemeigenen Wert angeben.

Die **"nullptr"** -Schlüsselwort ist äquivalent zu **nichts** in Visual Basic und **null** in C# geschrieben.

## <a name="usage"></a>Verwendung

Die **"nullptr"** Schlüsselwort kann überall dort verwendet werden ein Handle, systemeigenen Zeiger oder Funktionsargument verwendet werden kann.

Die **"nullptr"** -Schlüsselwort ist kein Typ und wird nicht unterstützt, für die Verwendung mit:

- [sizeof](../cpp/sizeof-operator.md)

- [typeid](../cpp/typeid-operator.md)

- `throw nullptr` (obwohl `throw (Object^)nullptr;` funktioniert)

Die **"nullptr"** Schlüsselwort kann bei der Initialisierung der folgenden Zeigertypen verwendet werden:

- Systemeigener Zeiger

- Windows-Runtime-handle

- Verwaltete handle

- Verwaltete innerer Zeiger

Die **"nullptr"** -Schlüsselwort kann verwendet werden, um zu testen, wenn ein Zeiger oder Handle Verweis gleich null ist, bevor der Verweis verwendet wird.

Funktionsaufrufe zwischen Sprachen, die null-Zeiger-Werte für die fehlerüberprüfung verwenden sollten richtig interpretiert werden.

Ein Handle für 0 (null) kann nicht initialisiert werden; nur **"nullptr"** kann verwendet werden. Zuweisung der Konstante 0 in ein Objekthandle erzeugt eine geschachtelte `Int32` und eine Umwandlung in `Object^`.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, dass die **"nullptr"** -Schlüsselwort kann verwendet werden, wo ein Handle, systemeigene Zeiger ist, oder Funktionsargument verwendet werden kann. Und im Beispiel wird veranschaulicht, die die **"nullptr"** -Schlüsselwort kann verwendet werden, um einen Verweis zu überprüfen, bevor sie verwendet wird.

```cpp
// mcpp_nullptr.cpp
// compile with: /clr
value class V {};
ref class G {};
void f(System::Object ^) {}

int main() {
// Native pointer.
   int *pN = nullptr;
// Managed handle.
   G ^pG = nullptr;
   V ^pV1 = nullptr;
// Managed interior pointer.
   interior_ptr<V> pV2 = nullptr;
// Reference checking before using a pointer.
   if (pN == nullptr) {}
   if (pG == nullptr) {}
   if (pV1 == nullptr) {}
   if (pV2 == nullptr) {}
// nullptr can be used as a function argument.
   f(nullptr);   // calls f(System::Object ^)  
}
```

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass **"nullptr"** und 0 (null) für systemeigene Zeiger austauschbar verwendet werden kann.

```cpp
// mcpp_nullptr_1.cpp
// compile with: /clr
class MyClass {
public:
   int i;
};

int main() {
   MyClass * pMyClass = nullptr;
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");

   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");

   pMyClass = 0;
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");

   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");
}
```

```Output
pMyClass == nullptr

pMyClass == 0

pMyClass == nullptr

pMyClass == 0
```

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass **"nullptr"** wird als ein Handle für einen beliebigen Typ oder einen systemeigenen Zeiger auf einen beliebigen Typ interpretiert. Bei einem funktionsüberladung mit Handles auf verschiedene Arten, werden einem Mehrdeutigkeitsfehler generiert. Die **"nullptr"** explizit in einen Typ umgewandelt werden müssten.

```cpp
// mcpp_nullptr_2.cpp
// compile with: /clr /LD
void f(int *){}
void f(int ^){}

void f_null() {
   f(nullptr);   // C2668
   // try one of the following lines instead
   f((int *) nullptr);
   f((int ^) nullptr);
}
```

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, die Umwandlung **"nullptr"** zulässig ist, und eines Zeigers bzw. Handles zurückgegeben, zu der Cast-Typ, enthält die **"nullptr"** Wert.

```cpp
// mcpp_nullptr_3.cpp
// compile with: /clr /LD
using namespace System;
template <typename T>
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type

int main() {
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)

   // Delete the following line to resolve.
   f(nullptr);

   f(0);   // T = int, call f(int)  
}
```

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass **"nullptr"** als Funktionsparameter verwendet werden können.

```cpp
// mcpp_nullptr_4.cpp
// compile with: /clr
using namespace System;
void f(Object ^ x) {
   Console::WriteLine("test");
}

int main() {
   f(nullptr);
}
```

```Output
test
```

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass Ziehpunkte deklariert und nicht explizit initialisiert, standardmäßig initialisiert sie sind **"nullptr"**.

```cpp
// mcpp_nullptr_5.cpp
// compile with: /clr
using namespace System;
ref class MyClass {
public:
   void Test() {
      MyClass ^pMyClass;   // gc type
      if (pMyClass == nullptr)  
         Console::WriteLine("NULL");
   }
};

int main() {
   MyClass ^ x = gcnew MyClass();
   x -> Test();
}
```

```Output
NULL
```

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass **"nullptr"** kann in einen systemeigenen Zeiger zugewiesen werden, wenn die Kompilierung mit `/clr`.

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>Anforderungen

Compileroption: (nicht erforderlich, die von allen Optionen zur codegenerierung, einschließlich der unterstützten `/ZW` und `/clr`)

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET- und UWP](../windows/component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)