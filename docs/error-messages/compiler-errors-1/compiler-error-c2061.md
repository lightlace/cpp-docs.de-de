---
title: Compilerfehler C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: dc64852523b6b56bc506260576e3c79164628340
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735930"
---
# <a name="compiler-error-c2061"></a>Compilerfehler C2061

Syntax Fehler: Bezeichner "Bezeichner"

Der Compiler hat einen Bezeichner gefunden, der nicht erwartet wurde. Stellen Sie sicher, dass `identifier` deklariert ist, bevor Sie ihn verwenden.

Ein Initialisierer kann in Klammern eingeschlossen werden. Um dieses Problem zu vermeiden, schließen Sie den Deklarator in Klammern ein, oder machen Sie ihn als `typedef`.

Dieser Fehler kann auch verursacht werden, wenn der Compiler einen Ausdruck als Klassen Vorlagen Argument erkennt. Verwenden Sie [Typname](../../cpp/typename.md) , um dem Compiler mitzuteilen, dass es sich um einen-Typ handelt.

Im folgenden Beispiel wird C2061 generiert:

```cpp
// C2061.cpp
// compile with: /c
template < A a >   // C2061
// try the following line instead
// template < typename b >
class c{};
```

C2061 kann auftreten, wenn Sie einen Instanznamen an [typeid](../../extensions/typeid-cpp-component-extensions.md)übergeben:

```cpp
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
