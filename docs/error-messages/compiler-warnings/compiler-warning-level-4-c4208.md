---
title: Compilerwarnung (Stufe 4) C4208
ms.date: 11/04/2016
f1_keywords:
- C4208
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
ms.openlocfilehash: e15140bd2f0983bde64c89a054fd733d1ab902ac
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541863"
---
# <a name="compiler-warning-level-4-c4208"></a>Compilerwarnung (Stufe 4) C4208

nicht dem Standard entsprechende Erweiterung: delete [Exp]-Exp ausgewertet, aber ignoriert

Mit Microsoft Extensions (/Ze) können Sie ein Array mithilfe eines Werts innerhalb von Klammern mit dem [Delete-Operator](../../cpp/delete-operator-cpp.md)löschen. Der Wert wird ignoriert.

```cpp
// C4208.cpp
// compile with: /W4
int main()
{
   int * MyArray = new int[18];
   delete [18] MyArray;      // C4208
   MyArray = new int[18];
   delete [] MyArray;        // ok
}
```

Diese Werte sind unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ungültig.