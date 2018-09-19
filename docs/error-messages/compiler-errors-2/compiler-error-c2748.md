---
title: Compilerfehler C2748 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2748
dev_langs:
- C++
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d57c7919cd33f9e27ad34b1298d8af36ec360200
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058061"
---
# <a name="compiler-error-c2748"></a>Compilerfehler C2748

verwaltet oder WinRT-Arrayerstellung muss eine Arraygröße oder einen Arrayinitialisierung besitzen

Eine verwaltete oder ein WinRT-Array wurde nicht ordnungsgemäß formatiert. Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).

Im folgenden Beispiel wird C2748 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2748.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>();   // C2748
   // try the following line instead
   array<int> ^p2 = new array<int>(2);
}
```