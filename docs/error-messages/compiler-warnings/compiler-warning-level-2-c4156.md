---
title: Compilerwarnung (Stufe 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 7d9a4ed09f026267e2c0f37fbbe4550ecd668dfc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514425"
---
# <a name="compiler-warning-level-2-c4156"></a>Compilerwarnung (Stufe 2) C4156

Löschen eines Arrayausdrucks ohne Verwendung der Arrayform von "Delete". die Arrayform ersetzt

Der nicht-Arrayform von **löschen** ein Array kann nicht gelöscht werden. Der Compiler übersetzte **löschen** in das Array-Formular.

Diese Warnung tritt nur unter Microsoft-Erweiterungen (/ Ze).

## <a name="example"></a>Beispiel

```
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```