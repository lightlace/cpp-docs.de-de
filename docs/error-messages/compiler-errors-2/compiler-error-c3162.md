---
title: Compilerfehler C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: 95cd2c4af614906da7ba2d1c4c5dd488059f970a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761802"
---
# <a name="compiler-error-c3162"></a>Compilerfehler C3162

"Typ": ein Referenztyp mit einem destrukturtor kann nicht als Typ des statischen Datenmembers "Member" verwendet werden.

Der Common Language Runtime kann nicht wissen, wann ein benutzerdefinierter destrukturtor ausgeführt werden soll, wenn die Klasse auch eine statische Element Funktion enthält.

Ein Dekonstruktor wird niemals ausgeführt, es sei denn, das Objekt wird explizit gelöscht.

Weitere Informationen finden Sie unter

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Häufig auftretende 64-Bit-Migrationsprobleme bei Visual C++](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3162 generiert.

```cpp
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
