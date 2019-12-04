---
title: Compilerfehler C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 25023277258d33ab77bde18f6cdfabc862f50a63
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741741"
---
# <a name="compiler-error-c3821"></a>Compilerfehler C3821

"Funktion": ein verwalteter Typ oder eine verwaltete Funktion kann nicht in einer nicht verwalteten Funktion verwendet werden.

Funktionen mit der Inlineassembly oder [setjmp](../../c-runtime-library/reference/setjmp.md) können keine Werttypen oder verwalteten Klassen enthalten. Entfernen Sie die Inlineassembly, und `setjmp` oder entfernen Sie die verwalteten Objekte, um diesen Fehler zu beheben.

C3821 kann auch auftreten, wenn Sie versuchen, den automatischen Speicher in einer vararg-Funktion zu verwenden.  Weitere Informationen finden Sie unter [Variablen Argument Listen (...) (C++/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) und [ C++ Stapel Semantik für Verweis Typen](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3821 generiert.

```cpp
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3821 generiert.

```cpp
// C3821b.cpp
// compile with: /clr
// processor: /x86
ref class A {
   public:
   int i;
};

int main() {
   // cannot use managed classes in this function
   A ^a;

   __asm {
      nop
   }
} // C3821
```
