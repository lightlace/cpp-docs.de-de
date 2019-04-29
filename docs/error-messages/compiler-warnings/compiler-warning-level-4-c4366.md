---
title: Compilerwarnung (Stufe 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: 11fcb0070359201de39ca5f33c83d000e02f0835
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391555"
---
# <a name="compiler-warning-level-4-c4366"></a>Compilerwarnung (Stufe 4) C4366

Das Ergebnis des unären Operators "Operator" möglicherweise nicht ausgerichtet.

Wenn ein Strukturmember jemals nicht ausgerichtete aufgrund von Überlastung werden konnte, warnt der Compiler bei, dass die Adresse des Mitglieds ein ausgerichtete Zeiger zugewiesen ist. Standardmäßig werden alle Zeiger ausgerichtet.

Um C4366 zu beheben, ändern Sie die Ausrichtung der Struktur oder deklarieren den Zeiger mit dem [__unaligned](../../cpp/unaligned.md) Schlüsselwort.

Weitere Informationen finden Sie unter __unaligned und [Pack](../../preprocessor/pack.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4366 generiert.

```
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