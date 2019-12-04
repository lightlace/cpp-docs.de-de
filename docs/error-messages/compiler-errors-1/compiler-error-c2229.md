---
title: Compilerfehler C2229
ms.date: 11/04/2016
f1_keywords:
- C2229
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
ms.openlocfilehash: 2d974c4f0630a592daad956448bf21cea21efb7c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759268"
---
# <a name="compiler-error-c2229"></a>Compilerfehler C2229

der Typ "Bezeichner" weist ein ungültiges Array der Größen NULL auf.

Ein Member einer Struktur oder eines Bitfelds enthält ein Array der Größe 0 (null), das nicht das letzte Element ist.

Da Sie ein Array mit der Größe 0 (null) als letzten Member der Struktur haben können, müssen Sie die Größe angeben, wenn Sie die Struktur zuordnen.

Wenn das Array der Größenangabe nicht der letzte Member der Struktur ist, kann der Compiler den Offset für die verbleibenden Felder nicht berechnen.

Im folgenden Beispiel wird C2229 generiert:

```cpp
// C2229.cpp
struct S {
   int a[0];  // C2229  zero-sized array
   int b[1];
};

struct S2 {
   int a;
   int b[0];
};

int main() {
   // allocate 7 elements for b field
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];
   s2->b[6] = 100;
}
```
