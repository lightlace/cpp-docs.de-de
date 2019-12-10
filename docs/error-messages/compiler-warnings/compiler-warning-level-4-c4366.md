---
title: Compilerwarnung (Stufe 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: fb4cead9367c5ef69627f607c521f480ad94271f
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991052"
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
