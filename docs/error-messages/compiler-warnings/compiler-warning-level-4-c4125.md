---
title: Compilerwarnung (Stufe 4) C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: 3b82bfd1a1acff07a0fd47bbd2abfb08178a74c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401357"
---
# <a name="compiler-warning-level-4-c4125"></a>Compilerwarnung (Stufe 4) C4125

Dezimale Ziffer beendet oktale Escapesequenz

Der Compiler wertet die oktale Zahl ohne die Dezimalziffer aus und geht davon aus, dass die Dezimalziffer ein Zeichen ist.

## <a name="example"></a>Beispiel

```
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

Wenn die Ziffer 9 als Zeichen vorgesehen ist, korrigieren Sie das Beispiel wie folgt:

```
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```