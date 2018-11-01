---
title: Compilerfehler C2495
ms.date: 11/04/2016
f1_keywords:
- C2495
helpviewer_keywords:
- C2495
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
ms.openlocfilehash: 83a0359fce175b12dd18e2500d63d7a86bed9f0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436035"
---
# <a name="compiler-error-c2495"></a>Compilerfehler C2495

'Bezeichner': 'Nothrow' kann nur auf Funktionsdeklarationen oder Funktionsdefinitionen angewendet werden

Die [Nothrow](../../cpp/nothrow-cpp.md) erweiterten Attribut kann nur auf Funktionsdeklarationen oder-Definitionen angewendet werden.

Im folgende Beispiel wird die C2495 generiert:

```
// C2495.cpp
// compile with: /c
__declspec(nothrow) class X {   // C2495
   int m_data;
} x;

__declspec(nothrow) void test();   // OK
```