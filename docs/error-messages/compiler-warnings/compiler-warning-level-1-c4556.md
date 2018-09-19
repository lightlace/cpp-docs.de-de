---
title: Compilerwarnung (Stufe 1) C4556 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- C4556
dev_langs:
- C++
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987e4dc3ba6aea7dcb01dc05cd94c45baced05b8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211027"
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