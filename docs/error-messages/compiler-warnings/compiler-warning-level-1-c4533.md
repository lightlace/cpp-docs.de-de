---
title: Compilerwarnung (Stufe 1) C4533
ms.date: 11/04/2016
f1_keywords:
- C4533
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
ms.openlocfilehash: 6ee88af66238497216d7e5dab497394a58a55805
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965751"
---
# <a name="compiler-warning-level-1-c4533"></a>Compilerwarnung (Stufe 1) C4533

die Initialisierung von "Variable" wird von "Instruction" übersprungen.

Eine Anweisung in Ihrem Programm hat den Ablauf der Steuerung geändert, sodass eine Anweisung, die eine Variable initialisiert hat, nicht ausgeführt wurde. Im folgenden Beispiel wird C4533 generiert:

```cpp
// C4533.cpp
// compile with: /W1
#include <stdio.h>

struct A
{
   int m_data;
};

int main()
{
   if (1)
   {
      goto Label;
   }

   A a = { 100 };

   Label:   // C4533
      printf("\n%d", a.m_data);   // prints an uninitialized value
}
```