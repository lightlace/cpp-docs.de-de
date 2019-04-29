---
title: Compilerwarnung (Stufe 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: 55512bf28c8c20512d0d245810d3e5c1fec36939
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402033"
---
# <a name="compiler-warning-level-3-c4334"></a>Compilerwarnung (Stufe 3) C4334

'Operator': Ergebnis der 32-Bit-Verschiebung wurde implizit zu 64 Bit konvertiert (war eine 64-Bit-Verschiebung vorgesehen?)

Das Ergebnis der 32-Bit-Verschiebung wurde implizit nach 64-Bit konvertiert, und der Compiler vermutet, dass eine 64-Bit-Verschiebung vorgesehen war.  Zur Behebung des Problems verwenden Sie eine 64-Bit-Verschiebung, oder wandeln Sie das Ergebnis der Verschiebung explizit in 64-Bit um.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4334 generiert.

```
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```