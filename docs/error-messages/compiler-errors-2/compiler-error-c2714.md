---
title: Compilerfehler C2714
ms.date: 11/04/2016
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: feba363a7cd15d92bf850e8cba457ff310d15490
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556363"
---
# <a name="compiler-error-c2714"></a>Compilerfehler C2714

__alignof(void) ist nicht zulässig

Zu einem Operator wurde ein ungültiger Wert übergeben.

Finden Sie unter [__alignof-Operator](../../cpp/alignof-operator.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2714 generiert.

```
// C2714.cpp
int main() {
   return __alignof(void);   // C2714
   return __alignof(char);   // OK
}
```