---
title: Variable Argumentlisten (...) (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
ms.openlocfilehash: ec1e2cefa33bc9d749d0f05e170c2f2db9b25f02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515955"
---
# <a name="variable-argument-lists--ccli"></a>Variable Argumentlisten (...) (C++/CLI)

Dieses Beispiel zeigt, wie Sie die Syntax `...` in C++/CLI verwenden können, um Funktionen zu implementieren, die eine variable Anzahl von Argumenten haben.

> [!NOTE]
> Dieses Thema betrifft C++/CLI. Informationen zur Verwendung von `...` in C++ nach ISO-Standard finden Sie unter [Auslassungszeichen- und Variadic-Vorlagen](../cpp/ellipses-and-variadic-templates.md) und „Ellipsen und Standardargumente“ in [Postfixausdrücke](../cpp/postfix-expressions.md).

Der Parameter, der `...` verwendet, muss der letzte Parameter in der Parameterliste sein.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```cpp
// mcppv2_paramarray.cpp
// compile with: /clr
using namespace System;
double average( ... array<Int32>^ arr ) {
   int i = arr->GetLength(0);
   double answer = 0.0;

   for (int j = 0 ; j < i ; j++)
      answer += arr[j];

   return answer / i;
}

int main() {
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));
}
```

```Output
3
```

## <a name="code-example"></a>Codebeispiel

Das folgende Beispiel zeigt, wie Sie in C# eine Visual C++-Funktion aufrufen, die eine variable Anzahl von Argumenten akzeptiert.

```cpp
// mcppv2_paramarray2.cpp
// compile with: /clr:safe /LD
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};
```

Die Funktion `f` kann beispielsweise von C# oder Visual Basic aufgerufen werden, als wäre sie eine Funktion, die eine variable Anzahl von Argumenten akzeptieren kann.

In C# kann ein Argument, das an ein `ParamArray`-Parameter übergeben wird, durch eine variable Anzahl von Argumenten aufgerufen werden. Das folgende Codebeispiel ist in C#.

```cs
// mcppv2_paramarray3.cs
// compile with: /r:mcppv2_paramarray2.dll
// a C# program

public class X {
   public static void Main() {
      // Visual C# will generate a String array to match the
      // ParamArray attribute
      C myc = new C();
      myc.f("hello", "there", "world");
   }
}
```

Ein Aufruf von `f` in Visual C++ kann ein initialisiertes Array oder ein Array mit variabler Länge übergeben.

```cpp
// mcpp_paramarray4.cpp
// compile with: /clr
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};

int main() {
   C ^ myc = gcnew C();
   myc->f("hello", "world", "!!!");
}
```

## <a name="see-also"></a>Siehe auch

[Arrays](arrays-cpp-component-extensions.md)