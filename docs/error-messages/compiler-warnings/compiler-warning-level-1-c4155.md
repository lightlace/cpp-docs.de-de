---
title: Compilerwarnung (Stufe 1) C4155
ms.date: 11/04/2016
f1_keywords:
- C4155
helpviewer_keywords:
- C4155
ms.assetid: ba233353-09e3-4195-8127-13a27ddd8d70
ms.openlocfilehash: 1f47b990762ebe2ea18368949c1781fcf5553d8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391854"
---
# <a name="compiler-warning-level-1-c4155"></a>Compilerwarnung (Stufe 1) C4155

Löschen eines Arrayausdrucks ohne Verwendung der Arrayform von "delete"

Die Arrayform von **delete** sollte zum Löschen eines Arrays verwendet werden. Diese Warnung tritt nur unter der ANSI-Kompatibilität (/Za) auf.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4155 generiert:

```
// C4155.cpp
// compile with: /Za /W1
#include <stdio.h>

int main(void)
{
    int (*array)[ 10 ] = new int[ 5 ] [ 10 ];
    array[0][0] = 8;

    printf_s("%d\n", array[0][0]);

   delete array;   // C4155
    // try the following line instead
    // delete [] array;   // C4155
}
```