---
title: Compilerfehler C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: 8a4a2011124056af7064c8241450e1f3613776a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580868"
---
# <a name="compiler-error-c3073"></a>Compilerfehler C3073

"Type": Verweisklasse hat keinen benutzerdefinierten Kopierkonstruktor

In einem [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) Kompilierung, generiert der Compiler einen Kopierkonstruktor für einen Verweistyp nicht. In einem **"/ CLR"** Kompilierung, müssen Sie einen eigenen Kopierkonstruktor für einen Verweistyp definieren, wenn eine Instanz des Typs, der kopiert werden soll.

Weitere Informationen finden Sie unter [C++-Stapelsemantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3073 generiert.

```
// C3073.cpp
// compile with: /clr
ref class R {
public:
   R(int) {}
};

ref class S {
public:
   S(int) {}
   S(const S %rhs) {}   // copy constructor
};

void f(R) {}
void f2(S) {}
void f3(R%){}

int main() {
   R r(1);
   f(r);   // C3073
   f3(r);   // OK

   S s(1);
   f2(s);   // OK
}
```