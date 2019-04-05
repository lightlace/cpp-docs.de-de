---
title: Compilerfehler C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 248431afb25aa4b9480818f76388f6ad56d8e006
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778246"
---
# <a name="compiler-error-c3821"></a>Compilerfehler C3821

'Funktion': verwaltete Typ oder die Funktion kann nicht in eine nicht verwaltete Funktion verwendet werden

Funktionen, mit der Inlineassembly oder [Setjmp](../../c-runtime-library/reference/setjmp.md) darf keine Werttypen oder verwaltete Klassen enthalten. Um diesen Fehler zu beheben, entfernen Sie die Inlineassembly und `setjmp` oder entfernen Sie die verwalteten Objekte.

C3821 kann auch auftreten, wenn Sie versuchen, die automatische Speicherung in eine Vararg-Funktion zu verwenden.  Weitere Informationen finden Sie unter [Variablenargumentlisten (...) (C++ / CLI) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) und [C++-Stapelsemantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).

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
