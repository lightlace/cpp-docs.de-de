---
title: Compilerwarnung (Stufe 1) C4533 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4533
dev_langs:
- C++
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a99211afe310730e9041f2f04dc8ce67a762ed0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084860"
---
# <a name="compiler-warning-level-1-c4533"></a>Compilerwarnung (Stufe 1) C4533

Initialisierung von "Variable" durch "Anweisung" übersprungen

Eine Anweisung im Programm die ablaufsteuerung, dahingehend geändert, dass, eine Anweisung, die eine Variable initialisiert wurde nicht ausgeführt werden kann. Im folgende Beispiel wird die C4533 generiert:

```
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