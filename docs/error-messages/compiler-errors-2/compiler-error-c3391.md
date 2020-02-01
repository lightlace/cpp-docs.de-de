---
title: Compilerfehler C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: 7590ba9431892c07a32c27fdc97604c8b005fe33
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912857"
---
# <a name="compiler-error-c3391"></a>Compilerfehler C3391

"type_arg": Ungültiges Typargument für den generischen Parameter "param" von "generic_type", muss ein Werttyp sein, der keine NULL-Werte zulässt.

Ein generischer Typ wurde fehlerhaft instanziiert. Überprüfen Sie die Typdefinition. Weitere Informationen finden Sie unter <xref:System.Nullable> und [Generika](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C# verwendet, um eine Komponente zu erstellen, die einen generischen Typ mit bestimmten Einschränkungen enthält, die beim Erstellen von C++generischen Typen in/CLI. nicht unterstützt werden. Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```csharp
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

Wenn die C3391. dll-Komponente verfügbar ist, generiert das folgende Beispiel C3391.

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