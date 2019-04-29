---
title: Compilerwarnung (Stufe 4) C4127
ms.date: 09/13/2018
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: 7f1e23d15d8daa126987278611cb5a85a5a36fc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401310"
---
# <a name="compiler-warning-level-4-c4127"></a>Compilerwarnung (Stufe 4) C4127

> Bedingter Ausdruck ist konstant

## <a name="remarks"></a>Hinweise

Der steuernde Ausdruck einer **Wenn** Anweisung oder **während** Schleife, die mit einer Konstante ausgewertet wird. Aufgrund ihrer allgemeinen idiomatische Verwendung, ab Visual Studio 2015 Update 3, trivialen Konstanten wie z. B. 1 oder **"true"** lösen keine Warnung aus, es sei denn, sie sind, dass das Ergebnis eines Vorgangs in einem Ausdruck.

Wenn der steuernde Ausdruck einer **während** Schleife ist eine Konstante, da die Schleife in der Mitte beendet wird, ersetzen Sie die **während** -Schleife mit einem **für** Schleife. Lassen Sie die Initialisierung, den Beendigungstest und die schleifenerhöhung einer **für** -Schleife, die bewirkt, die Schleife dass zu einer unendlichen, genau wie `while(1)`, und Sie beenden die Schleife, aus dem Text der der **für** -Anweisung.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt zwei Möglichkeiten, C4127 generiert und gezeigt, wie, eine for-Schleife, um die Warnung zu vermeiden:

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```