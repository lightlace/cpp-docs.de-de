---
title: Compilerfehler C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 1cfc762cc7151eb2d55f8bd681bec935aea2acd4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625965"
---
# <a name="compiler-error-c3821"></a>Compilerfehler C3821

'Funktion': verwaltete Typ oder die Funktion kann nicht in eine nicht verwaltete Funktion verwendet werden

Funktionen, mit der Inlineassembly oder [Setjmp](../../c-runtime-library/reference/setjmp.md) darf keine Werttypen oder verwaltete Klassen enthalten. Um diesen Fehler zu beheben, entfernen Sie die Inlineassembly und `setjmp` oder entfernen Sie die verwalteten Objekte.

C3821 kann auch auftreten, wenn Sie versuchen, die automatische Speicherung in eine Vararg-Funktion zu verwenden.  Weitere Informationen finden Sie unter [Variablenargumentlisten (...) (C++ / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) und [C++-Stapelsemantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3821 generiert.

```
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3821 generiert.

```
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
