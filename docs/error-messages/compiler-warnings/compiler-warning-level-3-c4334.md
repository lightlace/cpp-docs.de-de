---
title: Compilerwarnung (Stufe 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: ebebfe9994be3dd136e3924cb2aea60c0c901926
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051638"
---
# <a name="compiler-warning-level-3-c4334"></a>Compilerwarnung (Stufe 3) C4334

"Operator": das Ergebnis der 32-Bit-Verschiebung wurde implizit in 64 Bits konvertiert (war 64-Bit-Shift beabsichtigt?)

Das Ergebnis der 32-Bit-Verschiebung wurde implizit in 64-Bits konvertiert, und der Compiler hat fest, dass eine 64-Bit-Verschiebung beabsichtigt war.  Um diese Warnung zu beheben, verwenden Sie entweder die 64-Bit-Schicht, oder wandeln Sie das Verschiebungs Ergebnis explizit in 64-Bit um.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4334 generiert.

```cpp
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```