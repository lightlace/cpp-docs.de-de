---
title: Compilerwarnung (Stufe 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: 18045377210b6c020786ad2ec2e003d0e764e4b5
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683264"
---
# <a name="compiler-warning-level-4-c4366"></a>Compilerwarnung (Stufe 4) C4366

Das Ergebnis des unären Operators "Operator" ist möglicherweise nicht ausgerichtet.

Wenn ein Strukturmember aufgrund der Verpackung nicht ausgerichtet werden kann, wird der Compiler gewarnt, wenn die Adresse des betreffenden Members einem ausgerichteten Zeiger zugewiesen wird. Standardmäßig werden alle Zeiger ausgerichtet.

Um C4366 aufzulösen, ändern Sie entweder die Ausrichtung der Struktur, oder deklarieren Sie den Zeiger mit dem [__unaligned](../../cpp/unaligned.md) -Schlüsselwort.

Weitere Informationen finden Sie unter __unaligned und [Paket](../../preprocessor/pack.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4366 generiert.

```cpp
// C4366.cpp
// compile with: /W4 /c
// processor: IPF x64
#pragma pack(1)
struct X {
   short s1;
   int s2;
};

int main() {
   X x;
   short * ps1 = &x.s1;   // OK
   int * ps2 = &x.s2;   // C4366
}
```