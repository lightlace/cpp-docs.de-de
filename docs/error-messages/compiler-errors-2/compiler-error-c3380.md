---
title: Compilerfehler C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: e03212c3148ba7f5c445dfee02ee32629ab5d373
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668584"
---
# <a name="compiler-error-c3380"></a>Compilerfehler C3380

"Klasse": Ungültiger Assembler-Zugriffsspezifizierer - nur "public" oder "private" sind zulässig

Wenn das [public](../../cpp/public-cpp.md) - oder [private](../../cpp/private-cpp.md) -Schlüsselwort auf eine verwaltete Klasse oder Struktur angewendet wird, gibt es an, ob die Klasse über Assemblymetadaten verfügbar gemacht wird. Nur `public` oder `private` kann auf eine Klasse in einem Programm angewendet werden, das mit [/clr](../../build/reference/clr-common-language-runtime-compilation.md)kompiliert wird.

Die `ref` und `value` Schlüsselwörter, bei der Verwendung mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md), um anzugeben, dass eine Klasse verwaltet ist (finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md)).

Im folgenden Beispiel wird C3380 generiert:

```
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
