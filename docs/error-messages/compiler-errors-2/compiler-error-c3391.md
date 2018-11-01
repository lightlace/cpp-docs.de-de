---
title: Compilerfehler C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: cac397e4588c493fb8c47932feb97a5f12cf2583
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578216"
---
# <a name="compiler-error-c3391"></a>Compilerfehler C3391

'Typargument': Ungültiges Typargument für generischen Parameter 'Param' von 'generischer_typ', generisch, muss ein NULL-Werte

Ein generischer Typ wurde fehlerhaft instanziiert. Überprüfen Sie die Typdefinition. Weitere Informationen finden Sie unter <xref:System.Nullable> und [Generika](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird c# verwendet eine Komponente zu erstellen, die einen generischen Typ mit bestimmten Einschränkungen, die beim Erstellen von generischer Typen in C++ nicht unterstützt werden, enthält c++ / CLI. Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```cs
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

Wenn die Komponente C3391.dll verfügbar ist, im folgende Beispiel wird C3391 generiert:

```cpp
// C3391_b.cpp
// Compile by using: cl /clr C3391_b.cpp
#using <C3391.dll>
using namespace System;
value class VClass {};

int main() {
   GR< Nullable<VClass> >^ a =
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK
}
```