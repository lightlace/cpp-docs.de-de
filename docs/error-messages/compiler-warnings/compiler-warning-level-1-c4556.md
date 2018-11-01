---
title: Compilerwarnung (Stufe 1) C4556
ms.date: 08/27/2018
f1_keywords:
- xml
- C4556
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
ms.openlocfilehash: 53261b97249340ce56ce6ae0f5cc0eab7e97a107
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538488"
---
# <a name="compiler-warning-level-1-c4556"></a>Compilerwarnung (Stufe 1) C4556

> der Wert des systeminternen unmittelbaren Arguments "*Wert*"liegt außerhalb des Bereichs"*Lowerbound* - *Upperbound*"

## <a name="remarks"></a>Hinweise

Eine systeminterne Funktion entspricht eine Hardware-Anweisung. Die Hardware-Anweisung verfügt über eine feste Anzahl von Bits, um die Konstante zu codieren. Wenn *Wert* ist außerhalb des gültigen Bereichs, wird nicht codiert werden ordnungsgemäß. Der Compiler schneidet der zusätzlichen Bits ab.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4556 generiert:

```cpp
// C4556.cpp
// compile with: /W1
// processor: x86 IPF
#include <xmmintrin.h>

void test()
{
   __m64 m;
   _m_pextrw(m, 5);   // C4556
}

int main()
{
}
```