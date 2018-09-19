---
title: Compilerfehler C3535 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3535
dev_langs:
- C++
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 215fa52f892cb569b32335ca439811eb07b28dc7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094077"
---
# <a name="compiler-error-c3535"></a>Compilerfehler C3535

Typ 'Typ1' in 'Typ2' kann nicht hergeleitet werden.

Der Typ der Variable deklariert, indem die `auto` Schlüsselwort kann nicht vom Typ des der Initialisierungsausdruck hergeleitet werden. Dieser Fehler tritt beispielsweise auf, wenn der Initialisierungsausdruck ergibt `void`, das ist kein Typ.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass der Typ des Initialisierungsausdrucks nicht `void`.

1. Stellen Sie sicher, dass die Deklaration nicht über einen Zeiger auf ein grundlegender Typ ist. Weitere Informationen finden Sie unter [Basistypen](../../cpp/fundamental-types-cpp.md).

1. Stellen Sie sicher, dass die Deklaration ein Zeiger auf einen Typ, der Initialisierungsausdruck ein Zeigertyp ist.

## <a name="example"></a>Beispiel

Im folgende Beispiel C3535 erzeugt, da der Initialisierungsausdruck ergibt `void`.

```
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

Im folgende Beispiel C3535 erzeugt, da die Anweisung Variablen deklariert `x` Ausdruck wird als Zeiger auf einen abgeleiteten Typ, aber der Typ des Initialisierers double. Daher kann der Compiler den Typ der Variablen nicht ableiten.

```
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel C3535 erzeugt, weil Variablen `p` einen Zeiger auf einen abgeleiteten Typ deklariert, aber der Initialisierungsausdruck ist kein Zeigertyp.

```
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)<br/>
[Grundlegende Typen](../../cpp/fundamental-types-cpp.md)