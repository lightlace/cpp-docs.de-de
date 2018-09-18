---
title: Compilerwarnung (Stufe 4) C4702 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4702
dev_langs:
- C++
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d15072099c6329eced8ab9dd9c78f8f48c31fe7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057132"
---
# <a name="compiler-warning-level-4-c4702"></a>Compilerwarnung (Stufe 4) C4702

unerreichbarer code

Diese Warnung ist das Ergebnis einer konformitätsverbesserung für Compiler, die für Visual Studio .NET 2003 durchgeführt wurde: unerreichbarer Code. Wenn der Compiler (Back-End) nicht erreichbaren Code erkennt, generiert er C4702, eine Warnung der Stufe 4.

Entfernen Sie für Code, der in der Visual Studio .NET 2003 und die Visual Studio .NET der Versionen von Visual C++ gültig ist die nicht erreichbaren Code, oder sicherzustellen Sie, dass der gesamte Quellcode von Visual Studio erreicht werden kann.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4702 generiert.

```
// C4702.cpp
// compile with: /W4
#include <stdio.h>

int main() {
   return 1;
   printf_s("I won't print.\n");   // C4702 unreachable
}
```

## <a name="example"></a>Beispiel

Beim Kompilieren mit **/GX**, **/EHc**, **/EHsc**, oder **EHac** "extern" C-Funktionen verwenden, Code kann nicht erreicht werden kann, und da "extern" C Funktionen sind davon ausgegangen, dass nicht auslösen, der Catch-Block ist daher nicht erreichbar.  Wenn Sie glauben, dass diese Warnung ist ungültig, da eine Funktion auslösen kann, kompilieren Sie mit **/EHa** oder **/EHs**, je nachdem, auf die ausgelöste Ausnahme.

Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md) für Weitere Informationen.

Im folgende Beispiel wird die C4702 generiert.

```
// C4702b.cpp
// compile with: /W4 /EHsc
#include <iostream>

using namespace std;
extern "C" __declspec(dllexport) void Function2(){}

int main() {
   try {
      Function2();
   }
   catch (...) {
      cout << "Exp: Function2!" << endl;   // C4702
   }
}
```