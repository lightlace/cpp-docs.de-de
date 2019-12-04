---
title: Compilerfehler C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: 2e26b4b1af8ee3c078f3eae3c0cb6a2677c642c2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761880"
---
# <a name="compiler-error-c3380"></a>Compilerfehler C3380

"Klasse": Ungültiger Assembler-Zugriffsspezifizierer - nur "public" oder "private" sind zulässig

Wenn das [public](../../cpp/public-cpp.md) - oder [private](../../cpp/private-cpp.md) -Schlüsselwort auf eine verwaltete Klasse oder Struktur angewendet wird, gibt es an, ob die Klasse über Assemblymetadaten verfügbar gemacht wird. Nur `public` oder `private` kann auf eine Klasse in einem Programm angewendet werden, das mit [/clr](../../build/reference/clr-common-language-runtime-compilation.md)kompiliert wird.

Die `ref`-und `value` Schlüsselwörter geben bei Verwendung mit [/CLR](../../build/reference/clr-common-language-runtime-compilation.md)an, dass eine Klasse verwaltet wird (siehe [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Im folgenden Beispiel wird C3380 generiert:

```cpp
// C3380_2.cpp
// compile with: /clr
protected ref class A {   // C3380
// try the following line instead
// ref class A {
public:
   static int i = 9;
};

int main() {
   A^ myA = gcnew A;
   System::Console::WriteLine(myA->i);
}
```
