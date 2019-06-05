---
title: Compilerfehler C2362
ms.date: 06/03/2019
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: d48806982bbb6cdda4d29e47f6692e7e3601d6de
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503212"
---
# <a name="compiler-error-c2362"></a>Compilerfehler C2362

> Initialisierung von "*Bezeichner*" wird übersprungen, indem Sie ' Gehe zu *Bezeichnung*"

Beim Kompilieren mit [/Za](../../build/reference/za-ze-disable-language-extensions.md), ein Sprung auf die Bezeichnung wird verhindert, dass den Bezeichner initialisiert wird.

Sie können nur über eine Deklaration mit einem Initialisierer springen, wenn die Deklaration in einem Block eingeschlossen ist, die eingegeben haben, ist nicht oder wenn die Variable bereits initialisiert wurde.

Im folgende Beispiel wird die C2362 generiert:

```cpp
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

Mögliche Lösung:

```cpp
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```