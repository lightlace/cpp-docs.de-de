---
title: Compilerfehler C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: 0bd1e770e38fcb85164bfa205470ac55a12e1c87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466195"
---
# <a name="compiler-error-c2061"></a>Compilerfehler C2061

Syntaxfehler: Bezeichner "Identifier"

Der Compiler hat einen Bezeichner, in denen davon ausgegangen wurde nicht gefunden. Stellen Sie sicher, dass `identifier` wird deklariert, bevor Sie ihn verwenden.

Initialisierer kann durch Klammern eingeschlossen sein. Um dieses Problem zu vermeiden, schließen Sie den Deklarator in Klammern ein, oder stellen sie eine `typedef`.

Dieser Fehler kann auch verursacht werden, wenn der Compiler einen Ausdruck als Klassenvorlagenargument erkennt; Verwenden Sie [Typename](../../cpp/typename.md) um dem Compiler mitzuteilen, es ist ein Typ.

Im folgende Beispiel wird die C2061 generiert:

```
// C2061.cpp
// compile with: /c
template < A a >   // C2061
// try the following line instead
// template < typename b >
class c{};
```

C2061 kann auftreten, wenn Sie einen Instanznamen an übergeben [Typeid](../../windows/typeid-cpp-component-extensions.md):

```
// C2061b.cpp
// compile with: /clr
ref struct G {
   int i;
};

int main() {
   G ^ pG = gcnew G;
   System::Type ^ pType = typeid<pG>;   // C2061
   System::Type ^ pType2 = typeid<G>;   // OK
}
```