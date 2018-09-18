---
title: Compilerfehler C3821 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3821
dev_langs:
- C++
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e1f9a0bbb8eaae6b316b3d00e4201b2b64222ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023032"
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
