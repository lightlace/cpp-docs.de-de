---
title: Compilerwarnung (Stufe 3) C4414
ms.date: 11/04/2016
f1_keywords:
- C4414
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
ms.openlocfilehash: 0a9ceb332888e306b8cb3bcbe1832f773d02d63d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629813"
---
# <a name="compiler-warning-level-3-c4414"></a>Compilerwarnung (Stufe 3) C4414

'Funktion': short-Sprung zur Funktion konvertiert in near

Kurze Sprünge generieren kompakte Anweisung, die in eine Adresse in einem begrenzten Bereich von der Anweisung "branches". Die Anweisung enthält einen kurze Offset, der den Abstand zwischen dem Sprung und die Zieladresse, die Definition der Funktion darstellt. Während des Verknüpfens möglicherweise eine Funktion verschoben werden oder ein Link-Time-Optimierungen, die dazu führen, dass die Funktion, die außerhalb des gültigen Bereichs erreichbar, die von einem kurzen Offset verschoben werden. Der Compiler muss einen speziellen Datensatz für den Sprung generieren, müssen Sie die Anweisung "jmp" ganz oder nahe sein. Der Compiler versucht, die Konvertierung.

Der folgende Code generiert beispielsweise C4414:

```
// C4414.cpp
// compile with: /W3 /c
// processor: x86
int DoParityEven();
int DoParityOdd();
unsigned char global;
int __declspec(naked) DoParityEither()
{
   __asm
   {
      test global,0
      jpe SHORT DoParityEven  // C4414
      jmp SHORT DoParityOdd   // C4414
   }
}
```