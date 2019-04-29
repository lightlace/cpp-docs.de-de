---
title: Compilerwarnung (Stufe 1) C4548
ms.date: 11/04/2016
f1_keywords:
- C4548
helpviewer_keywords:
- C4548
ms.assetid: 2cee817e-e463-4d90-bbd2-de120d48c101
ms.openlocfilehash: 02010107c90f52f0fd2df838d90b78809fb80b70
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384178"
---
# <a name="compiler-warning-level-1-c4548"></a>Compilerwarnung (Stufe 1) C4548

Ausdruck vor dem Komma hat keine Auswirkung; es wurde ein Ausdruck mit Nebeneffekt erwartet

Der Compiler hat ein falsch formatiertes Kommaausdruck.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Im folgende Beispiel wird die C4548 generiert:

```
// C4548.cpp
// compile with: /W1
#pragma warning (default : 4548)
int main()
{
   int i = 0, k = 0;

   if ( i, k )   // C4548
   // try the following line instead
   // if ( i = 0, k )
      i++;
}
```