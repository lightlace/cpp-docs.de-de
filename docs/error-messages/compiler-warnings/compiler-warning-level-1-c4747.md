---
title: Compilerwarnung (Stufe 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: ecaabd482049771b1d3915470a2be7a52e36d361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462386"
---
# <a name="compiler-warning-level-1-c4747"></a>Compilerwarnung (Stufe 1) C4747

Aufrufen von verwalteten "Entrypoint": verwalteter Code kann nicht ausgeführt werden, unter der Loadersperre, einschließlich des DLL-Einstiegspunkts und Aufrufen von DLL-Einstiegspunkt eingehen

Der Compiler hat einen (wahrscheinlichen) in MSIL kompilierte DLL-Einstiegspunkt gefunden.  Aufgrund der Probleme mit dem Laden einer DLL, deren Einstiegspunkt in MSIL kompiliert wurde, sind Sie dringend davon abgeraten, eine DLL-Einstiegspunktfunktion in MSIL kompiliert.

Weitere Informationen finden Sie unter [Initialization of Mixed Assemblies](../../dotnet/initialization-of-mixed-assemblies.md) und [Linkertoolfehler LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Kompilieren Sie das Modul mit nicht **"/ CLR"**.

1. Markieren Sie die Einstiegspunktfunktion mit `#pragma unmanaged`.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4747 generiert.

```
// C4747.cpp
// compile with: /clr /c /W1
// C4747 expected
#include <windows.h>

// Uncomment the following line to resolve.
// #pragma unmanaged

BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {
   return TRUE;
};
```