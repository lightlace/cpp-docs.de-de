---
title: Variable Argumentlisten (...) (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 183208d734fa5ad39151b171bd9c6889863c8d33
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057173"
---
# <a name="variable-argument-lists--ccli"></a>Variable Argumentlisten (...) (C++/CLI)

Dieses Beispiel zeigt Informationen zur Verwendung der `...` Syntax in C++ / CLI, um Funktionen zu implementieren, die eine Variable Anzahl von Argumenten verfügen.

> [!NOTE]
> Dieses Thema betrifft C++/CLI. Informationen zur Verwendung der `...` in ISO-Standard-c++ finden Sie unter [Auslassungszeichen- und Variadic-Vorlagen](../cpp/ellipses-and-variadic-templates.md) und Ellipsen und Standardargumente in [Postfixausdrücke](../cpp/postfix-expressions.md).

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

[Arrays](../windows/arrays-cpp-component-extensions.md)