---
title: Compilerfehler C2229
ms.date: 11/04/2016
f1_keywords:
- C2229
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
ms.openlocfilehash: 998067e9af178c1898c3443c4e84da965c22fa81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301733"
---
# <a name="compiler-error-c2229"></a>Compilerfehler C2229

Typ "Identifier" wurde ein ungültiger NULL-array

Ein Member einer Struktur oder ein Bit enthält ein Array der Größe 0 (null), die nicht das letzte Element ist.

Da Sie eine NULL Array Größe wie das letzte Element der Struktur verwenden können, müssen Sie seine Größe angeben, beim Zuweisen der Struktur.

Wenn 0 (null) großen Arrays nicht der letzte Member der Struktur ist, kann der Compiler nicht den Offset für die verbleibenden Felder berechnen.

Im folgende Beispiel wird die C2229 generiert:

```
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