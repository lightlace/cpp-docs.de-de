---
title: Compilerfehler C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 5bf4e2e42b4534d47a2a7d3c9a838c404a99ba68
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769978"
---
# <a name="compiler-error-c3379"></a>Compilerfehler C3379

'Klasse': eine geschachtelte Klasse darf keinen Assembly-Zugriffsspezifizierer als Teil seiner Deklaration haben

Bei Anwendung auf einem verwalteten Typ, z. B. Klasse oder Struktur, die [öffentliche](../../cpp/public-cpp.md) und [private](../../cpp/private-cpp.md) -Schlüsselwort geben an, ob die Klasse über Assemblymetadaten verfügbar gemacht wird. `public` oder `private` kann nicht für eine geschachtelte Klasse, die den Assemblyzugriff der einschließenden Klasse erben, werden nicht angewendet werden.

Bei Verwendung mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md), `ref` und `value` -Schlüsselwort geben an, dass eine Klasse verwaltet wird (finden Sie unter [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Im folgende Beispiel wird die C3379 generiert:

```
// C3379a.cpp
// compile with: /clr
using namespace System;

public ref class A {
public:
   static int i = 9;

   public ref class BA {   // C3379
   // try the following line instead
   // ref class BA {
   public:
      static int ii = 8;
   };
};

int main() {

   A^ myA = gcnew A;
   Console::WriteLine(myA->i);

   A::BA^ myBA = gcnew A::BA;
   Console::WriteLine(myBA->ii);
}
```
