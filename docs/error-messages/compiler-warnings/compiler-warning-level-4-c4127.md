---
title: Compilerwarnung (Stufe 4) C4127 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bfd913b95b84d8425649476649f9bffa6163141
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601521"
---
# <a name="compiler-warning-level-4-c4127"></a>Compilerwarnung (Stufe 4) C4127

> Bedingter Ausdruck ist konstant

## <a name="remarks"></a>Hinweise

Der Kontrollausdruck einer `if` -Anweisung oder `while` -Schleife wird in eine Konstante ausgewertet. Aufgrund ihrer allgemeinen idiomatische Verwendung, ab Visual Studio 2015 Update 3, trivialen Konstanten wie z. B. 1 oder `true` lösen keine Warnung aus, es sei denn, sie sind, dass das Ergebnis eines Vorgangs in einem Ausdruck.

Wenn der steuernde Ausdruck einer `while` Schleife ist eine Konstante, da die Schleife in der Mitte beendet wird, ersetzen Sie die `while` -Schleife mit einem `for` Schleife. Lassen Sie die Initialisierung, den Beendigungstest und die schleifenerhöhung einer `for` -Schleife, die bewirkt, die Schleife dass zu einer unendlichen, genau wie `while(1)`, und Sie beenden die Schleife, aus dem Text der der `for` Anweisung.

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