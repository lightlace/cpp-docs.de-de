---
title: Compilerfehler C2714
ms.date: 11/04/2016
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: feba363a7cd15d92bf850e8cba457ff310d15490
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386790"
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