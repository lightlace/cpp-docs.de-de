---
title: Compilerfehler C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: f522a2de77e03a7c5f8f8dc774d62744417344fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540191"
---
# <a name="compiler-error-c3162"></a>Compilerfehler C3162

'Typ': ein Verweistyp mit einem Destruktor kann nicht als Typ des statischen Datenmember 'Member' verwendet werden

Die common Language Runtime wissen nicht, wann Sie einen benutzerdefinierten Destruktor ausgeführt werden, wenn die Klasse auch statische Memberfunktion enthält.

Ein Destruktor wird niemals ausgeführt werden, es sei denn, das Objekt explizit gelöscht werden.

Weitere Informationen finden Sie unter

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Häufig auftretende 64-Bit-Migrationsprobleme bei Visual C++](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3162 generiert.

```
// C3162.cpp
// compile with: /clr /c
ref struct A {
   ~A() { System::Console::WriteLine("in destructor"); }
   static A i;   // C3162
   static A^ a = gcnew A;   // OK
};

int main() {
   A ^ a = gcnew A;
   delete a;
}
```