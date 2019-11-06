---
title: Compilerwarnung (Stufe 1) C4033
ms.date: 11/04/2016
f1_keywords:
- C4033
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
ms.openlocfilehash: 740be5fa45d0cd332cc7ac6b62a983ce00d05a8f
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623729"
---
# <a name="compiler-warning-level-1-c4033"></a>Compilerwarnung (Stufe 1) C4033

"Funktion" muss einen Wert zurückgeben

Die Funktion gibt keinen Wert zurück. Es wird ein nicht definierter Wert zurückgegeben.

Funktionen, in denen `return` ohne einen Rückgabewert verwendet wird, müssen mit dem Typ `void`deklariert werden.

Dieser Fehler gilt für die C-Sprachcode.

Im folgenden Beispiel wird C4033 generiert:

```c
// C4033.c
// compile with: /W1 /LD
int test_1(int x)   // C4033 expected
{
   if (x)
   {
      return;   // C4033
   }
}
```