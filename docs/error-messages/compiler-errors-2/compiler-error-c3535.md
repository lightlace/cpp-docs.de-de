---
title: Compilerfehler C3535
ms.date: 11/04/2016
f1_keywords:
- C3535
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
ms.openlocfilehash: 6b487c0f94a00ec64e0c2178265c5a8c27544a51
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761555"
---
# <a name="compiler-error-c3535"></a>Compilerfehler C3535

der Typ für "Typ1" kann nicht von "Typ2" abgeleitet werden.

Der Typ der Variablen, die vom `auto`-Schlüsselwort deklariert wurde, kann nicht vom Typ des Initialisierungs Ausdrucks abgeleitet werden. Dieser Fehler tritt beispielsweise auf, wenn der Initialisierungs Ausdruck zu `void`ausgewertet wird. Dies ist kein Typ.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass der Typ des Initialisierungs Ausdrucks nicht `void`ist.

1. Stellen Sie sicher, dass die Deklaration kein Zeiger auf einen grundlegenden Typ ist. Weitere Informationen finden Sie unter [grundlegende Typen](../../cpp/fundamental-types-cpp.md).

1. Stellen Sie sicher, dass der Initialisierungs Ausdruck ein Zeigertyp ist, wenn die Deklaration ein Zeiger auf einen Typ ist.

## <a name="example"></a>Beispiel

Das folgende Beispiel ergibt C3535, da der Initialisierungs Ausdruck zu `void`ausgewertet wird.

```cpp
// C3535a.cpp
// Compile with /Zc:auto
void f(){}
int main()
{
   auto x = f();   //C3535
   return 0;
}
```

## <a name="example"></a>Beispiel

Das folgende Beispiel ergibt C3535, da die-Anweisung Variable `x` als Zeiger auf einen abgeleiteten Typ deklariert, aber der Typ des initialisiererausdrucks ist Double. Folglich kann der Compiler den Typ der Variablen nicht ableiten.

```cpp
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3535 erzeugt, da die Variable `p` einen Zeiger auf einen dedudierten Typ deklariert, aber der Initialisierungs Ausdruck kein Zeigertyp ist.

```cpp
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)<br/>
[Grundlegende Typen](../../cpp/fundamental-types-cpp.md)
