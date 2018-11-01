---
title: Compilerwarnung (Stufe 1) C4097
ms.date: 11/04/2016
f1_keywords:
- C4097
helpviewer_keywords:
- C4097
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
ms.openlocfilehash: d27e1d33db7a531d541bffdac015176de72077d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472149"
---
# <a name="compiler-warning-level-1-c4097"></a>Compilerwarnung (Stufe 1) C4097

Erwarteter pragma-Parameter sollte "restore" oder "off" sein

Einem Pragma wurde ein ungültiger Wert übergeben.

Im folgenden Beispiel wird C4097 generiert:

```
// C4097.cpp
// compile with: /W1
#pragma runtime_checks("",test)   // C4097
// try the following line instead
// #pragma runtime_checks("",off)

int main() {
}
```