---
title: Compilerwarnung (Stufe 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: bcd51c66359d0553b7657d85f5b45ee22d4648ff
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991650"
---
# <a name="compiler-warning-level-4-c4100"></a>Compilerwarnung (Stufe 4) C4100

'Bezeichner': Nicht referenzierter formaler Parameter

Auf den formalen Parameter wird im Funktionsrumpf nicht verwiesen. Der nicht referenzierte Parameter wird ignoriert.

C4100 kann auch ausgelöst werden, wenn der Code einen Destruktor für einen anderweitig nicht referenzierten Parameter des primitiven Typs aufruft.  Dies ist eine Einschränkung des Microsoft C++ -Compilers.

Im folgenden Beispiel wird C4100 generiert:

```cpp
// C4100.cpp
// compile with: /W4
void func(int i) {   // C4100, delete the unreferenced parameter to
                     //resolve the warning
   // i;   // or, add a reference like this
}

int main()
{
   func(1);
}
```
